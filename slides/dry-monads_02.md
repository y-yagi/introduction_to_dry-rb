## Maybe monad

```ruby
require 'dry-monads'
M = Dry::Monads
maybe_user = M.Maybe(user).bind do |u|
  M.Maybe(user.address).bind do |a|
    M.Maybe(a.street)
  end
end
puts maybe_user
# user + addressが存在する場合`Dry::Monads::Maybe::Some("Street Address")`
# どちらかがnilなら`Dry::Monads::Maybe::None`
```

上記は`#map`を使って下記のよう書く事も出来る

```ruby
Dry::Monads::Maybe(user).fmap(&:address).fmap(&:street)
```
