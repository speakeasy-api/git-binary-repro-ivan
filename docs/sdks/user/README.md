# User
(*user*)

## Overview

Operations about user

Find out more about our store
<http://swagger.io>

### Available Operations

* [create_user](#create_user) - Create user
* [create_users_with_array_input](#create_users_with_array_input) - Creates list of users with given input array
* [create_users_with_list_input](#create_users_with_list_input) - Creates list of users with given input array
* [login_user](#login_user) - Logs user into the system
* [logout_user](#logout_user) - Logs out current logged in user session
* [get_user_by_name](#get_user_by_name) - Get user by user name
* [update_user](#update_user) - Updated user
* [delete_user](#delete_user) - Delete user

## create_user

This can only be done by the logged in user.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="createUser" method="post" path="/user" -->
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

req = Models::Components::User.new()

res = s.user.create_user(request: req)

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                               | Type                                                    | Required                                                | Description                                             |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| `request`                                               | [Models::Components::User](../../models/shared/user.md) | :heavy_check_mark:                                      | The request object to use for the request.              |

### Response

**[T.nilable(Models::Operations::CreateUserResponse)](../../models/operations/createuserresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## create_users_with_array_input

Creates list of users with given input array

### Example Usage

<!-- UsageSnippet language="ruby" operationID="createUsersWithArrayInput" method="post" path="/user/createWithArray" -->
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

req = []

res = s.user.create_users_with_array_input(request: req)

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                               | Type                                                    | Required                                                | Description                                             |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| `request`                                               | [T::Array[Models::Components::User]](../../models//.md) | :heavy_check_mark:                                      | The request object to use for the request.              |

### Response

**[T.nilable(Models::Operations::CreateUsersWithArrayInputResponse)](../../models/operations/createuserswitharrayinputresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## create_users_with_list_input

Creates list of users with given input array

### Example Usage

<!-- UsageSnippet language="ruby" operationID="createUsersWithListInput" method="post" path="/user/createWithList" -->
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

req = [
  Models::Components::User.new(),
]

res = s.user.create_users_with_list_input(request: req)

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                               | Type                                                    | Required                                                | Description                                             |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| `request`                                               | [T::Array[Models::Components::User]](../../models//.md) | :heavy_check_mark:                                      | The request object to use for the request.              |

### Response

**[T.nilable(Models::Operations::CreateUsersWithListInputResponse)](../../models/operations/createuserswithlistinputresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## login_user

Logs user into the system

### Example Usage

<!-- UsageSnippet language="ruby" operationID="loginUser" method="get" path="/user/login" -->
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

res = s.user.login_user(username: 'Lou12', password: '0eXK37kzaSWlD1X')

unless res.res.nil?
  # handle response
end

```

### Parameters

| Parameter                            | Type                                 | Required                             | Description                          |
| ------------------------------------ | ------------------------------------ | ------------------------------------ | ------------------------------------ |
| `username`                           | *::String*                           | :heavy_check_mark:                   | The user name for login              |
| `password`                           | *::String*                           | :heavy_check_mark:                   | The password for login in clear text |

### Response

**[T.nilable(Models::Operations::LoginUserResponse)](../../models/operations/loginuserresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## logout_user

Logs out current logged in user session

### Example Usage

<!-- UsageSnippet language="ruby" operationID="logoutUser" method="get" path="/user/logout" -->
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

res = s.user.logout_user()

if res.status_code == 200
  # handle response
end

```

### Response

**[T.nilable(Models::Operations::LogoutUserResponse)](../../models/operations/logoutuserresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## get_user_by_name

Get user by user name

### Example Usage

<!-- UsageSnippet language="ruby" operationID="getUserByName" method="get" path="/user/{username}" -->
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

res = s.user.get_user_by_name(username: 'Edyth10')

unless res.body.nil?
  # handle response
end

```

### Parameters

| Parameter                                                  | Type                                                       | Required                                                   | Description                                                |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| `username`                                                 | *::String*                                                 | :heavy_check_mark:                                         | The name that needs to be fetched. Use user1 for testing.  |

### Response

**[T.nilable(Models::Operations::GetUserByNameResponse)](../../models/operations/getuserbynameresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## update_user

This can only be done by the logged in user.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="updateUser" method="put" path="/user/{username}" -->
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

res = s.user.update_user(username: 'Alison.Cassin', user: Models::Components::User.new())

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                               | Type                                                    | Required                                                | Description                                             |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| `username`                                              | *::String*                                              | :heavy_check_mark:                                      | name that need to be updated                            |
| `user`                                                  | [Models::Components::User](../../models/shared/user.md) | :heavy_check_mark:                                      | Updated user object                                     |

### Response

**[T.nilable(Models::Operations::UpdateUserResponse)](../../models/operations/updateuserresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## delete_user

This can only be done by the logged in user.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="deleteUser" method="delete" path="/user/{username}" -->
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

res = s.user.delete_user(username: 'Rita_Schuppe')

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                         | Type                              | Required                          | Description                       |
| --------------------------------- | --------------------------------- | --------------------------------- | --------------------------------- |
| `username`                        | *::String*                        | :heavy_check_mark:                | The name that needs to be deleted |

### Response

**[T.nilable(Models::Operations::DeleteUserResponse)](../../models/operations/deleteuserresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |