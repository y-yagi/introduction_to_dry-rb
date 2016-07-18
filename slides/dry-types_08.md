## Constraints

制約を設定する事も可能

```ruby
class Book < Dry::Types::Struct
  attribute :id, Types::Maybe::Coercible::Int
  attribute :name, Types::Coercible::String.constrained(min_size: 3, max_size: 9)
end
Book.new(id: 1, name: 'ab')
# => [Book.new] "ab" (String) has invalid type for :name (Dry::Types::StructError)
```
制約には[dry\-logic](http://dry-rb.org/gems/dry-logic/)に登録されているルールを使用可能
