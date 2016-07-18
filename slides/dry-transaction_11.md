## Step adapters

```ruby
save_user = Dry.Transaction(container: Container) do
  map :process
  try :validate, catch: ValidationError
  tee :persist
end
```

独自のstepを作成する事も出来る(Custom step adapters)
