# HistoryExport

## Example HistoryExport Object

```
{
  "id": 1,
  "start_at": "2000-01-01T01:00:00Z",
  "end_at": "2000-01-01T01:00:00Z",
  "status": "ready",
  "query_action": "read",
  "query_interface": "ftp",
  "query_user_id": 1,
  "query_file_id": 1,
  "query_parent_id": 1,
  "query_path": "MyFile.txt",
  "query_folder": "Folder",
  "query_src": "SrcFolder",
  "query_destination": "DestFolder",
  "query_ip": "127.0.0.1",
  "query_username": "jerry",
  "query_failure_type": "bad_password",
  "query_target_id": 1,
  "query_target_name": "full",
  "query_target_permission": "full",
  "query_target_user_id": 1,
  "query_target_username": "jerry",
  "query_target_platform": "windows",
  "query_target_permission_set": "desktop_app"
}
```

* `id` (int64): History Export ID
* `start_at` (date-time): Start date/time of export range.
* `end_at` (date-time): End date/time of export range.
* `status` (string): Status of export.  Will be: `building` or `ready`
* `query_action` (string): Filter results by this this action type. Valid values: `create`, `read`, `update`, `destroy`, `move`, `login`, `failedlogin`, `copy`, `user_create`, `user_update`, `user_destroy`, `group_create`, `group_update`, `group_destroy`, `permission_create`, `permission_destroy`, `api_key_create`, `api_key_update`, `api_key_destroy`
* `query_interface` (string): Filter results by this this interface type. Valid values: `web`, `ftp`, `robot`, `jsapi`, `webdesktopapi`, `sftp`, `dav`, `desktop`, `restapi`, `scim`
* `query_user_id` (int64): Return results that are actions performed by the user indiciated by this User ID
* `query_file_id` (int64): Return results that are file actions related to the file indicated by this File ID
* `query_parent_id` (int64): Return results that are file actions inside the parent folder specified by this folder ID
* `query_path` (string): Return results that are file actions related to this path.
* `query_folder` (string): Return results that are file actions related to files or folders inside this folder path.
* `query_src` (string): Return results that are file moves originating from this path.
* `query_destination` (string): Return results that are file moves with this path as destination.
* `query_ip` (string): Filter results by this IP address.
* `query_username` (string): Filter results by this username.
* `query_failure_type` (string): If searching for Histories about login failures, this parameter restricts results to failures of this specific type.  Valid values: `expired_trial`, `account_overdue`, `locked_out`, `ip_mismatch`, `password_mismatch`, `site_mismatch`, `username_not_found`, `none`, `no_ftp_permission`, `no_web_permission`, `no_directory`, `errno_enoent`, `no_sftp_permission`, `no_dav_permission`, `no_restapi_permission`, `key_mismatch`, `region_mismatch`, `expired_access`, `desktop_ip_mismatch`, `desktop_api_key_not_used_quickly_enough`, `disabled`
* `query_target_id` (int64): If searching for Histories about specific objects (such as Users, or API Keys), this paremeter restricts results to objects that match this ID.
* `query_target_name` (string): If searching for Histories about Users, Groups or other objects with names, this parameter restricts results to objects with this name/username.
* `query_target_permission` (string): If searching for Histories about Permisisons, this parameter restricts results to permissions of this level.
* `query_target_user_id` (int64): If searching for Histories about API keys, this parameter restricts results to API keys created by/for this user ID.
* `query_target_username` (string): If searching for Histories about API keys, this parameter restricts results to API keys created by/for this username.
* `query_target_platform` (string): If searching for Histories about API keys, this parameter restricts results to API keys associated with this platform.
* `query_target_permission_set` (string): If searching for Histories about API keys, this parameter restricts results to API keys with this permission set.
* `user_id` (int64): User ID.  Provide a value of `0` to operate the current session's user.


---

## List History Exports

```
Files::HistoryExport.list(
  user_id: 1, 
  page: 1, 
  per_page: 1
)
```

### Parameters

* `user_id` (int64): User ID.  Provide a value of `0` to operate the current session's user.
* `page` (int64): Current page number.
* `per_page` (int64): Number of records to show per page.  (Max: 10,000, 1,000 or less is recommended).
* `action` (string): Deprecated: If set to `count` returns a count of matching records rather than the records themselves.


