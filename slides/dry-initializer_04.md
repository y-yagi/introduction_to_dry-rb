## dry-initializer

`param` or `option`に指定してない値を指定しようとすると`ArgumentError`

```ruby
class User
  extend Dry::Initializer::Mixin
end
user = User.new email: 'joe@example.com' # raises ArgumentError
```

値を無視(エラーを起こさない)したい場合は、`tolerant_to_unknown_options`を使用すればOK

```ruby
class User
  extend Dry::Initializer::Mixin
  tolerant_to_unknown_options
end
user = User.new email: 'joe@example.com'
# => <User >
```
