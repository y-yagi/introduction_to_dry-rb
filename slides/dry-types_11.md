## Value Object

Value Objectも作れる

```ruby
class Location < Dry::Types::Value
  attribute :lat, Types::Strict::Float
  attribute :lng, Types::Strict::Float
end

loc1 = Location.new(lat: 1.23, lng: 4.56)
loc2 = Location.new(lat: 1.23, lng: 4.56)

loc1 == loc2
```
`Dry::Types::Struct`と同じ振る舞い + equality methodが追加されている
