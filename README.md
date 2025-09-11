
---

# Automated Theorem Generator △1

**User Manual**

---

## System Requirements

- **Operating System**: Windows 10 or later
    
- **Memory**: Minimum 4 GB RAM (8 GB or more recommended)
    
- **Storage**: At least 100 MB of available space
    

---

## Program Overview

The **Automated Theorem Generator** is a tool based on the _Triangle Standard Contradiction Separation_.  
It automatically generates theorems from logical literals provided by the user.  
The program features a graphical user interface, making it simple to operate and suitable for both research and teaching.

---

## Features

- **Literal Parsing**: Parses logical literals such as `p(a)` or `~q(b)`.
    
- **Input Validation**: Checks whether inputs follow syntax and logical rules.
    
- **Theorem Generation**: Produces of the input literals and generates theorems.
    
- **CNF Output**: Converts results into CNF (Conjunctive Normal Form) compliant with the TPTP format.
    
- **Paging and Browsing**: Allows navigation through theorems generated.
    

---

## Input Rules

### Input Format

Formulas must follow propositional logic and first-order logic syntax:

```
Predicate(term1, term2, ...)
```

- Predicates must begin with a letter; letters, digits, and underscores are allowed.
    
- The terms can be constants (e.g., a, b, c) or variables (e.g., X, Y, Z) or function terms (e.g., f(X,Y),g(X,Y,Z,U)).
    
- Negation is supported: prefix the predicate with `~` (e.g., `~p(a)`).
    
- Compound terms are supported (e.g., `f(a)`, `g(X, Y)`).
    

### Examples

```
p(a)
~q(b)
r(f(X))
s(g(a), h(b, c))
~t(f(g(X), Y), Z)
```

### Validation Rules

1. **No Identical Predicate Symbols**
    
    - Invalid: `p(a)` and `p(b)`
        
    - Valid: `p(a)` and `q(b)`
        
2. **No Complementary Predicate Symbols**
    
    - Invalid: `p(a)` and `~p(a)`
        
    - Valid: `p(a)` and `~q(b)`
        
3. **Functions with Consistent Metricity**
    
    - Invalid: `f(a)` and `f(a, b)`
        
    - Valid: `f(a)` and `g(a, b)`
        
---

## How to Use

### Literal Input

1. Select **“Literal Input”**.
    
2. Enter multiple literals separated by semicolons, e.g.:
    
    ```
    p(a); ~q(b); r(f(X)); s(g(Y), Z)
    ```
    
3. The program automatically parses and validates all inputs.
    

### Generator Theorems

1. Ensure all inputs are valid.
    
2. Click **“Generator”**.
    
3. The program produces theorems and outputs CNF clauses.
    
4. Browse results using the paging controls.
    

---

## Paging and Navigation

### Paging Controls

Located at the bottom of the interface:

- **Total Pages**: Displays “Theorem Total: X” (shows “N/A” if input > 10 formulas).
    
- **Page Number Box**: Displays current page; users can enter a number to jump.
    
- **Buttons**:
    
    - `<<` Previous page
        
    - `>>` Next page
        
---

## FAQ

**Q: My input shows ❌ and no theorems are generated. What should I do?**

**A:**

- Check for correct syntax (parentheses, commas).
    
- Ensure rules (no identical predicate symbols, no complementary predicate symbols, same number of variants for function symbols with the same name) are not violated.
    
- Refer to the error message, correct the input, and try again.
    

---
