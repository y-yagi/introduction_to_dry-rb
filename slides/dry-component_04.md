## dry-component

componentは`dry-container` + `dry-auto_inject`を使用しているので、作成したcontainerをクラスにinjectすることも可能

```ruby
class PostPublisher
  include Application::Inject['utils.logger']

  def call(post)
    # some stuff
    logger.debug("post published: #{post}")
  end
end
```
