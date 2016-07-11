## エラーメッセージ

* i18nもサポートしている

```
require 'i18n'
require 'dry-validation'

schema = Dry::Validation.Schema do
  configure { config.messages = :i18n }
  required(:email).filled
end

puts schema.call(email: '').messages(locale: :pl)
# => { :email => ["musi być wypełniony"] }
```

