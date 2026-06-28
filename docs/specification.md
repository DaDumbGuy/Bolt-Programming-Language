Bolt Programming Language Specification

Version: 0.1.0 (Draft)

1. Introduction

Bolt is a programming language built completely from scratch for game development.

Bolt does not copy the syntax of existing programming languages. Every keyword, operator, command, and language rule is designed specifically for Bolt.

The goals of Bolt are:

Original syntax
Easy to read
Beginner friendly
High performance
Built for games
Consistent design

2. Language Philosophy

Bolt follows five principles:

Originality

Every feature should be designed for Bolt instead of copied from another language.

Readability

Programs should be easy for humans to read.

Simplicity

Common tasks should require as little code as possible.

Consistency

Similar language features should follow similar rules.

Performance

Bolt should eventually compile into fast native applications.

3. Official Decisions

Language Name

Bolt

File Extension

.bolt

Compiler

boltc

Current Version

0.1.0 Draft

Current Status

Language Design Phase

4. Reserved Keywords

No keywords have been officially approved yet.

They will be added after community discussion and design.

5. Data Types

Bolt uses a hybrid type system.

By default, Bolt automatically determines the data type of a variable (type inference). Developers may also explicitly specify a data type when greater control or readability is desired.

### Built-in Data Types

| Type    | Purpose                           |
| ------- | --------------------------------- |
| `ember` | Whole numbers                     |
| `surge` | Decimal numbers                   |
| `glyph` | Text                              |
| `truth` | Boolean values (`true` / `false`) |
| `vault` | Collection of values              |
| `form`  | User-defined object or type       |
| `empty` | Represents no value               |

### Examples

Automatic type inference:

```bolt
forge health = 100
forge speed = 5.5
forge player = "Alex"
forge alive = true
```

Explicit typing:

```bolt
forge health : ember = 100
forge speed : surge = 5.5
forge player : glyph = "Alex"
forge alive : truth = true
```


6. Variables


Variables store data that can be used and modified throughout a program.

### Keyword

| Keyword | Purpose                 |
| ------- | ----------------------- |
| `forge` | Declares a new variable |

### Variable Declaration

Bolt supports both **type inference** and **explicit typing**.

#### Type Inference

The compiler automatically determines the variable's type.

```bolt
forge health = 100
forge speed = 5.5
forge playerName = "Alex"
forge alive = true
```

#### Explicit Typing

The programmer may explicitly specify the variable's type.

```bolt
forge health : ember = 100
forge speed : surge = 5.5
forge playerName : glyph = "Alex"
forge alive : truth = true
```

### Variable Naming Rules

* Names must begin with a letter (`A-Z` or `a-z`) or an underscore (`_`).
* Names may contain letters, numbers, and underscores.
* Keywords cannot be used as variable names.
* Variable names are case-sensitive.

### Reassigning Variables

A variable's value can be changed after it has been created.

```bolt
forge score = 0

score = 10
score = score + 5
```

### Examples

```bolt
forge playerHealth = 100
forge playerSpeed = 6.5
forge playerName = "Bolt"
forge gameRunning = true
```


7. Operators

Bolt supports three categories of operators.

### Arithmetic Operators

| Operator | Description        |
| -------- | ------------------ |
| `+`      | Addition           |
| `-`      | Subtraction        |
| `*`      | Multiplication     |
| `/`      | Division           |
| `%`      | Remainder (Modulo) |
| `^`      | Power              |

Example:

```bolt
forge total = 10 + 5
forge speed = 20 / 2
forge area = 5 ^ 2
```

---

### Comparison Operators

| Operator | Description              |
| -------- | ------------------------ |
| `==`     | Equal to                 |
| `!=`     | Not equal to             |
| `>`      | Greater than             |
| `<`      | Less than                |
| `>=`     | Greater than or equal to |
| `<=`     | Less than or equal to    |

Example:

```bolt
health == 100
score >= 50
```

---

### Logical Operators

| Operator | Description |   |            |
| -------- | ----------- | - | ---------- |
| `&&`     | Logical AND |   |            |
| `        |             | ` | Logical OR |
| `!`      | Logical NOT |   |            |

Example:

```bolt
alive && hasKey
!gameOver
```

 8. Conditions

Bolt uses a natural-language inspired conditional system.

### Keywords

| Keyword     | Purpose                                             |
| ----------- | --------------------------------------------------- |
| `when`      | Starts a conditional block                          |
| `otherwise` | Checks another condition if the previous one failed |
| `finally`   | Executes when no previous conditions are true       |

### Syntax

