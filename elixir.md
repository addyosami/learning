# Elixir
* Basic Types

- - -
# TODO

* cheashet `iex`
* symbol table or atom table
- - -
# Q&A

* enums?
- - -

##### 1. Basic Types

###### 1.1. Numbers (`Integer` ++ `Float`)

`10/2` always return `Float`.  
`0x`: hexadecimal.
`0b`: binary.
`e`: exponent.
**no limit** upper `Integer`, just the **available of memory**.

###### 1.2. Atom
a **constant** where **its name** is also **its value**.
`:ok`, `:"this is also ok"`.
*atom* is used quite **extensively** in *Elixir*.
*atom* is **very memory efficient**. each *atom* is stored in the *atom table*. This means that comparing `:ok` or `:error` isn't actually comparing the **string** `ok` or `error`, but rather whatever **integer** that **maps to**. In that sense they're similar to *enums* in other langs.
`true` => `Data type: Atom`
`nil || false || :firstname || true` => `:firstname`

###### 1.3. String
*UTF-8 encoded*.
```
"Hello, " <> "Lee"
"string #{interpolation}"
```
`"Test #{[1,2,3]}"` => `<<84, 101, 115, 116, 32, 1, 2, 3>>`
What *Elixir* returned was a **group of ASCII char codes**, each code representing one of our letters, with the last three representing the three numbers we passed in.  
The **reason** it did this is because in *Elixir* `String` is actually `Binary`.

`Binary` is just a **sequence of bytes** defined with the `<<>>`
`¥ <> <<0>>`: trick to see the binary of a string (concanate with *null byte*).

###### 1.4. Tuple

**ordered collection**.
**typically**, *2,3,4* values. have more? => use `List` or `Map` instead.
*Elixir* data is **immutable**.
**common approach** to **returning** the **results & data**.

###### 1.5. List
###### 1.5.1. Keyword list
is *single-linked list*.
`options = [{:first, false}, {:last, true}]`: keyword list
`options[:first]`

###### Immutable

add a new value to the head of another list by these steps.
* create new value
* add a pointer for this new value and that pointer will point to the original list. (it doesn't copy the whole values of original list to the new list, just add a pointer).

the **variables** themself are **immutable**
*Elixir* **re-binding** the variable. the **data itself** is **immutable**, but it is **possible** to **re-bind** a variable to a **new data**.

###### 1.6. Map

* key **doesn't** have to be an `Atom` (`Keyword List`).
* only allow **one instance of each key** (`Keyword List` **doesn't**).
* more **efficient** than `Keyword List`.

`other_map.name`: can access **directly** like this if the key is `Atom`

with `Map`, we can **partial** pattern matching.
*1.2+*: `Map` can work **efficiently** with millions of keys. This is because of updates to the Erlang VM.







