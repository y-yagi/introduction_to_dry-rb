## Form Validation

* form params用のSchemaクラスが提供されている
* form用のschemaクラスは、HashのkeyがStringでも動作するようになっている

```ruby
schema = Dry::Validation.Form do
  required(:email).filled(:str?)

  required(:age).filled(:int?, gt?: 18)
end

errors = schema.call('email' => '', 'age' => '18').messages
```
