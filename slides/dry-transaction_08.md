## dry-transaction

各stepに引数を渡す事も可能

```ruby
DB = []

class Container
  extend Dry::Container::Mixin

  register :process, -> input {
    Dry::Monads.Right(name: input["name"], email: input["email"])
  }

  register :validate, -> allowed, input {
    input[:email].include?(allowed) ? Dry::Monads.Left(:not_valid) : Dry::Monads.Right(input)
  }

  register :persist, -> input {
    DB << input; Dry::Monads.Right(input)
  }
end

save_user = Dry.Transaction(container: Container) do
  step :process
  step :validate
  step :persist
end

input = {"name" => "Jane", "email" => "jane@doe.com"}
save_user.call(input, validate: ["doe.com"])
# => Right({:name=>"Jane", :email=>"jane@doe.com"})

save_user.call(input, validate: ["smith.com"])
# => Left(:not_valid)
```
