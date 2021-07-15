# Rust - Learning

- [Rust - Learning](#rust---learning)
- [Getting started](#getting-started)
- [Variables](#variables)
    - [Assigning a variable](#assigning-a-variable)
    - [Assigning multiple variables](#assigning-multiple-variables)
    - [Mutability](#mutability)
    - [Constants](#constants)
    - [Integer Types](#integer-types)
- [Strings](#strings)
    - [Get string length](#get-string-length)
    - [Push **character** onto string](#push-character-onto-string)
    - [Push onto string](#push-onto-string)
    - [Check if empty string](#check-if-empty-string)
    - [String .contains](#string-contains)
    - [String .replace](#string-replace)
- [Tuples](#tuples)
    - [Defining a tuple](#defining-a-tuple)
    - [Accessing tuple values](#accessing-tuple-values)
- [Arrays](#arrays)
    - [Defining an array](#defining-an-array)
    - [Accessing array values](#accessing-array-values)
    - [Changing/Re-Assigning array values](#changingre-assigning-array-values)
    - [Get array length](#get-array-length)
- [Loops](#loops)
    - [The `loop` Keyword](#the-loop-keyword)
    - [For Loops](#for-loops)
    - [Vectors](#vectors)
    - [Indexing](#indexing)
- [Projects](#projects)
  - [1. hello-world](#1-hello-world)

# Getting started
1. Download rustup from the [Rust website](https://www.rust-lang.org/tools/install).
2. Run the exe. Follow the simple on-screen instructions for a quick install.
3. Rust is installed! Open a new visual studio code project.
4. Type `cargo new [project name]`, rust will automatically **create** a project folder and the needed files to run a rust project. *(You won't need to create the folder yourself.*
5. It will provide you by default, with a hello world program. cd into the new directory and type cargo run to build and test the new project.


# Variables
### Assigning a variable
To initialise a variable, use the `let` keyword.
```rust
let x = 45
```
### Assigning multiple variables
```rust
let (x,y) = (23,34)
```
### Mutability
By default, this variable is also known as **immutable** *(it can't be changed)*. If you were to run `x = 20`, you would get an error.
To change this, we use the `mut` keyword.
```rust
let mut x = 45
```
This makes the variable **mutable**, so is able to be changed.
### Constants
To make a variable constant, use the `const` keyword.
```rust
const MAX_INT = 200;
```
### Integer Types
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


# Strings
There are two types of strings
1. Primitive string -> Immutable, fixed-length string in memory.
2. String -> Growable, heap-allocated

To initialise a primitive string, it is how you would expect.
```rust
let hello = "Hello"
```
To initialise a rust-type String:
```rust
let hello = String::from("Hello");
```
### Get string length
```rust
let hello = String::from("Hello");
println!("{}",hello.len()); // the .len method can be used on both primitive type strings and Rust-type strings.

Output: 5
```
### Push **character** onto string
```rust
let hello = String::from("Hello");
hello.push('w'); //single quotes + one char length
println!("{}",hello);

Output: Hellow
```
This will not work if you try to push a string. All of this below will give you an error:
```rust
let hello = String::from("Hello");
hello.push("w"); //double quotes
hello.push("world"); // double quotes + longer than 1 char
hello.push('wo'); // longer than 1 char
```
### Push onto string
To add an extra string onto another string, we use the `push_str` method.
```rust
let hello = String::from("Hello ");
hello.push_str("world");
println!("{}",hello);

Output: "Hello World"
```

### Check if empty string
To check if a string is empty, use the `is_empty()` method.
```rust
let hello = String::from("");
println!("{}",hello.is_empty());

Output: true
```

### String .contains
To check if a string contains a value, use the `contains()` method.
```rust
let hello = String::from("Hello");
println!("Does the string contain 'World': {}", hello.contains("World"));

Output: false
```

### String .replace 
To replace a string with something else, use the `replace()` method.
```rust
let hello = String::from("Hello World");
println!("Replace: {}", hello.replace("World","There"));

Output: "Hello There"
```

# Tuples
A tuple is basically a group of values that can be different types unlike arrays. They can have a maximum of 12 elements.
### Defining a tuple
To define a tuple, we use *brackets*`()`, unlike arrays with square brackets `[]`.
```rust
//Defining a tuple
let tuple = ("Philip","London",16);
// You can also specify the data types
let tuple: (&str,&str,i8) = ("Philip","London",16);
```
### Accessing tuple values
To access tuple values, we use a `.` after the variable name and use the index, which works similar to arrays and starts at 0. For example:
```rust
let tuple = ("Philip","London",16);
println!("{} is {} years old and from {}",tuple.0,tuple.2,tuple.1);

Output: Philip is 16 years old and from London
``` 

# Arrays
An array is a group of values that are of the same data type.
To define an array, we use square brackets `[]` both to determine the data type, length and elements of the array
### Defining an array
```rust
//i32 = Data Type
//5 = Array Length
//[1,2,3,4,5] = Array data
let numbers: [i32;5] = [1,2,3,4,5];
```
### Accessing array values
To access array values, it's like any other programming language, indexing starts at 0 and we use square brackets `[]` to access a singular element.
```rust
let numbers: [i32;5] = [1,2,3,4,5];
println!("{}",numbers[0]);

Output: 1
```

### Changing/Re-Assigning array values
In order to change the values of elements inside an array, firstly the array must be mutable, by default in rust variables are immutable. We use the `mut` keyboard to do this. To change a value, we access the element we want to change and use the equals sign (`=`) to re-assign it.
```rust
let mut numbers: [i32;5] = [1,2,3,4,5];
numbers[1] = 5;
println!("{}",numbers[1]);

Output: 5
```

### Get array length
To get the array length, use the `.len()` method.
```rust
let numbers: [i32;5] = [1,2,3,4,5];
println!("{}",numbers.len());

Output: 5;
```



# Loops
### The `loop` Keyword
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

### For Loops
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

### Indexing
```rust
let animals = vec!["Rabbit","Dog","Cat"];
for (index, animal) in animals.iter().enumerate(){
    println!("The index is {}. The animal name is {}",index, animal);
}
```
The `.enumerate()` method at the end of the expression will allow us to pass a `"tuple"` to have two variables in the for loop `(index, animal)`.
We can now use `index` inside the for loop to find our index.



# Projects
## 1. [hello-world](hello-world/)