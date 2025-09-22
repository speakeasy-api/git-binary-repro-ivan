# openapi

Developer-friendly & type-safe Ruby SDK specifically catered to leverage *openapi* API.

<div align="left">
    <a href="https://www.speakeasy.com/?utm_source=openapi&utm_campaign=ruby"><img src="https://custom-icon-badges.demolab.com/badge/-Built%20By%20Speakeasy-212015?style=for-the-badge&logoColor=FBE331&logo=speakeasy&labelColor=545454" /></a>
    <a href="https://opensource.org/licenses/MIT">
        <img src="https://img.shields.io/badge/License-MIT-blue.svg" style="width: 100px; height: 28px;" />
    </a>
</div>


<br /><br />
> [!IMPORTANT]
> This SDK is not yet ready for production use. To complete setup please follow the steps outlined in your [workspace](https://app.speakeasy.com/org/ian/ian). Delete this section before > publishing to a package manager.

<!-- Start Summary [summary] -->
## Summary

Swagger Petstore: This is a sample server Petstore server.  You can find out more about Swagger at [http://swagger.io](http://swagger.io) or on [irc.freenode.net, #swagger](http://swagger.io/irc/).  For this sample, you can use the api key `special-key` to test the authorization filters.

For more information about the API: [Find out more about Swagger](http://swagger.io)
<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [openapi](#openapi)
  * [SDK Installation](#sdk-installation)
  * [SDK Example Usage](#sdk-example-usage)
  * [Authentication](#authentication)
  * [Available Resources and Operations](#available-resources-and-operations)
  * [Error Handling](#error-handling)
  * [Server Selection](#server-selection)
* [Development](#development)
  * [Maturity](#maturity)
  * [Contributions](#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start SDK Installation [installation] -->
## SDK Installation

The SDK can be installed using [RubyGems](https://rubygems.org/):

```bash
gem install specific_install
gem specific_install  
```
<!-- End SDK Installation [installation] -->

<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

req = Models::Components::PetInput.new(
  name: 'doggie',
  photo_urls: [
    'https://example.com/photo.png',
  ],
)

res = s.pet.add_pet(request: req)

if res.status_code == 200
  # handle response
end

```
<!-- End SDK Example Usage [usage] -->

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security scheme globally:

| Name            | Type   | Scheme       |
| --------------- | ------ | ------------ |
| `petstore_auth` | oauth2 | OAuth2 token |

To authenticate with the API the `petstore_auth` parameter must be set when initializing the SDK client instance. For example:
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

req = Models::Components::PetInput.new(
  name: 'doggie',
  photo_urls: [
    'https://example.com/photo.png',
  ],
)

res = s.pet.add_pet(request: req)

if res.status_code == 200
  # handle response
end

```

### Per-Operation Security Schemes

Some operations in this SDK require the security scheme to be specified at the request level. For example:
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new

res = s.pet.get_pet_by_id(security: Models::Operations::GetPetByIdSecurity.new(
    api_key: '<YOUR_API_KEY_HERE>',
  ), pet_id: 311_674)

unless res.body.nil?
  # handle response
end

```
<!-- End Authentication [security] -->

<!-- Start Available Resources and Operations [operations] -->
## Available Resources and Operations

<details open>
<summary>Available methods</summary>


### [pet](docs/sdks/pet/README.md)

* [add_pet](docs/sdks/pet/README.md#add_pet) - Add a new pet to the store
* [add_pet_raw](docs/sdks/pet/README.md#add_pet_raw) - Add a new pet to the store
* [update_pet](docs/sdks/pet/README.md#update_pet) - Update an existing pet
* [update_pet_raw](docs/sdks/pet/README.md#update_pet_raw) - Update an existing pet
* [find_pets_by_status](docs/sdks/pet/README.md#find_pets_by_status) - Finds Pets by status
* [~~find_pets_by_tags~~](docs/sdks/pet/README.md#find_pets_by_tags) - Finds Pets by tags :warning: **Deprecated**
* [get_pet_by_id](docs/sdks/pet/README.md#get_pet_by_id) - Find pet by ID
* [update_pet_with_form](docs/sdks/pet/README.md#update_pet_with_form) - Updates a pet in the store with form data
* [delete_pet](docs/sdks/pet/README.md#delete_pet) - Deletes a pet
* [upload_file](docs/sdks/pet/README.md#upload_file) - Uploads an image

### [store](docs/sdks/store/README.md)

* [get_inventory](docs/sdks/store/README.md#get_inventory) - Returns pet inventories by status
* [place_order](docs/sdks/store/README.md#place_order) - Place an order for a pet
* [get_order_by_id](docs/sdks/store/README.md#get_order_by_id) - Find purchase order by ID
* [delete_order](docs/sdks/store/README.md#delete_order) - Delete purchase order by ID

### [user](docs/sdks/user/README.md)

* [create_user](docs/sdks/user/README.md#create_user) - Create user
* [create_users_with_array_input](docs/sdks/user/README.md#create_users_with_array_input) - Creates list of users with given input array
* [create_users_with_list_input](docs/sdks/user/README.md#create_users_with_list_input) - Creates list of users with given input array
* [login_user](docs/sdks/user/README.md#login_user) - Logs user into the system
* [logout_user](docs/sdks/user/README.md#logout_user) - Logs out current logged in user session
* [get_user_by_name](docs/sdks/user/README.md#get_user_by_name) - Get user by user name
* [update_user](docs/sdks/user/README.md#update_user) - Updated user
* [delete_user](docs/sdks/user/README.md#delete_user) - Delete user

</details>
<!-- End Available Resources and Operations [operations] -->

<!-- Start Error Handling [errors] -->
## Error Handling

Handling errors in this SDK should largely match your expectations. All operations return a response object or raise an error.

By default an API error will raise a `Errors::APIError`, which has the following properties:

| Property       | Type                                    | Description           |
|----------------|-----------------------------------------|-----------------------|
| `message`     | *string*                                 | The error message     |
| `status_code`  | *int*                                   | The HTTP status code  |
| `raw_response` | *Faraday::Response*                     | The raw HTTP response |
| `body`        | *string*                                 | The response content  |

When custom error responses are specified for an operation, the SDK may also throw their associated exception. You can refer to respective *Errors* tables in SDK docs for more details on possible exception types for each operation. For example, the `add_pet` method throws the following exceptions:

| Error Type       | Status Code | Content Type |
| ---------------- | ----------- | ------------ |
| Errors::APIError | 4XX, 5XX    | \*/\*        |

### Example

```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

begin
    req = Models::Components::PetInput.new(
      name: 'doggie',
      photo_urls: [
        'https://example.com/photo.png',
      ],
    )

    res = s.pet.add_pet(request: req)

    if res.status_code == 200
      # handle response
    end
rescue Errors::APIError => e
  # handle default exception
  raise e
end

```
<!-- End Error Handling [errors] -->

<!-- Start Server Selection [server] -->
## Server Selection

### Override Server URL Per-Client

The default server can be overridden globally by passing a URL to the `server_url (String)` optional parameter when initializing the SDK client instance. For example:
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      server_url: 'http://petstore.swagger.io/v2',
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

req = Models::Components::PetInput.new(
  name: 'doggie',
  photo_urls: [
    'https://example.com/photo.png',
  ],
)

res = s.pet.add_pet(request: req)

if res.status_code == 200
  # handle response
end

```
<!-- End Server Selection [server] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

# Development

## Maturity

This SDK is in beta, and there may be breaking changes between versions without a major version update. Therefore, we recommend pinning usage
to a specific package version. This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

## Contributions

While we value open-source contributions to this SDK, this library is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation. 
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release. 

### SDK Created by [Speakeasy](https://www.speakeasy.com/?utm_source=openapi&utm_campaign=ruby)
