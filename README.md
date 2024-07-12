# ⚠️ THE DOCUMENTATION IS OUTDATED, WILL BE UPDATED TOMORROW ⚠️

# Jeugdjournaal (Youth News) Python
The `jeugdjournaal` library simplifies interaction with the Jeugdjournaal website and API (https://jeugdjournaal.nl). It provides functionalities to retrieve article details, participate in polls, read/post comments, and explore articles.

## Installation
You can install `jeugdjournaal` via pip:

```
pip install jeugdjournaal
```

## Example Usage
```python
import jeugdjournaal

# Example: Retrieve article details
article_id = '2528081'
article_details = jeugdjournaal.read_item(article_id)
print(article_details['title'])
print(article_details['content'])

# Example: Vote in a poll
poll_id = 'Zdf'
vote_response = jeugdjournaal.vote_in_poll(poll_id)
print(vote_response)

# Example: Retrieve comments
comments = jeugdjournaal.get_comments(article_id, limit=10)
print(comments)
```

## Documentation
For more details, refer to the [documentation](https://github.com/hcr5/SomPy/blob/main/docs.md)
