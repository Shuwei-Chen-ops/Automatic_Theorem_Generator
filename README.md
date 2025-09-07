
---

# Automated Theorem Generator

**User Manual**

---

## System Requirements

- **Operating System**: Windows 10 or later
    
- **Memory**: Minimum 4 GB RAM (8 GB or more recommended)
    
- **Storage**: At least 100 MB of available space
    

---

## Program Overview

The **Automated Theorem Generator** is a tool based on the _Contradiction Separation_.  
It automatically generates theorems from logical formulas provided by the user.  
The program features a graphical user interface, making it simple to operate and suitable for both research and teaching.

---

## Features

- **Formula Parsing**: Parses logical formulas such as `p(a)` or `~q(b)`.
    
- **Input Validation**: Checks whether inputs follow syntax and logical rules.
    
- **Theorem Generation**: Produces all possible permutations of the input formulas and generates theorems.
    
- **CNF Output**: Converts results into CNF (Conjunctive Normal Form) compliant with the TPTP format.
    
- **Paging and Browsing**: Allows navigation through theorems generated from different permutations.
    

---

## Input Rules

### Input Format

Formulas must follow first-order logic syntax:

```
Predicate(term1, term2, ...)
```

- Predicates must begin with a letter; letters, digits, and underscores are allowed.
    
- Terms can be variables (e.g., X, Y, Z) or constants (e.g., a, b, c).
    
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

1. **Unique Predicates**
    
    - Invalid: `p(a)` and `p(b)`
        
    - Valid: `p(a)` and `q(b)`
        
2. **No Complementary Pairs**
    
    - Invalid: `p(a)` and `~p(a)`
        
    - Valid: `p(a)` and `~q(b)`
        
3. **Consistent Arity**
    
    - Invalid: `f(a)` and `f(a, b)`
        
    - Valid: `f(a)` and `g(a, b)`
        
4. **No Unifiable Complements**
    
    - Invalid: `p(X)` and `~p(a)`
        
    - Valid: `p(X)` and `~q(Y)`
        

---

## How to Use

### Single Input Mode

1. Select **“Single Input”** (default).
    
2. Enter a formula in the input box (e.g., `p(a)`).
    
3. Press **Enter** to add more lines.
    
4. Validation status appears on the right:
    
    - ✅ Valid input
        
    - ❌ Invalid input
        

### Multiple Input Mode

1. Select **“Multiple Inputs”**.
    
2. Enter multiple formulas separated by semicolons, e.g.:
    
    ```
    p(a); ~q(b); r(f(X)); s(g(Y), Z)
    ```
    
3. The program automatically parses and validates all inputs.
    

### Generator Theorems

1. Ensure all inputs are valid (show ✅).
    
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
        

### Paging Modes

- **Standard Mode (≤ 10 formulas)**
    
    - Shows total pages
        
    - Full navigation supported
        
- **Large Input Mode (> 10 formulas)**
    
    - Displays total pages as “N/A”
        
    - Still supports forward/backward navigation
        
    - Pages generated on demand
        

### Navigation Notes

- On the first page, `<<` is disabled.
    
- In Standard Mode, on the last page, `>>` is disabled.
    
- In Large Input Mode, `>>` is always enabled.
    
- Invalid page numbers reset to the current page.
    

---

## FAQ

**Q: My input shows ❌ and no theorems are generated. What should I do?**

**A:**

- Check for correct syntax (parentheses, commas).
    
- Ensure rules (uniqueness, complementarity, consistency) are not violated.
    
- Refer to the error message, correct the input, and try again.
    

---