```bolt
when health <= 0

    echo "Game Over"

otherwise health < 50

    echo "Low Health"

finally
    echo "Healthy"

finish
```

### Rules

* Every conditional block begins with `when`.
* Additional conditions use `otherwise`.
* The final fallback uses `finally`.
* Every conditional block ends with `finish`.


9. Loops


Loops allow code to repeat until a condition is met or for a specific number of times.

### Keywords

| Keyword  | Purpose  |
| -------- | -------- |
| `repeat` | Repeat a |



10. Functions

Functions allow reusable blocks of code.

### Keyword

| Keyword | Purpose             |
| ------- | ------------------- |
| `spark` | Declares a function |

### Syntax

```bolt
spark greet(name)

    echo "Hello " + name

finish
```

Calling a function:

```bolt
greet("Alex")
```

### Returning Values

Functions return values using the `return` keyword.

```bolt
spark add(a, b)

    return a + b

finish
```

Example:

```bolt
forge result = add(5, 10)
echo result
```


11. Objects

Objects group related data and behavior into a single reusable type.

### Keyword

| Keyword | Purpose                    |
| ------- | -------------------------- |
| `craft` | Declares a new object type |

### Syntax

```bolt
craft Player

    forge health = 100
    forge speed = 5

    spark jump(force)

        echo "Jumping with " + force

    finish

finish
```

### Creating an Object

Objects are created using the `forge` keyword.

```bolt
forge hero = Player()
```

### Accessing Members

Use the dot (`.`) operator to access properties and methods.

```bolt
hero.health = 80
hero.jump(15)
```

### Rules

* Every object begins with `craft`.
* Objects may contain variables and functions.
* Objects end with `finish`.
* Objects may be instantiated using `forge`.


12. Modules

Modules allow programs to be split across multiple files.

### Keyword

| Keyword | Purpose |
|---------|---------|
| `link` | Imports another Bolt source file |

### Syntax

```bolt
link "player.bolt"
link "enemy.bolt"
link "world.bolt"
```

### Rules

- `link` must appear before program execution begins.
- Paths are relative to the current file.
- A module is loaded only once.

13. Error Handling

Bolt provides structured error handling to prevent programs from crashing unexpectedly.

### Keywords

| Keyword   | Purpose                                              |
| --------- | ---------------------------------------------------- |
| `attempt` | Begins a block that may produce an error             |
| `rescue`  | Handles any error that occurs in the `attempt` block |
| `always`  | Executes whether an error occurs or not              |
| `throw`   | Raises a custom error                                |

### Syntax

```bolt
attempt

    link "save.bolt"
    loadGame()

rescue

    echo "Failed to load the save file."

always

    echo "Continuing program..."

finish
```

### Throwing an Error

```bolt
throw "PlayerNotFound"
```

### Rules

* Every `attempt` block must end with `finish`.
* `rescue` is optional.
* `always` is optional.
* `always` executes regardless of whether an error occurs.
* A `throw` statement immediately exits the current `attempt` block.


14. Standard Library

Bolt includes a built-in standard library to provide common functionality without requiring external packages.

### Console

| Function  | Purpose           |
| --------- | ----------------- |
| `echo()`  | Display text      |
| `input()` | Read user input   |
| `clear()` | Clear the console |

### Math

| Function   | Purpose                     |
| ---------- | --------------------------- |
| `abs()`    | Absolute value              |
| `sqrt()`   | Square root                 |
| `pow()`    | Raise to a power            |
| `random()` | Generate a random number    |
| `clamp()`  | Restrict a value to a range |

### Strings

| Function   | Purpose               |
| ---------- | --------------------- |
| `length()` | Number of characters  |
| `upper()`  | Convert to uppercase  |
| `lower()`  | Convert to lowercase  |
| `split()`  | Split text into parts |
| `join()`   | Combine text          |

### Collections

| Function     | Purpose                         |
| ------------ | ------------------------------- |
| `push()`     | Add an element                  |
| `pop()`      | Remove the last element         |
| `size()`     | Number of elements              |
| `contains()` | Check whether an element exists |

### Files

| Function   | Purpose                |
| ---------- | ---------------------- |
| `read()`   | Read a file            |
| `write()`  | Write a file           |
| `exists()` | Check if a file exists |

### Time

| Function  | Purpose             |
| --------- | ------------------- |
| `time()`  | Current system time |
| `sleep()` | Pause execution     |

### Game Development (Planned)

Future versions of Bolt will include built-in support for:

* Graphics
* Audio
* Input
* Physics
* Networking
* UI
* Animation
* Cameras

