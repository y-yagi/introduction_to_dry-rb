## エラーメッセージ

* エラーメッセージはyamlに定義した値を使用する事が出来る

```ruby
schema = Dry::Validation.Schema do
  configure { config.messages_file = '/path/to/my/errors.yml' }
end
```

```yml
en:
  errors:
    size?:
      arg:
        default: "size must be %{num}"
        range: "size must be within %{left} - %{right}"

      value:
        string:
          arg:
            default: "length must be %{num}"
```
