# Bolt Compiler Design

## Compiler Name

boltc

---

## Goal

The Bolt compiler reads `.bolt` source files, checks them for errors, and produces an executable program.

---

## Compiler Stages

1. Lexer
2. Parser
3. AST (Abstract Syntax Tree)
4. Semantic Analyzer
5. Optimizer (Future)
6. Code Generator

---

## Pipeline

.bolt Source File
        │
        ▼
Lexer
        │
        ▼
Parser
        │
        ▼
AST
        │
        ▼
Semantic Analyzer
        │
        ▼
Code Generator
        │
        ▼
Executable (.exe)

---

## Responsibilities

### Lexer

- Read characters
- Produce tokens

### Parser

- Check syntax
- Build the AST

### AST

- Represents the structure of the program

### Semantic Analyzer

- Check variable names
- Check types
- Detect invalid code

### Code Generator

- Produce executable machine code (future)