---

## Show History Export

```
Files::HistoryExport.find(id)
```

### Parameters

* `id` (int64): Required - History Export ID.


---

## Create History Export

```
Files::HistoryExport.create(
  user_id: 1, 
  start_at: "2000-01-01T01:00:00Z", 
  end_at: "2000-01-01T01:00:00Z", 
  query_action: "read", 
  query_interface: "ftp", 
  query_user_id: 1, 
  query_file_id: 1, 
  query_parent_id: 1, 
  query_path: "MyFile.txt", 
  query_folder: "Folder", 
  query_src: "SrcFolder", 
  query_destination: "DestFolder", 
  query_ip: "127.0.0.1", 
  query_username: "jerry", 
  query_failure_type: "bad_password", 
  query_target_id: 1, 
  query_target_name: "full", 
  query_target_permission: "full", 
  query_target_user_id: 1, 
  query_target_username: "jerry", 
  query_target_platform: "windows", 
  query_target_permission_set: "desktop_app"
)
```

### Parameters

* `user_id` (int64): User ID.  Provide a value of `0` to operate the current session's user.
* `start_at` (string): Start date/time of export range.
* `end_at` (string): End date/time of export range.
* `query_action` (string): Filter results by this this action type. Valid values: `create`, `read`, `update`, `destroy`, `move`, `login`, `failedlogin`, `copy`, `user_create`, `user_update`, `user_destroy`, `group_create`, `group_update`, `group_destroy`, `permission_create`, `permission_destroy`, `api_key_create`, `api_key_update`, `api_key_destroy`
* `query_interface` (string): Filter results by this this interface type. Valid values: `web`, `ftp`, `robot`, `jsapi`, `webdesktopapi`, `sftp`, `dav`, `desktop`, `restapi`, `scim`
* `query_user_id` (int64): Return results that are actions performed by the user indiciated by this User ID
* `query_file_id` (int64): Return results that are file actions related to the file indicated by this File ID
* `query_parent_id` (int64): Return results that are file actions inside the parent folder specified by this folder ID
* `query_path` (string): Return results that are file actions related to this path.
* `query_folder` (string): Return results that are file actions related to files or folders inside this folder path.
* `query_src` (string): Return results that are file moves originating from this path.
* `query_destination` (string): Return results that are file moves with this path as destination.
* `query_ip` (string): Filter results by this IP address.
* `query_username` (string): Filter results by this username.
* `query_failure_type` (string): If searching for Histories about login failures, this parameter restricts results to failures of this specific type.  Valid values: `expired_trial`, `account_overdue`, `locked_out`, `ip_mismatch`, `password_mismatch`, `site_mismatch`, `username_not_found`, `none`, `no_ftp_permission`, `no_web_permission`, `no_directory`, `errno_enoent`, `no_sftp_permission`, `no_dav_permission`, `no_restapi_permission`, `key_mismatch`, `region_mismatch`, `expired_access`, `desktop_ip_mismatch`, `desktop_api_key_not_used_quickly_enough`, `disabled`
* `query_target_id` (int64): If searching for Histories about specific objects (such as Users, or API Keys), this paremeter restricts results to objects that match this ID.
* `query_target_name` (string): If searching for Histories about Users, Groups or other objects with names, this parameter restricts results to objects with this name/username.
* `query_target_permission` (string): If searching for Histories about Permisisons, this parameter restricts results to permissions of this level.
* `query_target_user_id` (int64): If searching for Histories about API keys, this parameter restricts results to API keys created by/for this user ID.
* `query_target_username` (string): If searching for Histories about API keys, this parameter restricts results to API keys created by/for this username.
* `query_target_platform` (string): If searching for Histories about API keys, this parameter restricts results to API keys associated with this platform.
* `query_target_permission_set` (string): If searching for Histories about API keys, this parameter restricts results to API keys with this permission set.


---

## Delete History Export

```
Files::HistoryExport.delete(id)
```

### Parameters

* `id` (int64): Required - History Export ID.


---

## Delete History Export

```
history_export = Files::HistoryExport.find(1)
history_export.delete
```

### Parameters

* `id` (int64): Required - History Export ID.
