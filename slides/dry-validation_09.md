## Macros

```ruby
# when
Dry::Validation.Schema do
  # rule(email: [:login]) { |login| login.true?.then(value(:email).filled?) }
  required(:email).maybe

  required(:login).filled(:bool?).when(:true?) do
    value(:email).filled?
  end
end
```

```ruby
# confirmation
Dry::Validation.Schema do
  # rule(password_confirmation: [:password]) do |password|
  #   value(:password_confirmation).eql?(password) }
  # end
  required(:password).filled(min_size?: 12).confirmation
end
```

