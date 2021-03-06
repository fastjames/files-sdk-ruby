# Request

## Example Request Object

```
{
  "id": 1,
  "path": "",
  "source": "",
  "destination": "",
  "automation_id": "",
  "user_display_name": ""
}
```

* `id` (int64): Request ID
* `path` (string): Folder path This must be slash-delimited, but it must neither start nor end with a slash. Maximum of 5000 characters.
* `source` (string): Source filename, if applicable
* `destination` (string): Destination filename
* `automation_id` (string): ID of automation that created request
* `user_display_name` (string): User making the request (if applicable)
* `user_ids` (string): A list of user IDs to request the file from. If sent as a string, it should be comma-delimited.
* `group_ids` (string): A list of group IDs to request the file from. If sent as a string, it should be comma-delimited.


---

## List Requests

```
Files::Request.list(
  page: 1, 
  per_page: 1, 
  mine: true
)
```

### Parameters

* `page` (int64): Current page number.
* `per_page` (int64): Number of records to show per page.  (Max: 10,000, 1,000 or less is recommended).
* `action` (string): Deprecated: If set to `count` returns a count of matching records rather than the records themselves.
* `mine` (boolean): Only show requests of the current user?  (Defaults to true if current user is not a site admin.)


---

## List Requests by path

```
Files::Request.list_for(path, 
  page: 1, 
  per_page: 1, 
  mine: true
)
```

### Parameters

* `page` (int64): Current page number.
* `per_page` (int64): Number of records to show per page.  (Max: 10,000, 1,000 or less is recommended).
* `action` (string): Deprecated: If set to `count` returns a count of matching records rather than the records themselves.
* `path` (string): Required - Path to operate on.
* `mine` (boolean): Only show requests of the current user?  (Defaults to true if current user is not a site admin.)


---

## Create Request

```
Files::Request.create(path, 
  destination: "destination"
)
```

### Parameters

* `path` (string): Required - Folder path on which to request the file.
* `destination` (string): Required - Destination filename (without extension) to request.
* `user_ids` (string): A list of user IDs to request the file from. If sent as a string, it should be comma-delimited.
* `group_ids` (string): A list of group IDs to request the file from. If sent as a string, it should be comma-delimited.


---

## Delete Request

```
Files::Request.delete(id)
```

### Parameters

* `id` (int64): Required - Request ID.


---

## Create Request

```
request = Files::Request.find(1)
request.create(
  destination: "destination"
)
```

### Parameters

* `path` (string): Required - Folder path on which to request the file.
* `destination` (string): Required - Destination filename (without extension) to request.
* `user_ids` (string): A list of user IDs to request the file from. If sent as a string, it should be comma-delimited.
* `group_ids` (string): A list of group IDs to request the file from. If sent as a string, it should be comma-delimited.
