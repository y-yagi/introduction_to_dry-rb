## Default

```ruby
class Book < Dry::Types::Struct
  attribute :id, Types::Maybe::Coercible::Int
  attribute :status, Types::Coercible::String.default('draft')
end
puts Book.new(id: 1, status: nil).status #=> 'draft'
```
