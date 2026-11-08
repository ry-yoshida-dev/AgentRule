---
paths:
  - "**/*.py"
---

# Python Rules

## Style

- Write code that complies with modern Python standards (e.g., Black, Ruff).
- Do not rely on implicit string concatenation (`"part1" "part2"`). Use one f-string per message, or join parts with explicit `+`.

## Docstrings

- All public classes, methods, and functions must have docstrings in the NumPy documentation style.
- Include Parameters, Returns, and Raises sections only when they contain meaningful information.
- Do not document None returns in a Returns section.

## Typing

- All variables, attributes, parameters, and return values must have explicit type annotations where the syntax allows.
- The use of `Any` is prohibited.
- Prefer domain-specific types, Protocols, generic type parameters, and abstract base classes.
- Use `object` only when no meaningful abstraction can be expressed.
- Use built-in generic types such as `list[str]` and `dict[str, int]`. Do not use `typing.List`, `typing.Dict`, or similar aliases.
- Use the `X | Y` union syntax. Do not use `Union`.
- Use `| None` only when absence is a valid domain concept.
- Code must pass `mypy --strict`.
- Code must pass basedpyright without suppressions where avoidable.
- Use casts and `# type: ignore` only when the type relationship cannot be expressed statically.

## Modeling

- Prefer `match-case` for Enum dispatch, state transitions, and multi-branch logic. Use `if-elif` when it is clearly more readable.
- Prefer a dedicated `@dataclass` when a function returns multiple related values with domain meaning. Tuples are fine for small, self-evident results.
- Use `@dataclass` for a class whose `__init__` only stores its parameters as attributes.
- Use `Enum` for states, categories, and finite domains. String literal branching is prohibited.
- Prefer cohesive class-based designs over collections of standalone functions.
- Avoid classes and wrappers that do not provide clear semantic value.
- All boolean variables and attributes must use the `is_*` naming convention.

## Errors

- Do not use `try-except` for expected flow control.

## Structure

- Use `__init__.py` to manage public APIs and prevent messy deep imports.
- Each Python file must contain at most one class.
- Supporting data structures should be placed in their own files.
- **Hierarchy Separation**: Place the concrete classes of each project-defined abstract class (ABC or Protocol) that has two or more explicitly inheriting concrete classes as follows. Concrete classes used only in tests belong in the test directory and are outside this rule.
  - When concrete classes of two or more abstract classes import one another within the same implementation (one direction is enough), create a directory per implementation and name each file after its abstract class (`<implementation>/<abstract>.py`). When an implementation lacks some of the abstract classes, omit those files.
  - Otherwise, create a directory per abstract class and name each file after its implementation (`<plural of abstract>/<implementation>.py`).
  - In both layouts, place each abstract class as `<abstract>.py` at the same level as the directories of its concrete classes.
  - When abstract classes inherit from other abstract classes, decide the layout by the abstract class the concrete class inherits directly.
  - Derive the file name by removing prefixes and suffixes such as `Base`, `Abstract`, `Protocol`, and `Interface` from the abstract class name and converting it to snake_case. Name the directory by pluralizing only the last word in English (`DataLoader` becomes `data_loaders/`, `Strategy` becomes `strategies/`).
  - Include the implementation name in each concrete class name (the concrete class in `tmp/processor.py` is `TmpProcessor`).
  - When adding or removing abstract classes or implementations changes which layout applies, propose the move and do not move existing files until instructed.
- **Non-Redundant Filenames**: Filenames must not repeat the parent directory or domain concept as a prefix or suffix (e.g., inside `processors/`, use `tmp.py` instead of `tmp_processor.py`).

## Tests

- Cover logic with unit tests.
