# Elm
> http://elm-lang.org/

## CLI commands

### `elm-repl` 
> repl


### `elm-reactor` 
> to build apps like webpack does


### `elm-make` 
> to compile apps into HTML and JS

eg.
```sh
elm-make Main.elm --output=main.html
```

### `elm-package`
> like npm for elm

#### notable commands

- `install`: install the dependencies in elm-package.json
- `publish`: publish your library to the Elm Package Catalog
- `bump`: bump version numbers based on API changes
- `diff`: get the difference between two APIs

## Core language

### strings
```elm
"hello" -- "hello"
"hello" ++ "world" -- "helloworld"
```

### number
```elm
10/3 -- 3.33333  (float)
10//3 -- 3 (Int)
```

### functions
```elm
 isNegative n = n < 0
 
 isNegative 4 -- False
```

### conditionals
```elm
if True then "hello" else "world" -- True
```

### lists
> Arrays of the same type

```elm
names = [ "Alice", "Bob", "Chuck" ]
```

#### List methods
- `List.isEmtpy`
- `List.length`
- `List.sort`
- `List.map`

### Tuples

> Array of fixed number of values with any type.

```elm
(True, "name accepted!")
```

## Work flow
> Redux works similar like Elm. 

- Model (Redux store)
- Msg (Redux action)
- Update (Redux reducer)





