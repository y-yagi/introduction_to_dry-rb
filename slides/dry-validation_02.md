## dry-validation

```ruby
EMAIL_REGEX = /.*@.*/

schema = Dry::Validation.Schema do
  required(:name).filled
  required(:email).filled(format?: EMAIL_REGEX)
  required(:age).maybe(:int?)

  required(:address).schema do
    required(:street).filled
    required(:city).filled
    required(:zipcode).filled
  end
end
```
各要素毎にルールを定義する
