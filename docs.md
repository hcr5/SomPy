# Jeugdjournaal (Dutch Youth News) Python Library Documentation

---

## Installation

You can install the library via pip:

```bash
pip install jeugdjournaal
```

---

### `read_item(item_id)`
Fetch and parse an article from Jeugdjournaal by its ID.

**Attributes:**
- `item_id`: The ID of the article to fetch.

**Returns:**
- `Article` object with attributes:
  - `title` (str): The title of the article.
  - `content` (str): The content of the article.
  - `images` (list): A list of image URLs in the article.

**Example:**
```python
article = jeugdjournaal.read_item(1234567)
print(article.title, article.content, article.images)
```

---

### `get_poll_ids(item_id)`
Fetch poll IDs from an article by its ID (**Note**: Not all articles contain polls, it may raise an exception).

**Attributes:**
- `item_id`: The ID of the article to fetch poll IDs from.

**Returns:**
- `PollIds` object with attributes:
  - `id_1` (str): The ID of the first poll option.
  - `id_2` (str): The ID of the second poll option.

**Example:**
```python
poll_ids = jeugdjournaal.get_poll_ids(1234567)
print(poll_ids.id_1, poll_ids.id_2)
```

---

### `vote_in_poll(vote_id)`
Vote in a poll using its ID.

**Attributes:**
- `vote_id`: The ID of the poll option to vote for.

**Example:**
```python
jeugdjournaal.vote_in_poll(ABC)
```

---

### `get_poll_data(item_id)`
Fetch poll data from an article by its ID. (**Note**: Not all articles contain polls, it may raise an exception).

**Attributes:**
- `item_id`: The ID of the article to fetch poll data from.

**Returns:**
- `PollResults` object with attributes:
  - `total_votes` (int): The total number of votes.
  - `answers` (list): A list of dictionaries with the keys "text" and "votes" for each poll answer.

**Example:**
```python
poll_data = jeugdjournaal.get_poll_data(1234567)
print(poll_data.total_votes, poll_data.answers)
```

---

### `get_comments(item_id, limit)`
Fetch comments from an article by its ID.

**Attributes:**
- `item_id`: The ID of the article to fetch comments from.
- `limit`: The maximum number of comments to fetch.

**Returns:**
- `list` of `Comment` objects, each with attributes:
  - `id` (int): The ID of the comment.
  - `content` (str): The content of the comment.
  - `name` (str): The name of the commenter.
  - `pinned` (bool): Whether the comment is pinned.
  - `published_at` (str): The publication date of the comment.

**Example:**
```python
comments = jeugdjournaal.get_comments(1234567, 5)
for comment in comments:
    print(comment.id, comment.content, comment.name, comment.pinned, comment.published_at)
```

---

### `get_comment_reactions(item_id, comment_id, limit)`
Fetch reactions to a specific comment by its ID.

**Attributes:**
- `item_id`: The ID of the article containing the comment.
- `comment_id`: The ID of the comment to fetch reactions for.
- `limit`: The maximum number of reactions to fetch.

**Returns:**
- `list` of `Reaction` objects, each with attributes:
  - `id` (int): The ID of the reaction.
  - `content` (str): The content of the reaction.
  - `name` (str): The name of the person who reacted.
  - `pinned` (bool): Whether the reaction is pinned.
  - `published_at` (str): The publication date of the reaction.

**Example:**
```python
reactions = jeugdjournaal.get_comment_reactions(1234567, 890, 5)
for reaction in reactions:
    print(reaction.id, reaction.content, reaction.name, reaction.pinned, reaction.published_at)
```

---

### `post_comment(item_id, name, content)`
Post a comment to an article. (**Note**: It will be visible on the Jeugdjournaal website once approved by moderators.)

**Attributes:**
- `item_id`: The ID of the article to post a comment to.
- `name`: The name of the commenter.
- `content`: The content of the comment.

**Example:**
```python
jeugdjournaal.post_comment(1234567, 'John Doe', 'This is a test comment.')
```

---

### `get_items(query, amount, page)`
Fetch a list of items from Jeugdjournaal.

**Parameters:**
- `query`: The search term. Leave unchanged for the latest articles.
- `amount`: The number of articles to retrieve.
- `page`: The starting page for the search.

**Returns:**
- `list` of `Item` objects, each with attributes:
  - `title` (str): The title of the item.
  - `id` (int): The ID of the item.
  - `published_at` (str): The publication date of the article.
  - `modified_at` (str): The modification date of the article.

**Example:**
```python
items = jeugdjournaal.get_items()
for item in items:
    print(item.title, item.id, item.published_at, item.modified_at)
```
