## dry-transaction

* 複数のビジネスロジックを一つの塊(container)として扱う
* 塊として扱う事により、テストがしやすくなる、かつ再利用が可能となる(はず)
* 戻り値は`Right` or `Left`のみを扱う事により、エラーハンドリングをシンプルに行えるようにする
