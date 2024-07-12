# API Documentation

## Functions

### `jeugdjournaal.get_poll_ids(item_id)`
Fetches poll IDs and names from an article.

#### Example
```python
poll_ids = jeugdjournaal.get_poll_ids(2528544)
print(poll_ids)
```

### `jeugdjournaal.vote_in_poll(vote_id)`
Votes in a poll using the provided ID.

#### Example
```python
response = jeugdjournaal.vote_in_poll('some_vote_id')
print(response)
```

### `jeugdjournaal.get_poll_data(item_id)`
Retrieves poll results from an article.

#### Example
```python
poll_results = jeugdjournaal.get_poll_data(2528544)
print(poll_results)
```

### `jeugdjournaal.get_comments(item_id, limit)`
Fetches comments for an article with a limit.

#### Example
```python
comments = jeugdjournaal.get_comments(2528544, 10)
print(comments)
```

### `jeugdjournaal.get_comment_reactions(item_id, comment_id, limit)`
Fetches reactions to a specific comment with a limit.

#### Example
```python
reactions = jeugdjournaal.get_comment_reactions(2528544, 'comment_id_here', 5)
print(reactions)
```

### `jeugdjournaal.post_comment(item_id, name, content)`
Posts a comment to an article.

#### Example
```python
comment_info = jeugdjournaal.post_comment(2528544, 'John Doe', 'Great article!')
print(comment_info)
```

### `jeugdjournaal.get_items()`
Fetches a list of items from the main page.

#### Example
```python
items = jeugdjournaal.get_items()
print(items)
```

### `jeugdjournaal.read_item(item_id)`
Reads and retrieves content from an article.

#### Example
```python
item_content = jeugdjournaal.read_item(2528544)
print(item_content)
```
```
