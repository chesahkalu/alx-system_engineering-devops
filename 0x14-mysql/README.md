# Mysql :page_with_curl: 0x14-mysql

## About this project :bulb:

In this project, I learned how to set up database backups on web servers using
using `MySQL` in a `Ubuntu` server. I configured the primary-replica setup(Master-Slave replication) on two servers.
This is an outline of the steps I took to configure a MySQL instance on one server as a source database and then configure a 
MySQL instance on another server to function as its replica. It also includes an overview of how MySQL handles replication.

* Install Mysql on both servers:
    - copy signature key for package verification at https://dev.mysql.com/doc/refman/5.7/en/checking-gpg-signature.html
    key is present in file 'signature.key'. Save key in a file 'signature.key' on server
    - add the key to the server's apt keyring:
    sudo apt-key add signature.key
    - add the apt repo to the server's sources list:
    sudo sh -c 'echo "deb http://repo.mysql.com/apt/ubuntu bionic mysql-5.7" >> /etc/apt/sources.list.d/mysql.list'
    - update the package list:
    sudo apt-get update
    - Install the mysql server 5.7:
    sudo apt install -f mysql-client=5.7* mysql-community-server=5.7* mysql-server=5.7*

    - Ensure that Alx public key is in the '/.ssh/authorized_keys' file of the ubuntu user on both servers to enable access to the servers for check

    - Create a Alx user on both servers with given username and password and host, to enable access to the Mysql servers for check:
    `CREATE USER ‘user’@‘localhost' IDENTIFIED WITH mysql_native_password BY 'password';`

    - Make sure Alx user has permission to check the primary/replica status of your databases:
    `GRANT REPLICATION SLAVE ON *.* TO 'user'@'localhost';`

* Create a database on the primary server, create a table and add data to it:
    - replicate the database on the replica server
    - Make sure Alx has SELECT priveleges on table to check table exists and has data:
    `GRANT SELECT ON tyrell_corp.nexus6 TO 'holberton_user'@'localhost';`

* Each replica in a MySQL replication environment connects to the source database with a username and password. 
Replicas can connect using any MySQL user profile that exists on the source database and has the appropriate privileges.
    - Create a user('replica_user') on the source database that the replica can use to connect to the source database, with prefered password and
    host = '%' to enable access to the source database from any host and not only from replica server.
    `CREATE USER ‘replica_user’@‘%’ IDENTIFIED WITH mysql_native_password BY 'password';`
    - Grant the user the privileges required for replication- The user must have the REPLICATION SLAVE privilege;
    `GRANT REPLICATION SLAVE ON *.* TO 'replica_user'@'%';`
    - Make sure Alx has SELECT priveleges on mysql.user to confirm the replica exist
'GRANT SELECT ON mysql.user to 'holberton_user'@'localhost';'
    - Flush privileges:
    `flush privileges;`

* Set up Mysql config file on Source and Replica server with correct details as in file 4-mysql_configuration_primary and 4-mysql_configuration_replica
    - commenting out bind-address= bind address is the ip address of the server. This is done to enable access to the server from any host and not only from localhost
    - set server-id to 1 on source server and 2 on replica server, both must be unique
    - set log_bin to /var/log/mysql/mysql-bin.log on source server and /var/log/mysql/mysql-bin.log on replica server. This is the location of the binary log file
    Your replica server must read the source’s binary log file so it knows when and how to replicate the source’s data.
    - set database name to replicate on both servers
    - Lastly, add a relay-log directive on replica config file defining the location of the replica’s relay log file - /var/log/mysql/mysql-relay-bin.log
    - sudo systemctl restart mysql - restart mysql service on both servers

* Retrieve binary log co-ordinates from source: this is the position from which the replica will start copying database events. Record the File name and the Position value, as you will need these later when you initiate replication
    - mysql> show master status;
    ```
    +------------------+----------+--------------------+------------------+
    | File             | Position | Binlog_Do_DB       | Binlog_Ignore_DB |
    +------------------+----------+--------------------+------------------+
    | mysql-bin.000001 |      154 | tyrell_corp          |                |
    +------------------+----------+--------------------+------------------+
    ```
    save the File and Position values for later use - 'mysql-bin.000001' and '154'

* Configure the replica to connect to the source database
```
>CHANGE MASTER TO
  >MASTER_HOST='source_server_ip',
  >MASTER_USER='replica_user',
  >MASTER_PASSWORD='password',
  >MASTER_LOG_FILE='mysql-bin.000001',
  >MASTER_LOG_POS=154;
```

    - Start the replica:
    `START SLAVE;`
    - Check the status of the replica:
    `SHOW SLAVE STATUS\G;`

* Allow connection on port 3306 on both servers (defualt port for mysql) to enable both servers to connect to each other
    - sudo ufw allow 3306/tcp

* Test the replica by creating a table on the source database and check if it is replicated on the replica database

## Files description :file_folder:

* [4-mysql_configuration_primary](./4-mysql_configuration_primary): The MySQL
`my.conf` configuration file used to set up my first server as a primary database
server on the database `tyrell_corp`.

* [4-mysql_configuration_replica](./4-mysql_configuration_replica): The MySQL
`my.conf` configuration file used to set up my second server as the replica
database server on the database `tyrell_corp`.

* [5-mysql_backup](./5-mysql_backup): Bash script that generates a compressed
`tar.gz` archive from a MySQL dump.
  * Usage: `./5-mysql_backup <MySQL root password>`
  * Generates a dump containing all MySQL databases on the root server.
  * Names the resulting tar archive in the format `day-month-year.tar.gz`.

