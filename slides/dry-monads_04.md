## Try monad

```ruby
require 'dry-monads'

module ExceptionalLand
  extend Dry::Monads::Try::Mixin

  res = Try() { 10 / 2 }
  res.value if res.success?
  # => 5
  # resは`Dry::Monads::Try::Success`のインスタンス

  res = Try() { 10 / 0 }
  res.exception if res.failure?
  # => #<ZeroDivisionError: divided by 0>
  # resは`Dry::Monads::Try::Failure`のインスタンス

  # デフォルトでは`StandardError`を継承している全てのクラスをキャッチするようになっている
  # 特定のクラスのみキャッチするよう指定する事も可能
  Try(NoMethodError, NotImplementedError) { 10 / 0 }
  # => raised ZeroDivisionError: divided by 0 exception
end
```
