# FastAPI Bash client

## Overview

This is a Bash client script for accessing FastAPI service.

The script uses cURL underneath for making all REST calls.

## Usage

```shell
# Make sure the script has executable rights
$ chmod u+x landing-portal-api.sh

# Print the list of operations available on the service
$ ./landing-portal-api.sh -h

# Print the service description
$ ./landing-portal-api.sh --about

# Print detailed information about specific operation
$ ./landing-portal-api.sh <operationId> -h

# Make GET request
./landing-portal-api.sh --host http://<hostname>:<port> --accept xml <operationId> <queryParam1>=<value1> <header_key1>:<header_value2>

# Make GET request using arbitrary curl options (must be passed before <operationId>) to an SSL service using username:password
landing-portal-api.sh -k -sS --tlsv1.2 --host https://<hostname> -u <user>:<password> --accept xml <operationId> <queryParam1>=<value1> <header_key1>:<header_value2>

# Make POST request
$ echo '<body_content>' | landing-portal-api.sh --host <hostname> --content-type json <operationId> -

# Make POST request with simple JSON content, e.g.:
# {
#   "key1": "value1",
#   "key2": "value2",
#   "key3": 23
# }
$ echo '<body_content>' | landing-portal-api.sh --host <hostname> --content-type json <operationId> key1==value1 key2=value2 key3:=23 -

# Make POST request with form data
$ landing-portal-api.sh --host <hostname> <operationId> key1:=value1 key2:=value2 key3:=23

# Preview the cURL command without actually executing it
$ landing-portal-api.sh --host http://<hostname>:<port> --dry-run <operationid>

```

## Docker image

You can easily create a Docker image containing a preconfigured environment
for using the REST Bash client including working autocompletion and short
welcome message with basic instructions, using the generated Dockerfile:

```shell
docker build -t my-rest-client .
docker run -it my-rest-client
```

By default you will be logged into a Zsh environment which has much more
advanced auto completion, but you can switch to Bash, where basic autocompletion
is also available.

## Shell completion

### Bash

The generated bash-completion script can be either directly loaded to the current Bash session using:

```shell
source landing-portal-api.sh.bash-completion
```

Alternatively, the script can be copied to the `/etc/bash-completion.d` (or on OSX with Homebrew to `/usr/local/etc/bash-completion.d`):

```shell
sudo cp landing-portal-api.sh.bash-completion /etc/bash-completion.d/landing-portal-api.sh
```

#### OS X

On OSX you might need to install bash-completion using Homebrew:

```shell
brew install bash-completion
```

and add the following to the `~/.bashrc`:

```shell
if [ -f $(brew --prefix)/etc/bash_completion ]; then
  . $(brew --prefix)/etc/bash_completion
fi
```

### Zsh

In Zsh, the generated `_landing-portal-api.sh` Zsh completion file must be copied to one of the folders under `$FPATH` variable.

## Documentation for API Endpoints

All URIs are relative to **

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AccessCheckApi* | [**checkGeneralAccess**](docs/AccessCheckApi.md#checkgeneralaccess) | **GET** /check-access/general | Check General Access
*AccessCheckApi* | [**checkPublicAccess**](docs/AccessCheckApi.md#checkpublicaccess) | **GET** /check-access/public | Check Public Access
*AdminAccessControlApi* | [**addNote**](docs/AdminAccessControlApi.md#addnote) | **POST** /access-control/admin/add-note | Add Note
*AdminAccessControlApi* | [**changeRequestState**](docs/AdminAccessControlApi.md#changerequeststate) | **POST** /access-control/admin/change-request-state | Change Request State
*AdminAccessControlApi* | [**deleteRequest**](docs/AdminAccessControlApi.md#deleterequest) | **POST** /access-control/admin/delete-request | Do Delete Request
*AdminAccessControlApi* | [**getAllPendingRequests**](docs/AdminAccessControlApi.md#getallpendingrequests) | **GET** /access-control/admin/all-pending-request-history | All Pending Request History
*AdminAccessControlApi* | [**getAllPendingRequestsForUser**](docs/AdminAccessControlApi.md#getallpendingrequestsforuser) | **GET** /access-control/admin/user-pending-request-history | User Pending Request History
*AdminAccessControlApi* | [**getAllRequests**](docs/AdminAccessControlApi.md#getallrequests) | **GET** /access-control/admin/all-request-history | All Request History
*AdminAccessControlApi* | [**getAllRequestsForUser**](docs/AdminAccessControlApi.md#getallrequestsforuser) | **GET** /access-control/admin/user-request-history | User Request History
*DefaultApi* | [**root**](docs/DefaultApi.md#root) | **GET** / | Root
*UserAccessControlApi* | [**generateAccessReport**](docs/UserAccessControlApi.md#generateaccessreport) | **GET** /access-control/user/generate-access-report | Generate Access Report
*UserAccessControlApi* | [**getPendingRequests**](docs/UserAccessControlApi.md#getpendingrequests) | **GET** /access-control/user/pending-request-history | Get Pending Access Requests
*UserAccessControlApi* | [**getRequests**](docs/UserAccessControlApi.md#getrequests) | **GET** /access-control/user/request-history | Get Full User Request History
*UserAccessControlApi* | [**requestAccessChange**](docs/UserAccessControlApi.md#requestaccesschange) | **POST** /access-control/user/request-change | Request Access Change


## Documentation For Models

 - [AccessLevel](docs/AccessLevel.md)
 - [AccessReport](docs/AccessReport.md)
 - [AccessReportResponse](docs/AccessReportResponse.md)
 - [AccessRequestList](docs/AccessRequestList.md)
 - [AccessRequestResponse](docs/AccessRequestResponse.md)
 - [AccessRequestStatusChange](docs/AccessRequestStatusChange.md)
 - [ChangeStateStatus](docs/ChangeStateStatus.md)
 - [ComponentName](docs/ComponentName.md)
 - [DeleteAccessRequest](docs/DeleteAccessRequest.md)
 - [HTTPValidationError](docs/HTTPValidationError.md)
 - [IntendedUserType](docs/IntendedUserType.md)
 - [LocationInner](docs/LocationInner.md)
 - [ReportAuthorisationComponent](docs/ReportAuthorisationComponent.md)
 - [ReportComponentRole](docs/ReportComponentRole.md)
 - [RequestAccessTableItem](docs/RequestAccessTableItem.md)
 - [RequestAddNote](docs/RequestAddNote.md)
 - [RequestStatus](docs/RequestStatus.md)
 - [Status](docs/Status.md)
 - [User](docs/User.md)
 - [ValidationError](docs/ValidationError.md)


## Documentation For Authorization


## OAuth2PasswordBearer


- **Type**: OAuth
- **Flow**: password
- **Token URL**: token
- **Scopes**: N/A

