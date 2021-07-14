# Rust - Learning

# Getting started
1. Download rustup from the [Rust website](https://www.rust-lang.org/tools/install).
2. Run the exe. Follow the simple on-screen instructions for a quick install.
3. Rust is installed! Open a new visual studio code project.
4. Type `cargo new [project name]`, rust will automatically **create** a project folder and the needed files to run a rust project. *(You won't need to create the folder yourself.*
5. It will provide you by default, with a hello world program. cd into the new directory and type cargo run to build and test the new project.

# Variables
## Initialising a variable
To initialise a variable, use the `let` keyword.
```rust
let x = 45
```
## Mutability
By default, this variable is also known as **immutable** *(it can't be changed)*. If you were to run `x = 20`, you would get an error.
To change this, we use the `mut` keyword.
```rust
let mut x = 45
```
This makes the variable **mutable**, so is able to be changed.
## Integer Types
```rust 
let x = 2
```
As the default in Rust, this code will create a **signed 32-bit integer**.
In order to change the integer type, use a colon `(:)` after the variable name.
For example:
```rust
let x:u64 = 123
```
This code will create an **unsigned 64-bit integer**.
|Length|Signed|Unsigned|
|------|------|--------|
|8-bit|`i8`|`u8`|
|16-bit|`i16`|`u16`|
|32-bit|`i32`|`u32`|
|64-bit|`i64`|`u64`|
|128-bit|`i128`|`u128`|

***Note, for floats it is the same syntax, replace `i`/`u` with `f`***
## More on Initialising Varaibles
It is always good practice in Rust to show the data type for each variable. Although it is not always necessary. For example:
```rust
let IsOpen = true
```
Will work fine, however it is always good practice to define it like this instead:
```rust
let ISOpen:bool = true
```
This will help with anybody reading your code, and in a big project will help. Although not necessary, recommended.

# Loops
## The `loop` Keyword
The loop keyword will perform an infinite loop in rust.
Usage:
```rust
loop {
    println!("This will be printed indefinitely");
}
```
In order to stop the loop, you must use the `break` keyword, which will *break* out of the loop.
```rust
let mut a = 0;
loop {
    a += 1;
    if a > 9{
        break;
    }

    println!("This will loop until a is 10, then it will break out of the loop");
}
```

## For Loops
For loops work similarly to any other language.
```rust
// 1..11 - known as an 'iterator'.
for i in 1..11{
    println!("{}",i);
}
```
This will return numbers 1 - 10.
### Vectors
You can use for loops to loop through vectors.
```rust
let animals = vec!["Rabbit","Dog","Cat"];
for animal in animals.iter(){
    println!("The animal name is {}", animal);
}
```
We call the `.iter()` method on animals to prevents the ownership of the values inside the vector being moved to the for loop. Without the `.iter()` method, you won't be able to access the animals variable after the for loop. So always use `.iter()` with vectors.

### For loop Index
```rust
    let animals = vec!["Rabbit","Dog","Cat"];
    for (index, animal) in animals.iter().enumerate(){
        println!("The index is {}. The animal name is {}",index, animal);
    }
```
The `.enumerate()` method at the end of the expression will allow us to pass a `"tuple"` to have two variables in the for loop `(index, animal)`.
We can now use `index` inside the for loop to find our index.

# Enums



# Projects
## 1. [hello-world](hello-world/)