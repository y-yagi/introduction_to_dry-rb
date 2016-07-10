## Built-in Types(Form)

```ruby
class Book < Dry::Types::Struct
  attribute :published, Types::Bool
end

puts Book.new(published: '1').published
# => [Book.new] "1" (String) has invalid type for :published (Dry::Types::StructError)
```

```ruby
class Book < Dry::Types::Struct
  attribute :published, Types::Form::Bool
end

puts Book.new(published: '1').published  #=> true
puts Book.new(id: 1, status: nil, published: 'yes').published #=> true
```

* "1 on On ON t true True TRUE  y yes Yes YES"はtrueとして扱われる
* "0 off Off OFF f false False FALSE n no No NO"はfalseとして扱われる
* Stringのintやfloatへの変換をデフォルトで行ってくれる
