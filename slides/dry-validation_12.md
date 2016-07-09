## Schemas

schemaを再利用する事も可能

```ruby
AddressSchema = Dry::Validation.Schema do
  required(:street).filled
  required(:city).filled
  required(:zipcode).filled
end

UserSchema = Dry::Validation.Schema do
  required(:email).filled
  required(:name).filled
  required(:address).schema(AddressSchema)
end
```
