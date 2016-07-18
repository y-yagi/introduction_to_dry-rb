## dry-auto_inject

```ruby
require 'dry-container'
require 'dry-auto_inject'

class DataStore
  attr_accessor :users

  def initialize
    @users = []
  end
end

my_container = Dry::Container.new

# containerにoperationを登録
my_container.register("data_store", -> { DataStore.new })
my_container.register("user_repository", -> { my_container["data_store"].users })
my_container.register("persist_user", -> { PersistUser.new })

# auto-injectionのセットアップ(Dry::AutoInject::Builderを作成している)
AutoInject = Dry::AutoInject(my_container)

# injectionをmixinする. これにより`PersistUser`クラスからcontainerのoperationを呼び出す事が出来るようになる.
class PersistUser
  include AutoInject["user_repository"]

  def call(user)
    user_repository << user
  end
end

persist_user = my_container["persist_user"]
persist_user.call(name: 'Jane')
```
