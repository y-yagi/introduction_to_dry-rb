## Schemas

validationのルールを定義したオブジェクト

```ruby
schema = Dry::Validation.Schema do
  required(:email).filled
  required(:age).filled
end

result = schema.call(email: 'jane@doe.org', age: 21)

# Validationを行った後の値を出力する
result.output
# => {:email=>'jane@doe.org', :age=>21}

# すべてのルールにパスしたかどうか
result.success?  # => true

# ルールに失敗したかどうか
result.failure?  # => false
```

