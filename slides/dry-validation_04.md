## Predicate Logic

validateのルールにはPredicate Logicが使える

```ruby
# Conjunction(`and`, `&`)
Dry::Validation.Schema do
  required(:age) { int? & gt?(18) }
end
```

```ruby
# Disjunction (`or`, `|`)
Dry::Validation.Schema do
  # `none?`は値がnilかどうかチェックする。以下の場合、値がnil or integerならOK
  required(:age) { none? | int? }
end
```

```ruby
# Implication (`then`, `>`)
Dry::Validation.Schema do
  # `filled?`がfalseを返す、又は両方の述語がtrueになるならOK
  required(:age) { filled? > int? }
end
```
