## Built-in Types(Maybe)

```ruby
class Book < Dry::Types::Struct
  attribute :id, Types::Coercible::Int
end
puts Book.new(id: nil)
# => [Book.new] nil (NilClass) has invalid type for :id (Dry::Types::StructError)
```

```ruby
class Book < Dry::Types::Struct
  attribute :id, Types::Maybe::Coercible::Int
end
puts Book.new(id: nil).id
# => None(Dry::Monads::Maybe::None)
```

