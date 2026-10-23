# Python Data Types, type() and isinstance() – Notes

## 1. What Is a Data Type?

A data type describes the kind of value a variable holds, for example a number or a piece of text. Python uses data types to know how to store a value and how to work with it.

---

## 2. Python Is Dynamically Typed

You do not specify a variable's data type when you create it. Python figures out the type from the value you assign.

```python
name = 'Rahim Uddin'   # string
age = 25               # integer
```

The same variable can later hold a value of a different type:

```python
age = 25
age = 'Twenty-five'    # age is now a string
```

---

## 3. Four Common Data Types

| Type | Meaning | Examples |
|------|---------|----------|
| `int` (Integer) | A whole number without decimals | `10`, `-5` |
| `float` (Float) | A number with a decimal point | `4.41`, `-0.4` |
| `str` (String) | A sequence of characters inside single or double quotes | `'Hello world!'` |
| `bool` (Boolean) | Only two possible values | `True`, `False` |

```python
my_integer_var = 10
print('Integer:', my_integer_var)   # Integer: 10

my_float_var = 4.50
print('Float:', my_float_var)       # Float: 4.5

my_string_var = 'hello'
print('String:', my_string_var)     # String: hello

my_boolean_var = True
print('Boolean:', my_boolean_var)   # Boolean: True
```

**Remember:**
- A float written as `4.50` is printed as `4.5`.
- `True` and `False` must start with a capital letter.

---

## 4. The type() Function

`type()` tells you what type a variable is.

```python
developer = 'Karim'
print(type(developer))   # <class 'str'>
```

`<class 'str'>` means `developer` is a string.

Output for each type you have learned:

```python
print(type(my_integer_var))   # <class 'int'>
print(type(my_float_var))     # <class 'float'>
print(type(my_string_var))    # <class 'str'>
print(type(my_boolean_var))   # <class 'bool'>
```

**Error:** Calling `type()` with no argument raises an error:

```
TypeError: type() takes 1 or 3 arguments
```

---

## 5. The isinstance() Function

Use `isinstance()` to check that a value is a specific type before performing an operation on it. It returns `True` or `False`.

**Why it matters:**

```python
account_balance = '12'
account_balance / 2
# TypeError: unsupported operand type(s) for /: 'str' and 'int'
```

`'12'` is inside quotes, so it is a string, and a string cannot be divided by a number.

**Checking a type:**

```python
account_balance = '12'
print(isinstance(account_balance, int))   # False
```

**Syntax:** `isinstance(value, type)`

**Checking multiple types at once:**

```python
account_balance = 12
print(isinstance(account_balance, (int, float)))   # True
```

Put the types inside parentheses. If the value matches any one of them, the result is `True`. If `account_balance` were `12.0`, the result would still be `True` because it is a float.

---

## 6. type() vs isinstance()

| | `type()` | `isinstance()` |
|---|---|---|
| Purpose | Shows the type | Checks whether the type matches |
| Returns | A class like `<class 'int'>` | `True` / `False` |
| Use it for | Finding out the type | Verifying before an operation |

---

## 7. Quick Recap

- A data type is the kind of value a variable holds.
- Python is dynamically typed, so you do not declare types.
- Four types: `int`, `float`, `str`, `bool`.
- `type()` shows the type of a variable.
- `isinstance()` checks a type and returns `True` or `False`.

## 8. Practice

1. Create variables with different values and run `type()` on each.
2. Run `isinstance(x, int)` on both `'12'` and `12` and compare the results.
3. Assign a number to a variable, then a string, and check `type()` after each assignment.
4. Create a variable `student_name = 'Nusrat Jahan'` and check whether it is a `str`.