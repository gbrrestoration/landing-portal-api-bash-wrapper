# AdminAccessControlApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**addNote**](AdminAccessControlApi.md#addNote) | **POST** /access-control/admin/add-note | Add Note
[**changeRequestState**](AdminAccessControlApi.md#changeRequestState) | **POST** /access-control/admin/change-request-state | Change Request State
[**deleteRequest**](AdminAccessControlApi.md#deleteRequest) | **POST** /access-control/admin/delete-request | Do Delete Request
[**getAllPendingRequests**](AdminAccessControlApi.md#getAllPendingRequests) | **GET** /access-control/admin/all-pending-request-history | All Pending Request History
[**getAllPendingRequestsForUser**](AdminAccessControlApi.md#getAllPendingRequestsForUser) | **GET** /access-control/admin/user-pending-request-history | User Pending Request History
[**getAllRequests**](AdminAccessControlApi.md#getAllRequests) | **GET** /access-control/admin/all-request-history | All Request History
[**getAllRequestsForUser**](AdminAccessControlApi.md#getAllRequestsForUser) | **GET** /access-control/admin/user-request-history | User Request History



## addNote

Add Note

### Example

```bash
landing-portal-api.sh addNote
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **requestAddNote** | [**RequestAddNote**](RequestAddNote.md) |  |

### Return type

[**Status**](Status.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## changeRequestState

Change Request State

change_request_state
For the specified user/id etc will update the entry in the 
table of access requests with the new state and the desired 
note if included.

If desired, an email will be sent to the specified user email 
as per the request information.

Arguments
----------
change_request : AccessRequestStatusChange
    The change request object - see models.py 
send_email_alert : Optional[bool]
    Should the user be sent an email which updates them as to the 
    status change.

Returns
-------
 : ChangeStateStatus
    Success if updated, false and message otherwise

See Also (optional)
--------

Examples (optional)
--------

### Example

```bash
landing-portal-api.sh changeRequestState  send_email_alert=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **accessRequestStatusChange** | [**AccessRequestStatusChange**](AccessRequestStatusChange.md) |  |
 **sendEmailAlert** | **boolean** |  | [optional] [default to false]

### Return type

[**ChangeStateStatus**](ChangeStateStatus.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteRequest

Do Delete Request

delete_request
Will delete record for specified username/id.

Only allowed for sys admin admins - use with caution.

Arguments
----------
delete_request : DeleteAccessRequest
    Description of what to delete

Returns
-------
 : Status
    Success if deleted, will be true even if record doesn't exist

See Also (optional)
--------

Examples (optional)
--------

### Example

```bash
landing-portal-api.sh deleteRequest
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **deleteAccessRequest** | [**DeleteAccessRequest**](DeleteAccessRequest.md) |  |

### Return type

[**Status**](Status.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getAllPendingRequests

All Pending Request History

all_pending_request_history
Given admin read permissions, pulls all entries in the access request table.

Arguments
----------

Returns
-------
 : AccessRequestList
    list of access request items

See Also (optional)
--------

Examples (optional)
--------

### Example

```bash
landing-portal-api.sh getAllPendingRequests
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**AccessRequestList**](AccessRequestList.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getAllPendingRequestsForUser

User Pending Request History

user_pending_request_history
Given admin read permissions will pull the pending requests of
a specified username.

Arguments
----------
username : str
    The username to pull history for.

Returns
-------
 : AccessRequestList
    list of access request items

See Also (optional)
--------

Examples (optional)
--------

### Example

```bash
landing-portal-api.sh getAllPendingRequestsForUser  username=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **username** | **string** |  | [default to null]

### Return type

[**AccessRequestList**](AccessRequestList.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getAllRequests

All Request History

all_request_history
Given admin read permissions, pulls all entries in the access request table.

Arguments
----------

Returns
-------
 : AccessRequestList
    list of access request items

See Also (optional)
--------

Examples (optional)
--------

### Example

```bash
landing-portal-api.sh getAllRequests
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**AccessRequestList**](AccessRequestList.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getAllRequestsForUser

User Request History

user_request_history
Given admin read permissions will pull the request history of
a specified username.

Arguments
----------
username : str
    The username to pull history for.

Returns
-------
 : AccessRequestList
    list of access request items

See Also (optional)
--------

Examples (optional)
--------

### Example

```bash
landing-portal-api.sh getAllRequestsForUser  username=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **username** | **string** |  | [default to null]

### Return type

[**AccessRequestList**](AccessRequestList.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

