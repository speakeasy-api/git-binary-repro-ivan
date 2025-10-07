# Pet
(*pet*)

## Overview

Everything about your Pets

Find out more
<http://swagger.io>

### Available Operations

* [add_pet](#add_pet) - Add a new pet to the store
* [add_pet_raw](#add_pet_raw) - Add a new pet to the store
* [update_pet](#update_pet) - Update an existing pet
* [update_pet_raw](#update_pet_raw) - Update an existing pet
* [find_pets_by_status](#find_pets_by_status) - Finds Pets by status
* [~~find_pets_by_tags~~](#find_pets_by_tags) - Finds Pets by tags :warning: **Deprecated**
* [get_pet_by_id](#get_pet_by_id) - Find pet by ID
* [update_pet_with_form](#update_pet_with_form) - Updates a pet in the store with form data
* [delete_pet](#delete_pet) - Deletes a pet
* [upload_file](#upload_file) - Uploads an image

## add_pet

Add a new pet to the store

### Example Usage

<!-- UsageSnippet language="ruby" operationID="addPet" method="post" path="/pet" -->
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

### Parameters

| Parameter                                                       | Type                                                            | Required                                                        | Description                                                     |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| `request`                                                       | [Models::Components::PetInput](../../models/shared/petinput.md) | :heavy_check_mark:                                              | The request object to use for the request.                      |

### Response

**[T.nilable(Models::Operations::AddPetResponse)](../../models/operations/addpetresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## add_pet_raw

Add a new pet to the store

### Example Usage

<!-- UsageSnippet language="ruby" operationID="addPet_raw" method="post" path="/pet" -->
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

req = "{\"photoUrls\":[\"https://example.com/photo.png\"],\"name\":\"doggie\"}".encode()

res = s.pet.add_pet_raw(request: req)

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                  | Type                                       | Required                                   | Description                                |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ | ------------------------------------------ |
| `request`                                  | [::String](../../models/shared/pet.md)     | :heavy_check_mark:                         | The request object to use for the request. |

### Response

**[T.nilable(Models::Operations::AddPetRawResponse)](../../models/operations/addpetrawresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## update_pet

Update an existing pet

### Example Usage

<!-- UsageSnippet language="ruby" operationID="updatePet" method="put" path="/pet" -->
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

res = s.pet.update_pet(request: req)

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                                       | Type                                                            | Required                                                        | Description                                                     |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| `request`                                                       | [Models::Components::PetInput](../../models/shared/petinput.md) | :heavy_check_mark:                                              | The request object to use for the request.                      |

### Response

**[T.nilable(Models::Operations::UpdatePetResponse)](../../models/operations/updatepetresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## update_pet_raw

Update an existing pet

### Example Usage

<!-- UsageSnippet language="ruby" operationID="updatePet_raw" method="put" path="/pet" -->
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

req = "{\"name\":\"doggie\",\"photoUrls\":[\"https://example.com/photo.png\"]}".encode()

res = s.pet.update_pet_raw(request: req)

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                  | Type                                       | Required                                   | Description                                |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ | ------------------------------------------ |
| `request`                                  | [::String](../../models/shared/pet.md)     | :heavy_check_mark:                         | The request object to use for the request. |

### Response

**[T.nilable(Models::Operations::UpdatePetRawResponse)](../../models/operations/updatepetrawresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## find_pets_by_status

Multiple status values can be provided with comma separated strings

### Example Usage

<!-- UsageSnippet language="ruby" operationID="findPetsByStatus" method="get" path="/pet/findByStatus" -->
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

res = s.pet.find_pets_by_status(status: [
  Models::Operations::Status::AVAILABLE,
])

unless res.body.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                 | Type                                                                      | Required                                                                  | Description                                                               |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `status`                                                                  | T::Array<[Models::Operations::Status](../../models/operations/status.md)> | :heavy_check_mark:                                                        | Status values that need to be considered for filter                       |

### Response

**[T.nilable(Models::Operations::FindPetsByStatusResponse)](../../models/operations/findpetsbystatusresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## ~~find_pets_by_tags~~

Muliple tags can be provided with comma separated strings. Use tag1, tag2, tag3 for testing.

> :warning: **DEPRECATED**: This will be removed in a future release, please migrate away from it as soon as possible.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="findPetsByTags" method="get" path="/pet/findByTags" -->
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

res = s.pet.find_pets_by_tags(tags: [])

unless res.body.nil?
  # handle response
end

```

### Parameters

| Parameter            | Type                 | Required             | Description          |
| -------------------- | -------------------- | -------------------- | -------------------- |
| `tags`               | T::Array<*::String*> | :heavy_check_mark:   | Tags to filter by    |

### Response

**[T.nilable(Models::Operations::FindPetsByTagsResponse)](../../models/operations/findpetsbytagsresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## get_pet_by_id

Returns a single pet

### Example Usage

<!-- UsageSnippet language="ruby" operationID="getPetById" method="get" path="/pet/{petId}" -->
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

### Parameters

| Parameter                                                                               | Type                                                                                    | Required                                                                                | Description                                                                             |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `security`                                                                              | [Models::Operations::GetPetByIdSecurity](../../models/operations/getpetbyidsecurity.md) | :heavy_check_mark:                                                                      | The security requirements to use for the request.                                       |
| `pet_id`                                                                                | *::Integer*                                                                             | :heavy_check_mark:                                                                      | ID of pet to return                                                                     |

### Response

**[T.nilable(Models::Operations::GetPetByIdResponse)](../../models/operations/getpetbyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## update_pet_with_form

Updates a pet in the store with form data

### Example Usage

<!-- UsageSnippet language="ruby" operationID="updatePetWithForm" method="post" path="/pet/{petId}" -->
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

res = s.pet.update_pet_with_form(pet_id: 509_712)

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                                                                                              | Type                                                                                                                   | Required                                                                                                               | Description                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `pet_id`                                                                                                               | *::Integer*                                                                                                            | :heavy_check_mark:                                                                                                     | ID of pet that needs to be updated                                                                                     |
| `request_body`                                                                                                         | [T.nilable(Models::Operations::UpdatePetWithFormRequestBody)](../../models/operations/updatepetwithformrequestbody.md) | :heavy_minus_sign:                                                                                                     | N/A                                                                                                                    |

### Response

**[T.nilable(Models::Operations::UpdatePetWithFormResponse)](../../models/operations/updatepetwithformresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## delete_pet

Deletes a pet

### Example Usage

<!-- UsageSnippet language="ruby" operationID="deletePet" method="delete" path="/pet/{petId}" -->
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

res = s.pet.delete_pet(pet_id: 818_965)

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter             | Type                  | Required              | Description           |
| --------------------- | --------------------- | --------------------- | --------------------- |
| `pet_id`              | *::Integer*           | :heavy_check_mark:    | Pet id to delete      |
| `api_key`             | *T.nilable(::String)* | :heavy_minus_sign:    | N/A                   |

### Response

**[T.nilable(Models::Operations::DeletePetResponse)](../../models/operations/deletepetresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## upload_file

Uploads an image

### Example Usage

<!-- UsageSnippet language="ruby" operationID="uploadFile" method="post" path="/pet/{petId}/uploadImage" -->
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

res = s.pet.upload_file(pet_id: 150_516)

unless res.api_response.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                | Type                                                                                                     | Required                                                                                                 | Description                                                                                              |
| -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `pet_id`                                                                                                 | *::Integer*                                                                                              | :heavy_check_mark:                                                                                       | ID of pet to update                                                                                      |
| `request_body`                                                                                           | [T.nilable(Models::Operations::UploadFileRequestBody)](../../models/operations/uploadfilerequestbody.md) | :heavy_minus_sign:                                                                                       | N/A                                                                                                      |

### Response

**[T.nilable(Models::Operations::UploadFileResponse)](../../models/operations/uploadfileresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |