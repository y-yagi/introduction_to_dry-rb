## dry-transaction

* `container`に`operation`を定義する
* `operation`は`#call(input)`が実装されている必要がある
* `operation`は`register`メソッドで登録出来る
* `Dry::Monads::Right`はsuccess、`Dry::Monads::Left`はfailure
