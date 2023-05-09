# API :page_with_curl: 0x16-api_advanced

## About this project :mortar_board:
In this project i continued practicing with APIs by using the [Reddit API](https://www.reddit.com/dev/api/).

## Task files description:

  * [0-subs.py](./0-subs.py): Python function that returns the total number of
  subscribers for a given subreddit.
  * Returns `0` if an invalid subreddit is given.

  * [1-top_ten.py](./1-top_ten.py): Python function that prints the top ten
  hottest posts for a given subreddit.
  * Prints `None` if an invalid subreddit is given.

  * [2-recurse.py](./2-recurse.py): Python function that recursively returns a
  list of titles for all hot articles on a given subreddit.
  * Returns `None` if no results are found on the given subreddit.

  * [100-count.py](./100-count.py): Python function that recursively prints a
  sorted count of given keywords parsed from titles of all hot articles on a given
  subreddit.
  * Keywords are case-insensitive and delimited by spaces.
  * Results are printed in descending order by count.
  * Words with identical counts are sorted alphabetically.
  * Words with no matches are skipped.
  * Results are based on the number of times a keyword appears - ie.,
  `java java java` counts as three separate instances of `java`.
