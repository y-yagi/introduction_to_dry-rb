## dry-transaction

後はtransactionの`#call`を呼び出して処理を行う

```ruby
DB = []
save_user.call("name" => "Jane", "email" => "jane@doe.com")
# => Right({:name=>"Jane", :email=>"jane@doe.com"})

save_user.call("name" => "Jane")
# => Left(:not_valid)
```
`Dry::Monads::Right`はsuccess、`Dry::Monads::Left`はfailure
