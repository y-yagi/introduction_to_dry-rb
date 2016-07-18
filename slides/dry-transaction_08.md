## dry-transaction

`#call`にブロックを渡して、結果毎に処理を行う事も出来る

```ruby
save_user.call("name" => "Jane", "email" => "jane@doe.com") do |m|
  m.success do |value|
    puts "Succeeded!"
  end

  m.failure :validate do |error|
    # `validate`ステップで失敗
    puts "Please provide a valid user."
  end

  m.failure do |error|
    # 何処かのステップで失敗
    puts "Couldn’t save this user."
  end
end

```
