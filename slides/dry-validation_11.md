## Schemas

独自のschemaクラスを定義する事も出来る

```ruby
class AppSchema < Dry::Validation::Schema
  configure do |config|
    config.messages_file = '/my/app/config/locales/en.yml'
    config.messages = :i18n
  end

  def email?(value)
    true
  end

  define! do
    # 共通のルールを定義
  end
end

Dry::Validation.Schema(AppSchema) do
end
```
