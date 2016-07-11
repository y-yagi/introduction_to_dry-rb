## Predicate Logic

```ruby
# Exclusive Disjunction (`xor`, `^`)
Dry::Validation.Schema do
  required(:eat_cookie).filled
  required(:have_cookie).filled

  rule(be_reasonable: [:eat_cookie, :have_cookie]) do |eat_cookie, have_cookie|
    eat_cookie.eql?('yes') ^ have_cookie.eql?('yes')
  end
end
```
