# Variables

A variable is a name a program uses to refer to a value. Names make programs easier to read and let a program reuse or update information.

```python
name = "Mina"
score = 10
score = score + 1
```

After these instructions, `name` refers to the text `"Mina"` and `score` refers to the number `11`. The `=` symbol in an assignment means “associate this name with this value,” not necessarily “these two things are mathematically equal.”

## Values and types

Programs work with values such as numbers, text, true-or-false values, and collections. A value's type describes what kind of value it is and which operations make sense. For example, adding two numbers is different from joining two pieces of text.

Languages handle types in different ways. Some check many type rules before a program runs; others discover certain mismatches while it runs. Even when a language allows flexibility, choosing clear and consistent values helps prevent bugs.

## Names and scope

Choose names that describe the purpose of a value, such as `item_count`, instead of vague names such as `x` when the meaning is not obvious. A variable's scope is the part of the program where that name can be used. Keeping values in a small, clear scope makes programs easier to understand.

Variables are connected to [memory](./memory.md): values must be represented somewhere while a program uses them. The exact relationship between a name and its value depends on the language.
