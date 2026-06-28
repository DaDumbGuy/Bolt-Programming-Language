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

Not yet designed.

11. Objects

Not yet designed.

12. Modules

Not yet designed.

13. Error Handling

Not yet designed.

14. Standard Library

Not yet designed.
