## dry-initializer

さっきのコードは下記と同等

```ruby
class User
  attr_reader :name, :type, :admin

  def initialize(name, type = 'customer', admin: false)
    @name  = name
    @type  = type
    @admin = admin

    fail TypeError unless String === @name
  end
end
```
