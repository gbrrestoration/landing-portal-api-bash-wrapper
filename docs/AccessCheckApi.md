# AccessCheckApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**checkGeneralAccess**](AccessCheckApi.md#checkGeneralAccess) | **GET** /check-access/general | Check General Access
[**checkPublicAccess**](AccessCheckApi.md#checkPublicAccess) | **GET** /check-access/public | Check Public Access



## checkGeneralAccess

Check General Access

Function Description
--------------------

Function used to determine if user has basic authentication
into the system - does not test any roles or permissions.   


Arguments
----------
user : User, optional
    The authenticated user - may or may not have the correct roles. 

Returns
-------
User
    Returns user information



See Also (optional)
--------

Examples (optional)
--------

### Example

```bash
landing-portal-api.sh checkGeneralAccess
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**User**](User.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## checkPublicAccess

Check Public Access

Function Description
--------------------

Checks if public access is possible.


Arguments
----------

Returns
-------
Status
    Success



See Also (optional)
--------

Examples (optional)
--------

### Example

```bash
landing-portal-api.sh checkPublicAccess
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**Status**](Status.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

