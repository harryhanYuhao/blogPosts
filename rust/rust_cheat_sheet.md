# Rust CheatSheet 

## Loops 

Rust does not have C styled loops

```c
// c
for (int i = 0; i < 10; ++i) {
    printf("%d\n", i);
}
```

Instead, rust uses idiosyncratic iterators: 

```rust
// rust 
for i in 0..9 {
    println!("{}", i);
}
```

A vector can be iterated over using 

```rust 
let v = vec![1, 2, 3, 4, 5];
for i in &v {
    println!("{}", i);
}
```

To access the index of the vector, use `iter().enumerate()`

```rust 
let v = vec![1, 2, 3, 4, 5];
for (index, value) in v.iter().enumerate() {
    println!("{}: {}", index, value);
}
```

## Traits

```
#[derive(Debug)] // for enum, struct, not for traits
```

To implement debug traits for dynamic traits use 

```
use std::fmt;
impl fmt::Debug for dyn TraitName {
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
        write!(f, "a")
    }
}
```
