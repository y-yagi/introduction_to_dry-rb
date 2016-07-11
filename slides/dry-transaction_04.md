## dry-transaction

作成したcontainerを使用してtransactionを作成する

```ruby
save_user = Dry.Transaction(container: Container) do
  step :process
  step :validate
  step :persist
end
```

