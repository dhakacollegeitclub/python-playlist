# Python Course – Lecture 3: Variables & the `print()` Function

> **Dhaka College IT Club – Python Course**
> Instructor: Md. Samiul Islam

---

## Table of Contents

1. [What Is a Variable?](#1-what-is-a-variable)
2. [Declaring Variables](#2-declaring-variables)
3. [Variable Naming Rules](#3-variable-naming-rules)
4. [Naming Conventions](#4-naming-conventions)
5. [Writing Comments](#5-writing-comments)
6. [How the `print()` Function Works](#6-how-the-print-function-works)
7. [Common Mistakes](#7-common-mistakes)
8. [Practice Exercises](#8-practice-exercises)
9. [Quick Summary (Cheat Sheet)](#9-quick-summary-cheat-sheet)

---

## 1. What Is a Variable?

A **variable** is a named container used to store data in a program. Think of it as a **labeled box**: the label is the variable's name, and the thing inside the box is its value.

```
┌───────────────────┐
│  name             │  ← label (variable name)
│  'Samiul Islam'   │  ← value stored inside
└───────────────────┘
```

Why do we need variables?

- To **store** data (a name, an age, a price, a score).
- To **reuse** the data many times without retyping it.
- To **change** the data later while the program runs.
- To make code **readable**, because a name like `user_age` explains itself.

---

## 2. Declaring Variables

In Python, you create a variable by writing:

```
variable_name = value
```

- **Left side:** the variable name.
- **`=`:** the **assignment operator**.
- **Right side:** the value you want to store.

> ⚠️ In math, `=` means "is equal to". In Python, `=` means **"store the value on the right into the name on the left"**.

### Example 1: Basic declaration

```python
name = 'Samiul Islam'
age = 18
```

- `name` holds the string `'Samiul Islam'`.
- `age` holds the number `18`.

### What is a string?

A **string** is a sequence of characters used to represent text. Strings are written inside **single quotes** `' '` or **double quotes** `" "`. Both are valid:

```python
greeting = 'Hello'
greeting = "Hello"
```

Numbers do **not** use quotes:

```python
age = 18        # a number
age = '18'      # a string that looks like a number (different thing!)
```

### Example 2: More variables

```python
first_name = 'Samiul'
last_name = 'Islam'
age = 18
city = 'Dhaka'
college = 'Dhaka College'
```

### Example 3: Changing a variable's value

Variables can be **reassigned**. That is why they are called *variables* (they can vary).

```python
age = 18
print(age)   # 18

age = 19
print(age)   # 19
```

The old value is replaced by the new one.

### Example 4: Using one variable to set another

```python
age = 18
new_age = age
print(new_age)   # 18
```

### Example 5: Assigning multiple variables in one line

```python
x, y, z = 1, 2, 3
```

(This works, but for beginners, writing each variable on its own line is clearer.)

### Example 6: Giving the same value to several variables

```python
a = b = c = 0
```

---

## 3. Variable Naming Rules

These are **rules**. If you break them, Python raises a `SyntaxError` and your program will not run.

### Rule 1: A name can only start with a letter or an underscore (`_`), not a number

```python
name1 = 'Samiul'    # ✅ starts with a letter
_name = 'Samiul'    # ✅ starts with an underscore
1name = 'Samiul'    # ❌ starts with a number
```

### Rule 2: A name can only contain letters, digits, and underscores

Allowed characters: `a-z`, `A-Z`, `0-9`, and `_`.

```python
user_age = 18       # ✅
user2 = 'Rahim'     # ✅
user age = 18       # ❌ contains a space
user-age = 18       # ❌ contains a hyphen
user@age = 18       # ❌ contains @
```

### Rule 3: Names are case-sensitive

`age`, `Age`, and `AGE` are **three different variables**.

```python
age = 18
Age = 25
AGE = 30

print(age)   # 18
print(Age)   # 25
print(AGE)   # 30
```

### Rule 4: A name cannot be a Python reserved keyword

Keywords have a special meaning in Python, so they cannot be used as variable names. Examples: `if`, `else`, `class`, `def`, `for`, `while`, `True`, `False`, `None`, `import`, `return`.

```python
class = 'Ten'     # ❌ 'class' is a keyword
if = 5            # ❌ 'if' is a keyword
def = 10          # ❌ 'def' is a keyword
```

To see all keywords on your machine:

```python
import keyword
print(keyword.kwlist)
```

### What an error looks like

```python
5variable_name = 5
```

```
    5variable_name = 5
     ^
SyntaxError: invalid syntax
```

> 💡 **Tip:** Do not fear errors. An error message is Python telling you exactly where it got confused. Learning to read errors is a core programmer skill.

### Valid vs. invalid: quick table

| Name | Valid? | Reason |
|---|---|---|
| `name` | ✅ | letters only |
| `user_name` | ✅ | letters and underscore |
| `_private` | ✅ | starts with underscore |
| `score2` | ✅ | digit is not first |
| `2score` | ❌ | starts with a digit |
| `my name` | ❌ | contains a space |
| `my-name` | ❌ | contains a hyphen |
| `for` | ❌ | reserved keyword |
| `Name` vs `name` | ✅ | two different variables |

---

## 4. Naming Conventions

**Rules** are enforced by Python. **Conventions** are good habits that the Python community agrees on. Breaking a convention will not cause an error, but it makes your code harder to read. Professional developers follow these.

### Convention 1: Use snake_case

Write names in **lowercase**, with words separated by **underscores**.

```python
my_variable_name = 'freeCodeCamp'
first_name = 'Samiul'
total_marks = 450
```

Other styles you may see in other languages (avoid these for Python variables):

```python
myVariableName = 1     # camelCase (common in JavaScript/Java)
MyVariableName = 1     # PascalCase (used for classes in Python)
my-variable-name = 1   # ❌ invalid in Python anyway
```

### Convention 2: Use descriptive names

A good name tells the reader what the variable stores.

```python
ua = 18             # ❌ What is "ua"?
age = 18            # 👍 Better
user_age = 18       # ✅ Best: clear purpose
```

More examples:

```python
# ❌ Poor names
n = 'Samiul'
p = 1500
t = 0.05

# ✅ Good names
student_name = 'Samiul'
product_price = 1500
tax_rate = 0.05
```

**Why it matters:** you write code once, but you (and your teammates) read it many times. Clear names save hours of confusion, especially in large codebases or when you return to your code months later.

### Convention 3: Avoid single-letter names

Single-letter names are common in Python (especially in math or short loops), but they communicate no meaning.

```python
x = 56        # ❌ 56 what? Age? Weight? Marks?
marks = 56    # ✅ Clear
```

### Convention 4: Do not use names that shadow built-in functions

```python
print = 'hello'   # ⚠️ legal, but now print() no longer works!
```

Avoid names like `print`, `list`, `str`, `int`, `max`, `min`, `sum` for your variables.

### Convention 5: Constants in UPPER_CASE (preview)

For values that should never change, programmers use all capital letters:

```python
PI = 3.14159
MAX_ATTEMPTS = 3
```

(Python won't stop you from changing them; it is just a signal to other developers.)

---

## 5. Writing Comments

A **comment** is a note inside your code that Python **ignores**. Comments are for humans, not for the computer.

### Single-line comments

Start with the pound symbol `#`. Everything after `#` on that line is ignored.

```python
# This is a single-line comment
name = 'Samiul Islam'
```

### Inline comments

You can put a comment at the end of a line of code:

```python
age = 18   # the user's age in years
```

### Multi-line comments

Python has no special multi-line comment symbol. Use consecutive single-line comments:

```python
# This is a
# multi-line
# comment
```

### Commenting out code

Comments are also used to temporarily disable a line of code:

```python
print('This runs')
# print('This does NOT run')
```

> 💡 In VS Code, select lines and press `Ctrl + /` (Windows/Linux) or `Cmd + /` (Mac) to toggle comments.

### When to use comments

✅ To explain **why** a piece of code exists.
✅ To leave **reminders** for yourself (e.g., `# TODO: add validation`).
✅ To clarify **tricky** logic.
✅ To help beginners and teammates.

### When NOT to use comments

❌ Do **not** use comments to explain what a variable name means. Pick a better name instead.

```python
# ❌ Bad: comment is covering for a poor name
x = 18   # age of the user

# ✅ Good: the name explains itself
user_age = 18
```

---

## 6. How the `print()` Function Works

### What is the terminal?

The **terminal** is the area where you see the **text output** of your program.

### What is `print()`?

`print()` is a **built-in function**, which means Python already provides it. You can use it right away without defining it yourself. Its job is to **send text and other values to the terminal**.

### Your first program

```python
print('Hello world!')   # Hello world!
```

Let's break it down:

```
print('Hello world!')
│    │ └───────────┘
│    │       └── argument (what we want to display)
│    └── parentheses (used to call the function)
└── function name
```

- `print` is the **function name**.
- `( )` are the **parentheses** that call the function.
- `'Hello world!'` is an **argument**, the value we pass to the function.

### Example 1: Printing text

```python
print('Welcome to Python!')
print("I am learning programming.")
```

**Output:**

```
Welcome to Python!
I am learning programming.
```

Each `print()` starts on a **new line**.

### Example 2: Printing numbers

```python
print(18)
print(3.14)
print(10 + 5)
```

**Output:**

```
18
3.14
15
```

Numbers don't need quotes. Python can even calculate inside `print()`.

### Example 3: Printing a variable

```python
name = 'Samiul Islam'
print(name)
```

**Output:**

```
Samiul Islam
```

### `print(name)` vs `print('name')`

This is a very common beginner confusion:

```python
name = 'Samiul Islam'

print(name)     # Samiul Islam  → prints the VALUE inside the variable
print('name')   # name          → prints the literal TEXT "name"
```

- **No quotes:** Python looks up the variable and prints its value.
- **With quotes:** Python prints exactly what you typed.

### Example 4: Printing multiple values

Separate arguments with **commas**:

```python
print('My favorite colors are', 'blue', 'green', 'red')
```

**Output:**

```
My favorite colors are blue green red
```

Python **automatically adds a space** between each item.

### Example 5: Mixing text and variables

```python
name = 'Samiul Islam'
age = 18

print('My name is', name)
print('I am', age, 'years old')
```

**Output:**

```
My name is Samiul Islam
I am 18 years old
```

You can mix strings, numbers, and variables in the same `print()`.

### Example 6: A complete mini-program

```python
# Student information
student_name = 'Samiul Islam'
student_age = 18
student_city = 'Dhaka'
student_college = 'Dhaka College'

# Display the information
print('Name:', student_name)
print('Age:', student_age)
print('City:', student_city)
print('College:', student_college)
```

**Output:**

```
Name: Samiul Islam
Age: 18
City: Dhaka
College: Dhaka College
```

### Example 7: Printing an empty line

```python
print('Line one')
print()
print('Line two')
```

**Output:**

```
Line one

Line two
```

### Example 8: Quotes inside strings

If your text contains a single quote, wrap it in double quotes (or vice versa):

```python
print("It's a beautiful day")
print('He said "Hello"')
```

**Output:**

```
It's a beautiful day
He said "Hello"
```

### Example 9: Printing a variable after changing it

```python
score = 50
print('Score:', score)

score = 75
print('Score:', score)
```

**Output:**

```
Score: 50
Score: 75
```

---

## 7. Common Mistakes

| Mistake | Wrong | Correct |
|---|---|---|
| Forgetting quotes around text | `print(Hello)` | `print('Hello')` |
| Mismatched quotes | `print('Hello")` | `print('Hello')` |
| Missing parentheses | `print 'Hello'` | `print('Hello')` |
| Wrong capitalization | `Print('Hello')` | `print('Hello')` |
| Starting a name with a number | `1name = 'Sam'` | `name1 = 'Sam'` |
| Space in a variable name | `my name = 'Sam'` | `my_name = 'Sam'` |
| Using a keyword as a name | `class = 'A'` | `class_name = 'A'` |
| Using a variable before creating it | `print(city)` | `city = 'Dhaka'` first, then `print(city)` |
| Confusing `=` with "equals" | reading `x = 5` as "x equals 5" | read it as "store 5 in x" |

### Example: `NameError`

If you use a variable before creating it, Python raises a `NameError`:

```python
print(city)
```

```
NameError: name 'city' is not defined
```

**Fix:**

```python
city = 'Dhaka'
print(city)
```

---

## 8. Practice Exercises

Try these yourself before looking at the solutions.

1. Create variables for your **name**, **age**, and **favorite color**, then print them on separate lines.
2. Print the sentence `My favorite colors are` followed by three colors using **one** `print()` call.
3. Create a variable `score = 50`, print it, change it to `80`, and print it again.
4. Fix these invalid names: `2nd_place`, `my city`, `total-marks`, `class`.
5. Rename the following variables to follow good conventions: `n`, `p`, `ua`.
6. Write a short program with at least **two comments** that prints your introduction.

<details>
<summary>Click to see solutions</summary>

```python
# 1
name = 'Samiul Islam'
age = 18
favorite_color = 'blue'
print('Name:', name)
print('Age:', age)
print('Favorite color:', favorite_color)

# 2
print('My favorite colors are', 'blue', 'green', 'red')

# 3
score = 50
print(score)
score = 80
print(score)

# 4
second_place = 2      # or place_2
my_city = 'Dhaka'
total_marks = 450
class_name = 'Ten'

# 5
student_name = 'Samiul'
product_price = 1500
user_age = 18

# 6
# Personal information
name = 'Samiul Islam'
age = 18

# Print the introduction
print('Hello! My name is', name, 'and I am', age, 'years old.')
```

</details>

---

## 9. Quick Summary (Cheat Sheet)

**Variables**

- A variable is a named box that stores data.
- Syntax: `variable_name = value`
- `=` is the **assignment operator** (it means "store", not "equals").
- Strings use quotes (`'...'` or `"..."`); numbers do not.
- A variable's value can be changed by reassigning.

**Naming rules (break them → `SyntaxError`)**

1. Start with a letter or `_`, never a digit.
2. Only letters, digits, and `_`.
3. Case-sensitive (`age` ≠ `Age` ≠ `AGE`).
4. No reserved keywords (`if`, `class`, `def`, …).

**Naming conventions (good habits)**

- Use `snake_case`.
- Use descriptive names (`user_age`, not `ua`).
- Avoid single-letter names.
- Do not reuse built-in names like `print` or `list`.

**Comments**

- Start with `#`; Python ignores them.
- Multi-line = several `#` lines.
- Explain **why**, not what a poorly-named variable means.

**`print()`**

- A built-in function that sends output to the terminal.
- Syntax: `print(argument)`
- Multiple values: `print('a', 'b', 'c')` → `a b c` (space added automatically).
- `print(name)` prints the value; `print('name')` prints the text.

---
