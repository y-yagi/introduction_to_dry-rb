## 組込みのPredicates

```ruby
# none?
required(:sample).value(:none?)

# eql?
required(:sample).value(eql?: 1234)

# type?(`str?`, `int?`などショートハンドもある)
required(:sample).value(type?: Integer)
required(:sample).str?

# empty?
required(:sample).value(:empty?)

# filled?
required(:sample).value(:filled?)
```
他にも`gt?`、`gteq?`、`max_size?`などなど
