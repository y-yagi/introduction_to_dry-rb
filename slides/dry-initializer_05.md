## dry-initializer

親クラスで定義したattributeは子クラスで使用可能

```ruby
require 'dry-initializer'

class User
  extend Dry::Initializer::Mixin

  param :name
end

class Employee < User
  param :position
end

employee = Employee.new('John', 'supercargo')
employee.name     # => 'John'
employee.position # => 'supercargo'
```
