## Jeugdjournaal (Youth News) Python Library

### `read_item(item_id)`
Fetch and parse an article from Jeugdjournaal by its ID.

**Attributes:**
- `item_id` (str): The ID of the article to fetch.

**Example:**
```python
article = jeugdjournaal.read_item('1234567')
```

### `get_poll_ids(item_id)`
Fetch poll IDs from an article by its ID.

**Attributes:**
- `item_id` (str): The ID of the article to fetch poll IDs from.

**Example:**
```python
poll_ids = jeugdjournaal.get_poll_ids('1234567')
```

### `vote_in_poll(vote_hash)`
Vote in a poll using its hash.

**Attributes:**
- `vote_hash` (str): The hash of the poll option to vote for.

**Example:**
```python
jeugdjournaal.vote_in_poll('abc123')
```

### `get_poll_data(item_id)`
Fetch poll data from an article by its ID.

**Attributes:**
- `item_id` (str): The ID of the article to fetch poll data from.

**Example:**
```python
poll_data = jeugdjournaal.get_poll_data('1234567')
```

### `get_comments(item_id, limit)`
Fetch comments from an article by its ID.

**Attributes:**
- `item_id` (str): The ID of the article to fetch comments from.
- `limit` (int): The maximum number of comments to fetch.

**Example:**
```python
comments = jeugdjournaal.get_comments('1234567', 5)
```

### `get_comment_reactions(item_id, comment_id, limit)`
Fetch reactions to a specific comment by its ID.

**Attributes:**
- `item_id` (str): The ID of the article containing the comment.
- `comment_id` (str): The ID of the comment to fetch reactions for.
- `limit` (int): The maximum number of reactions to fetch.

**Example:**
```python
reactions = jeugdjournaal.get_comment_reactions('1234567', '890', 5)
```

### `post_comment(item_id, name, content)`
Post a comment to an article.

**Attributes:**
- `item_id` (str): The ID of the article to post a comment to.
- `name` (str): The name of the commenter.
- `content` (str): The content of the comment.

**Example:**
```python
jeugdjournaal.post_comment('1234567', 'John Doe', 'This is a test comment.')
```

### `get_items()`
Fetch a list of items from the main page of Jeugdjournaal.

**Example:**
```python
items = jeugdjournaal.get_items()
```
