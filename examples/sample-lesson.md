# Sample Lesson: Python Variable Naming Rules

> This is a format demonstration. The opening case is a representative teaching scenario, not a claim about the historical origin of Python naming rules.

## 1. Classic / representative problem

Suppose a program stores three students' scores:

\`\`\`python
a = 86
b = 92
c = 78
\`\`\`

The program runs, but a week later you cannot tell which variable belongs to which student. Another developer may also accidentally overwrite a built-in name or use a Python keyword.

**Problem:** How should a program name values so that code remains valid and understandable?

## 2. Analyze the problem

There are two separate requirements:

- **Validity:** the name must be accepted by Python's syntax.
- **Readability:** a person should infer the value's meaning from the name.

A name can be syntactically valid but still be a poor choice, such as \`x1\`.

*Adaptive checkpoint:* “Which problem would still exist if we only checked whether the name was syntactically valid?”

## 3. How the knowledge solves it

Python uses identifiers to name variables, functions, classes, and other objects. Naming rules prevent ambiguous or syntactically invalid tokens; naming conventions improve communication between programmers.

\`\`\`python
yuewen_score = 86
average_score = 85.3
\`\`\`

The first name communicates ownership and meaning. The second communicates what the value represents.

## 4. Formalize the knowledge

An **identifier** is a name used to identify a program entity.

For ordinary Python identifiers:

- They may contain letters, underscores, and digits after the first character.
- They cannot start with a digit.
- They are case-sensitive.
- They cannot be Python reserved keywords such as \`class\` or \`for\`.

Examples:

\`\`\`python
student_score = 86   # valid
_score = 86           # valid
score2 = 86           # valid
2score = 86           # invalid
class = "A"           # invalid: reserved keyword
\`\`\`

A common convention is \`snake_case\` for variables and functions:

\`\`\`python
total_score = 256
\`\`\`

Remember the distinction: syntax rules determine whether a name is legal; style conventions determine whether it is easy to read.

## 5. Extend the problem

The same naming ideas apply to functions, classes, modules, and constants, but conventions differ by entity type. For example, Python commonly uses \`PascalCase\` for class names and uppercase names for module-level constants.

A valid identifier is not automatically a good name. \`x\` may be appropriate in a short mathematical loop, but \`total_student_score\` is clearer in business logic.

## 6. Progressive challenges

Ask one at a time; do not reveal all answers immediately.

1. **Recognition:** Is \`student_2\` a valid identifier?
2. **Basic operation:** Rewrite \`a = 90\` as a clearer variable assignment for a student's exam score.
3. **Reasoning:** Why is \`class\` invalid, while \`class_name\` is valid?
4. **Transfer:** A function calculates the average score of a class. Propose a suitable function name and explain the choice.
5. **Synthesis:** Review a short score-processing program and identify names that are invalid, misleading, or inconsistent.

## Teaching note

For a learner who answers the first three questions confidently, skip repetitive syntax drills and move to code review. If they confuse validity with naming style, return to that distinction before continuing.
