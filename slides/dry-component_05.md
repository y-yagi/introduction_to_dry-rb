## dry-component

yamlの読み込み&ENV varによる使用する値の切り分けも可能

```yaml
# /my/app/config/application.yml
development:
  foo: 'bar'
```

```ruby
class Application < Dry::Component::Container
  configure('development') do |config|
    config.name = :application
    config.root = '/my/app'
  end
end

Application.options.foo # => "bar"
```
