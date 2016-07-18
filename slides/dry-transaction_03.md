## dry-transaction

* `container`に`operation`を定義する
* `operation`は`#call(input)`が実装されている必要がある
* `operation`は`register`メソッドで登録出来る
* `operation`はsuccessの場合は`Dry::Monads::Right`、failureの場合は`Dry::Monads::Left`をそれぞれ返すようにする
