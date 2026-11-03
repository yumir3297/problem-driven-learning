---
type: learning-note
topic: "Python Variable Naming Rules"
created: YYYY-MM-DD
updated: YYYY-MM-DD
tags:
  - learning
  - python
---

# Python Variable Naming Rules

> This is a completed-note format demonstration. The opening case is a representative teaching scenario, not a claim about the historical origin of Python naming rules.

## 1. Classic / representative problem

Suppose a program stores three students' scores:

~~~python
a = 86
b = 92
c = 78
~~~

The program runs, but a week later you cannot tell which variable belongs to which student. Another developer may also accidentally overwrite a built-in name or use a Python keyword.

**Problem:** How should a program name values so that code remains valid and understandable?

## 2. Analyze the problem

There are two separate requirements:

- **Validity:** the name must be accepted by Python's syntax.
- **Readability:** a person should infer the value's meaning from the name.

A name can be syntactically valid but still be a poor choice, such as x1.

## 3. How the knowledge solves it

Python uses identifiers to name variables, functions, classes, and other objects. Naming rules prevent ambiguous or syntactically invalid tokens; naming conventions improve communication between programmers.

~~~python
yuewen_score = 86
average_score = 85.3
~~~

The first name communicates meaning. The second communicates what the value represents.

## 4. Formalize the knowledge

An **identifier** is a name used to identify a program entity.

For ordinary Python identifiers:

- They may contain letters, underscores, and digits after the first character.
- They cannot start with a digit.
- They are case-sensitive.
- They cannot be Python reserved keywords such as class or for.

> [!question] 学习中的疑问
> 为什么 2score 不行，但 score2 可以？
>
> **解答：** Python 解析标识符时，首字符不能是数字；后续字符才允许包含数字。因此 score2 合法，而 2score 不符合标识符语法。

Examples:

~~~python
student_score = 86   # valid
_score = 86           # valid
score2 = 86           # valid
2score = 86           # invalid
class = "A"           # invalid: reserved keyword
~~~

A common convention is snake_case for variables and functions:

~~~python
total_score = 256
~~~

Remember the distinction: syntax rules determine whether a name is legal; style conventions determine whether it is easy to read.

## 5. Extend the problem

The same naming ideas apply to functions, classes, modules, and constants, but conventions differ by entity type. For example, Python commonly uses PascalCase for class names and uppercase names for module-level constants.

A valid identifier is not automatically a good name. x may be appropriate in a short mathematical loop, but total_student_score is clearer in business logic.

## 6. Progressive challenges

Ask one at a time during teaching; do not reveal all answers immediately. In the completed note, record only the questions and answers actually discussed.

1. **Recognition:** Is student_2 a valid identifier?
2. **Basic operation:** Rewrite a = 90 as a clearer variable assignment for a student's exam score.
3. **Reasoning:** Why is class invalid, while class_name is valid?
4. **Transfer:** A function calculates the average score of a class. Propose a suitable function name and explain the choice.
5. **Synthesis:** Review a short score-processing program and identify names that are invalid, misleading, or inconsistent.

## Learning status

Record 已掌握 / 基本掌握 / 待巩固 only after observing the learner's actual explanation and application. Do not infer mastery from passive agreement.