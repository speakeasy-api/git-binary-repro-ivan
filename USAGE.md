<!-- Start SDK Example Usage [usage] -->
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