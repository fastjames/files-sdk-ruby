# FileComment

## Example FileComment Object

```
{
  "id": 1,
  "body": "What a great file!",
  "reactions": [

  ]
}
```

* `id` (int64): File Comment ID
* `body` (string): Comment body.
* `reactions` (array): Reactions to this comment.
* `path` (string): File path.


---

## List File Comments by path

```
Files::FileComment.list_for(path, 
  page: 1, 
  per_page: 1
)
```

### Parameters

* `page` (int64): Current page number.
* `per_page` (int64): Number of records to show per page.  (Max: 10,000, 1,000 or less is recommended).
* `action` (string): Deprecated: If set to `count` returns a count of matching records rather than the records themselves.
* `path` (string): Required - Path to operate on.


---

## Create File Comment

```
Files::FileComment.create(
  body: "body", 
  path: "path"
)
```

### Parameters

* `body` (string): Required - Comment body.
* `path` (string): Required - File path.


---

## Update File Comment

```
Files::FileComment.update(id, 
  body: "body"
)
```

### Parameters

* `id` (int64): Required - File Comment ID.
* `body` (string): Required - Comment body.


---

## Delete File Comment

```
Files::FileComment.delete(id)
```

### Parameters

* `id` (int64): Required - File Comment ID.


---

## Update File Comment

```
file_comment = Files::FileComment.find(1)
file_comment.update(
  body: "body"
)
```

### Parameters

* `id` (int64): Required - File Comment ID.
* `body` (string): Required - Comment body.


---

## Delete File Comment

```
file_comment = Files::FileComment.find(1)
file_comment.delete
```

### Parameters

* `id` (int64): Required - File Comment ID.
