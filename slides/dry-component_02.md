## dry-component

```ruby
class Application < Dry::Component::Container
  configure do |config|
    config.root = Pathname.new('./my/app')
  end
end

require 'logger'
Application.register('utils.logger', Logger.new($stdout))

Application['utils.logger']
```
