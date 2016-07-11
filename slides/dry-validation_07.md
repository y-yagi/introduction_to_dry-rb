## Custom Predicates

独自のPredicateを作成する事も可能

```ruby
schema = Dry::Validation.Schema do
  configure do
    def email?(value)
      ! /magical-regex-that-matches-emails/.match(value).nil?
    end
  end

  required(:email).filled(:str?, :email?)
end
```
