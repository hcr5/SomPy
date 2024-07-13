```python
# Jeugdjournaal (Youth News) Python Library Documentation

---

### `read_item(ARTICLE_ID)`
Fetch and parse an article from Jeugdjournaal by its ID.

**Attributes:**
- `ARTICLE_ID` (str): The ID of the article to fetch.

**Returns:**
- `Article` object with attributes:
  - `title` (str): The title of the article.
  - `content` (str): The content of the article.
  - `images` (list): A list of image URLs in the article.

**Example:**
```python
article = jeugdjournaal.read_item('ARTICLE_ID_HERE')
print(article.title, article.content, article.images)
```

---

### `get_poll_ids(ARTICLE_ID)`
Fetch poll IDs from an article by its ID (Warning: Not all articles contain polls, it may raise an exception).

**Attributes:**
- `ARTICLE_ID` (str): The ID of the article to fetch poll IDs from.

**Returns:**
- `PollIds` object with attributes:
  - `option_1` (dict): A dictionary with the keys "id" and "text" for the first poll option.
  - `option_2` (dict): A dictionary with the keys "id" and "text" for the second poll option.

**Example:**
```python
poll_ids = jeugdjournaal.get_poll_ids('ARTICLE_ID_HERE')
print(poll_ids.option_1, poll_ids.option_2)
```

---

### `vote_in_poll(POLL_ID)`
Vote in a poll using its ID.

**Attributes:**
- `POLL_ID` (str): The ID of the poll option to vote for.

**Example:**
```python
jeugdjournaal.vote_in_poll('POLL_ID_HERE')
```

---

### `get_poll_data(ARTICLE_ID)`
Fetch poll data from an article by its ID.

**Attributes:**
- `ARTICLE_ID` (str): The ID of the article to fetch poll data from.

**Returns:**
- `PollResults` object with attributes:
  - `total_votes` (int): The total number of votes.
  - `answers` (list): A list of dictionaries with the keys "text" and "votes" for each poll answer.

**Example:**
```python
poll_data = jeugdjournaal.get_poll_data('ARTICLE_ID_HERE')
print(poll_data.total_votes, poll_data.answers)
```

---

### `get_comments(ARTICLE_ID, COMMENT_LIMIT)`
Fetch comments from an article by its ID.

**Attributes:**
- `ARTICLE_ID` (str): The ID of the article to fetch comments from.
- `COMMENT_LIMIT` (int): The maximum number of comments to fetch.

**Returns:**
- `list` of `Comment` objects, each with attributes:
  - `comment_id` (str): The ID of the comment.
  - `comment_content` (str): The content of the comment.
  - `commenter_name` (str): The name of the commenter.
  - `is_pinned` (bool): Whether the comment is pinned.
  - `published_at` (str): The publication date of the comment.

**Example:**
```python
comments = jeugdjournaal.get_comments('ARTICLE_ID_HERE', 5)
for comment in comments:
    print(comment.comment_id, comment.comment_content, comment.commenter_name, comment.is_pinned, comment.published_at)
```

---

### `get_comment_reactions(ARTICLE_ID, COMMENT_ID, REACTION_LIMIT)`
Fetch reactions to a specific comment by its ID.

**Attributes:**
- `ARTICLE_ID` (str): The ID of the article containing the comment.
- `COMMENT_ID` (str): The ID of the comment to fetch reactions for.
- `REACTION_LIMIT` (int): The maximum number of reactions to fetch.

**Returns:**
- `list` of `Reaction` objects, each with attributes:
  - `reaction_id` (str): The ID of the reaction.
  - `reaction_content` (str): The content of the reaction.
  - `reactor_name` (str): The name of the person who reacted.
  - `is_pinned` (bool): Whether the reaction is pinned.
  - `published_at` (str): The publication date of the reaction.

**Example:**
```python
reactions = jeugdjournaal.get_comment_reactions('ARTICLE_ID_HERE', 'COMMENT_ID_HERE', 5)
for reaction in reactions:
    print(reaction.reaction_id, reaction.reaction_content, reaction.reactor_name, reaction.is_pinned, reaction.published_at)
```

---

### `post_comment(ARTICLE_ID, COMMENTER_NAME, COMMENT_CONTENT)`
Post a comment to an article.

**Attributes:**
- `ARTICLE_ID` (str): The ID of the article to post a comment to.
- `COMMENTER_NAME` (str): The name of the commenter.
- `COMMENT_CONTENT` (str): The content of the comment.

**Example:**
```python
jeugdjournaal.post_comment('ARTICLE_ID_HERE', 'COMMENTER_NAME_HERE', 'This is a test comment.')
```

---

### `get_items()`
Fetch a list of items from the main page of Jeugdjournaal.

**Returns:**
- `list` of `Item` objects, each with attributes:
  - `item_title` (str): The title of the item.
  - `item_id` (str): The ID of the item.

**Example:**
```python
items = jeugdjournaal.get_items()
for item in items:
    print(item.item_title, item.item_id)
```
