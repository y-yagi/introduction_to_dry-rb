## Built-in Types(definition, strict, coercible)

```ruby
class Book < Dry::Types::Struct
  attribute :id, Types::Int
end
puts Book.new(id: '1').id #=> '1'
puts Book.new(id: 'a').id #=> 'a'
```

```ruby
class Book < Dry::Types::Struct
  attribute :id, Types::Strict::Int
end
puts Book.new(id: '1').id # [Book.new] "1" (String) has invalid type for :id (Dry::Types::StructError)
puts Book.new(id: '1').id # [Book.new] "a" (String) has invalid type for :id (Dry::Types::StructError)
```

```ruby
class Book < Dry::Types::Struct
  attribute :id, Types::Coercible::Int
end
puts Book.new(id: '1').id #=> '1'
puts Book.new(id: 'a').id #=> `Integer': invalid value for Integer(): "a" (ArgumentError)
```
