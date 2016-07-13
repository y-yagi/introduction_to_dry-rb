## dry-logic

```ruby
require 'dry/logic'
require 'dry/logic/predicates'

include Dry::Logic

user_present = Rule::Key.new(Predicates[:filled?], name: :user)
has_min_age = Rule::Key.new(Predicates[:int?], name: [:user, :age]) & Rule::Key.new(Predicates[:gt?].curry(18), name: [:user, :age])

user_rule = user_present & has_min_age

user_rule.call(user: { age: 19 }).inspect
# => #<Dry::Logic::Result::Named success?=true input=18 rule=#<Dry::Logic::Rule::Key predicate=#<Dry::Logic::Predicate::Curried id=:gt? args=[18]> options={:evaluator=>#<Dry::Logic::Evaluator::Key path=[:user, :age]>, :name=>[:user, :age]}>>

user_rule.call(user: { age: 18 }).inspect
# => #<Dry::Logic::Result::Named success?=false input=18 rule=#<Dry::Logic::Rule::Key predicate=#<Dry::Logic::Predicate::Curried id=:gt? args=[18, 18]> options={:evaluator=>#<Dry::Logic::Evaluator::Key path=[:user, :age]>, :name=>[:user, :age]}>>

user_rule.call(user: { age: 'seventeen' }).inspect
# => #<Dry::Logic::Result::Named success?=false input="seventeen" rule=#<Dry::Logic::Rule::Key predicate=#<Dry::Logic::Predicate::Curried id=:int? args=["seventeen"]> options={:evaluator=>#<Dry::Logic::Evaluator::Key path=[:user, :age]>, :name=>[:user, :age]}>>

user_rule.call(user: { }).inspect
# => #<Dry::Logic::Result::Named success?=false input={} rule=#<Dry::Logic::Rule::Key predicate=#<Dry::Logic::Predicate::Curried id=:filled? args=[{}]> options={:evaluator=>#<Dry::Logic::Evaluator::Key path=[:user]>, :name=>:user}>>
```
