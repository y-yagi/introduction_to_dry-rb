## dry-validation

```ruby
puts schema.call(
  name: 'Jane',
  email: 'jane@doe.org',
  address: { street: 'Street 1', city: 'NYC', zipcode: '1234' }
).inspect
# => #<Dry::Validation::Result output={:name=>"Jane", :email=>"jane@doe.org", :address=>{:street=>"Street 1", :city=>"NYC", :zipcode=>"1234"}} messages={:age=>["is missing"]}>
```

modelにvalidationを指定するのではなく、validation object(schema)を作成し、そこにvalidateしたい値を渡す
