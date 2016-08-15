# Binding, Equivalence, and Names

Our syntax has two binding operators: colon ( `:` ), and equals ( `=` ). By convention, colon is used within objects, and equals is used outside of objects. Either way, binding works the same: binding asserts that the left hand side of the operator is equivalent to the right hand side. This is distinct from assignment, which is not a concept in Eve (therefore, we have no need for an `==` operator).

Names are another way to say one thing is equivalent to another; within a block, variables with the same name represent the same object or attribute of an object. For instance:

```
People who are 50 years old
  [tag: "person" age]
  age = 50

The same query as above
  [#person age: 50]

Never true
  [#person age: 10]
  person.age = 20
```

Names are a little more permissive in our syntax than other languages. We allow most symbols in a name (with the exception of space, @, #, //, period, question, comma, colon, and grouping symbols). So operators like `-` and `+` are valid symbols in a name. Furthermore, we support Unicode, so you can include symbols (such as letters from the Greek alphabet). Such permissive naming comes at the cost of requiring whitespace in expressions. For example `friend-age` is a name, whereas `friend - age` is subtracting `age` from `friend`.