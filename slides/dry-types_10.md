## Enum

enumもあるよ

```ruby
class Book < Dry::Types::Struct
  Statuses = Types::Strict::String.enum('draft', 'published', 'archived')

  attribute :id, Types::Maybe::Coercible::Int
  attribute :status, Statuses
end
puts Book.new(id: 1, status: 'published').status   # => published
puts Book.new(id: 1, status: 1).status             # => published

puts Book.new(id: 1, status: 'out').status
# => [Book.new] "out" (String) has invalid type for :status (Dry::Types::StructError)
```
