# UserAccessControlApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**generateAccessReport**](UserAccessControlApi.md#generateAccessReport) | **GET** /access-control/user/generate-access-report | Generate Access Report
[**getPendingRequests**](UserAccessControlApi.md#getPendingRequests) | **GET** /access-control/user/pending-request-history | Get Pending Access Requests
[**getRequests**](UserAccessControlApi.md#getRequests) | **GET** /access-control/user/request-history | Get Full User Request History
[**requestAccessChange**](UserAccessControlApi.md#requestAccessChange) | **POST** /access-control/user/request-change | Request Access Change



## generateAccessReport

Generate Access Report

generate_access_report
Generates a system access report for the current user token.

Returns
-------
 : AccessReportResponse
    The access report object which includes a description of
    access on a per component:role basis.

See Also (optional)
--------

Examples (optional)
--------

### Example

```bash
landing-portal-api.sh generateAccessReport
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**AccessReportResponse**](AccessReportResponse.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getPendingRequests

Get Pending Access Requests

get_pending_access_requests
For the current logged in user retrieves all of the entries in the 
access request table which have PENDING_APPROVAL status.
Note that the item format is directly mappable to the dynamodb entry.

Arguments
----------

Returns
-------
 : AccessRequestList
    A list of access request entries in the table

See Also (optional)
--------

Examples (optional)
--------

### Example

```bash
landing-portal-api.sh getPendingRequests
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


## getRequests

Get Full User Request History

get_full_user_request_history
For the current logged in user retrieves all of the entries in the 
access request table. Note that the item format is directly mappable
to the dynamodb entry.

Arguments
----------

Returns
-------
 : AccessRequestList
    A list of access request entries in the table

See Also (optional)
--------

Examples (optional)
--------

### Example

```bash
landing-portal-api.sh getRequests
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


## requestAccessChange

Request Access Change

request_access_change
If you supply an access report which has differences to the current 
token access levels, will send an email to the configured email addresses
which details the differences in the authorisation.

Adds an entry to the request access table which has the PENDING_APPROVAL 
status and encodes the username/request ID.

Will return a failure status if the user has a pending request which is too 
recent based on the config minimum days value.

Arguments
----------
access_report : AccessReport
    The desired access levels in the form of an access report

send_email : bool = True
    Should an alert email be sent?

Returns
-------
 : AccessRequestResponse
    Status saying whether or not the request was emailed successfully. 

Raises
------
HTTPException
    Raises 500 error if something goes wrong during process.

See Also (optional)
--------

Examples (optional)
--------

### Example

```bash
landing-portal-api.sh requestAccessChange  send_email=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **accessReport** | [**AccessReport**](AccessReport.md) |  |
 **sendEmail** | **boolean** |  | [optional] [default to true]

### Return type

[**AccessRequestResponse**](AccessRequestResponse.md)

### Authorization

[OAuth2PasswordBearer](../README.md#OAuth2PasswordBearer)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

