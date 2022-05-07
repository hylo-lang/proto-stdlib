A drawback of the pattern `collection.with_first(...)` is that it requires two definitions of `with_first`: a non-mutating and a mutating one.

---

One must be careful when returning a union type.
```
fun id(_ x: sink Maybe<Int>)) -> Maybe<Int> {
  match sink x {
    () => { () } // better expressed as `let this: () => { this }`
    sink let some => { some }
  }
}
```
Returning `()` instead of `self` creates a new existential.

---

Methods like `union` or `merge` require an efficient way to consume the operand.

---

I wonder whether it's better to define transformations on linked list as conuming or mutating.

---

Using `for_each` might be more efficient than iterating over a collection with indices, because we do not need to test bounds at each iteration.

--- 

We can't define default implementations of consuming methods.
Besides, it's not clear what we need to do in a consuming method to prepare the object's destruction.
