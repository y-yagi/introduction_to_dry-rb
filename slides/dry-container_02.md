## dry-container

```ruby
container = Dry::Container.new
container.register(:parrot) { |a| puts a }

parrot = container.resolve(:parrot)
parrot.call("Hello World")
# Hello World
# => nil
```
`register`で処理を登録し、`resolve`でその処理を取り出す
