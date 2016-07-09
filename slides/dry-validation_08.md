## Macros

```ruby
# required
Dry::Validation.Schema do
  # `required(:age) { filled? & int? }` と同じ
  required(:age).filled(:int?)
end
```

```ruby
# maybe
Dry::Validation.Schema do
  # `required(:age) { none? | int? }`と同じ
  required(:age).maybe(:int?)
end
```

```ruby
# each
Dry::Validation.Schema do
  # `required(:tags) { array? { each { str? } } }`と同じ
  required(:tags).each(:str?)
end
```
