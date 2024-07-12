# Jeugdjournaal Python Library Docs

### Functions
---
#### `jeugdjournaal.get_items()`
Retrieves a list of articles currently featured on the Jeugdjournaal homepage.

- **Returns:**
  - List of dictionaries, each containing `title` and `id` of an article.

##### Example:
```python
items = jeugdjournaal.get_items()
for item in items:
    print(item['title'], item['id'])
```

---

#### `jeugdjournaal.read_item(id)`
Retrieves details of a specific article identified by `id`.

- **Parameters:**
  - `id` (str): Unique identifier of the article.

- **Returns:**
  - Dictionary with `title`, `content`, and `image_urls` of the article.

##### Example:
```python
article = jeugdjournaal.read_item('2528544')
print(article['title'])
print(article['content'])
print(article['image_urls'])
```

---

#### `jeugdjournaal.get_poll_hashes(item_id)`
Retrieves poll information from a specific article identified by `item_id`.

- **Parameters:**
  - `item_id` (str): Unique identifier of the article.

- **Returns:**
  - JSON string containing poll hashes and their corresponding names (`hash_1`, `hash_1_name`, `hash_2`, `hash_2_name`).

##### Example:
```python
poll_hashes = jeugdjournaal.get_poll_hashes('2528544')
print(poll_hashes)
```

---

#### `jeugdjournaal.vote_in_poll(vote_hash)`
Votes in a poll using the provided `vote_hash`.

- **Parameters:**
  - `vote_hash` (str): Hash string representing the poll option to vote for.

- **Returns:**
  - JSON response from the API indicating success or failure of the vote.

##### Example:
```python
vote_response = jeugdjournaal.vote_in_poll('Zdf')
print(vote_response)
```

---

#### `jeugdjournaal.get_comments(item_id, limit)`
Retrieves comments associated with a specific article.

- **Parameters:**
  - `item_id` (str): Unique identifier of the article.
  - `limit` (int): Maximum number of comments to retrieve.

- **Returns:**
  - JSON response containing comments.

##### Example:
```python
comments = jeugdjournaal.get_comments('2528544', 10)
print(comments)
```

---

#### `jeugdjournaal.post_comment(item_id, name, content)`
Posts a comment to a specific article.

- **Parameters:**
  - `item_id` (str): Unique identifier of the article.
  - `name` (str): Name of the commenter.
  - `content` (str): Text content of the comment.

- **Returns:**
  - JSON response from the API indicating success or failure of posting the comment.

##### Example:
```python
comment_response = jeugdjournaal.post_comment('2528544', 'John Doe', 'This is a great article!')
print(comment_response)
```

---

#### `jeugdjournaal.get_comment_reactions(item_id, comment_id, limit)`
Retrieves reactions to a specific comment associated with an article.

- **Parameters:**
  - `item_id` (str): Unique identifier of the article.
  - `comment_id` (str): Unique identifier of the comment.
  - `limit` (int): Maximum number of reactions to retrieve.

- **Returns:**
  - JSON response containing reactions to the comment.

##### Example:
```python
reactions = jeugdjournaal.get_comment_reactions('2528544', '12345', 5)
print(reactions)
```
