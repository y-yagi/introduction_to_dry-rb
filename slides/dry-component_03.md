## dry-component

auto-registration機能もある

```ruby
require 'dry/component/container'

class Application < Dry::Component::Container
  configure do |config|
    config.root = Pathname.new('app')
    config.auto_register = 'lib'
  end

  load_paths!('lib')
end
```

```ruby
# app/lib/my_logger.rb
class MyLogger
  # some neat logger implementation
end
```

```ruby
# containerを`finalize`する事で、auto-registrationを実行する
Application.finalize!
Application['my_logger']
```
