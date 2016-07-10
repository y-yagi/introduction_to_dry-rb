## Array

```ruby
class Book < Dry::Types::Struct
  attribute :id, Types::Maybe::Coercible::Int
  attribute :comments, Types::Strict::Array.member(Types::Strict::String)
end
Book.new(id: 1, comments: [1])
#=> [Book.new] "ab" (String) has invalid type for :comments (Dry::Types::StructError)
```
