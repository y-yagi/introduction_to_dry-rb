## Step adapters

* `step`メソッドは`Either`オブジェクト返すoperationを指定する必要があるが、それ以外の値を返すoperationを登録する為のメソッドも用意されている
  * `map`: operationの実行結果をそのまま返す(`Right(output)`)
  * `try`: operationの中で指定したexceptionがraiseした場合、`Left(exception)`を返す。それ以外の場合は`Right(output)`を返す。
  * `tee`: operationの実行結果は一切チェックせず、入力値をそのまま返す(`Right(input)`)

