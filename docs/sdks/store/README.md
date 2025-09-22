# Store
(*store*)

## Overview

Access to Petstore orders

### Available Operations

* [get_inventory](#get_inventory) - Returns pet inventories by status
* [place_order](#place_order) - Place an order for a pet
* [get_order_by_id](#get_order_by_id) - Find purchase order by ID
* [delete_order](#delete_order) - Delete purchase order by ID

## get_inventory

Returns a map of status codes to quantities

### Example Usage

<!-- UsageSnippet language="ruby" operationID="getInventory" method="get" path="/store/inventory" -->
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new

res = s.store.get_inventory(security: Models::Operations::GetInventorySecurity.new(
    api_key: '<YOUR_API_KEY_HERE>',
  ))

unless res.object.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                   | Type                                                                                        | Required                                                                                    | Description                                                                                 |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| `security`                                                                                  | [Models::Operations::GetInventorySecurity](../../models/operations/getinventorysecurity.md) | :heavy_check_mark:                                                                          | The security requirements to use for the request.                                           |

### Response

**[T.nilable(Models::Operations::GetInventoryResponse)](../../models/operations/getinventoryresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## place_order

Place an order for a pet

### Example Usage

<!-- UsageSnippet language="ruby" operationID="placeOrder" method="post" path="/store/order" -->
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

req = Models::Components::Order.new()

res = s.store.place_order(request: req)

unless res.body.nil?
  # handle response
end

```

### Parameters

| Parameter                                                 | Type                                                      | Required                                                  | Description                                               |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| `request`                                                 | [Models::Components::Order](../../models/shared/order.md) | :heavy_check_mark:                                        | The request object to use for the request.                |

### Response

**[T.nilable(Models::Operations::PlaceOrderResponse)](../../models/operations/placeorderresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## get_order_by_id

For valid response try integer IDs with value >= 1 and <= 10. Other values will generated exceptions

### Example Usage

<!-- UsageSnippet language="ruby" operationID="getOrderById" method="get" path="/store/order/{orderId}" -->
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

res = s.store.get_order_by_id(order_id: 728_529)

unless res.body.nil?
  # handle response
end

```

### Parameters

| Parameter                          | Type                               | Required                           | Description                        |
| ---------------------------------- | ---------------------------------- | ---------------------------------- | ---------------------------------- |
| `order_id`                         | *::Integer*                        | :heavy_check_mark:                 | ID of pet that needs to be fetched |

### Response

**[T.nilable(Models::Operations::GetOrderByIdResponse)](../../models/operations/getorderbyidresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## delete_order

For valid response try integer IDs with positive integer value. Negative or non-integer values will generate API errors

### Example Usage

<!-- UsageSnippet language="ruby" operationID="deleteOrder" method="delete" path="/store/order/{orderId}" -->
```ruby
require 'openapi'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Openapi.new(
      petstore_auth: '<YOUR_PETSTORE_AUTH_HERE>',
    )

res = s.store.delete_order(order_id: 690_575)

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                | Type                                     | Required                                 | Description                              |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| `order_id`                               | *::Integer*                              | :heavy_check_mark:                       | ID of the order that needs to be deleted |

### Response

**[T.nilable(Models::Operations::DeleteOrderResponse)](../../models/operations/deleteorderresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |