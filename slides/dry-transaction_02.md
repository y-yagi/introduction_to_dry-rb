## dry-transaction

まず行いたいoperationを登録する為のcontainerを作成する

```ruby
require "dry-container"
require "dry-monads"

class Container
  extend Dry::Container::Mixin

  register :process, -> input {
    Dry::Monads.Right(name: input["name"], email: input["email"])
  }

  register :validate, -> input {
    input[:email].nil? ? Dry::Monads.Left(:not_valid) : Dry::Monads.Right(input)
  }

  register :persist, -> input {
    DB << input; Dry::Monads.Right(input)
  }
end
```
