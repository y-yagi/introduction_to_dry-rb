## dry-types

```ruby
require 'dry-types'

module Types
  include Dry::Types.module

  Email = String.constrained(format: /\A[\w+\-.]+@[a-z\d\-]+(\.[a-z]+)*\.[a-z]+\z/i)
  Age = Int.constrained(gt: 18)
end

class User < Dry::Types::Struct
  attribute :name, Types::String
  attribute :email, Types::Email
  attribute :age, Types::Age
end

User.new(name: 'tommy', email: 'tommy@example.com', age: 10)
# => [User.new] 10 (Fixnum) has invalid type for :age (Dry::Types::StructError)
```
