# General Rules

## Language

- Communicate with the user in **Japanese**.
- Write natural Japanese. When a technical term has an established form in its field, in English or katakana, use that form instead of translating it word for word.
- Write code, comments, documentation (e.g., README.md), commit messages, and PR descriptions in **English**.

## Documentation

- Add comments only at key points where the code alone does not convey the intent. Do not comment line by line.
- Every directory containing source files must include a concise `README.md` with an `Overview`.
- Sub-directories also need a `Components` table linking each file or sub-directory (except package initializers such as `__init__.py`) to its responsibility.
- Add an `Examples` section to a `README.md` where it helps the reader.
- When a code change affects public behavior, architecture, or usage, update the corresponding `README.md`.

## Design

- Avoid abbreviations unless they are industry-standard.
- At the start of a function or method, before doing any other work, validate the inputs its types do not guarantee.
- Raise or throw the most specific error type available. Do not use generic ones.
- Breaking changes are acceptable when they significantly improve code quality, maintainability, type safety, or architecture.
- Backward compatibility should not be preserved solely for its own sake.
- Keep processing latency low. Prefer batch operations, keyed lookups, and vectorized or built-in operations over element-by-element iteration, especially nested loops and per-item I/O.

## Structure

- Everything in a directory must belong to that directory's responsibility. When a new or existing file or sub-directory does not fit, propose moving it to a different directory or creating a new one.
- When a directory groups interchangeable items, such as the implementations of one abstract class, keep its contents the same kind of thing.
- In upper-level directories, follow the directory structure and naming conventions established for the programming language.
- Name files and directories so that reading a path from the top down lets the reader infer what each level contains.
- Avoid vocabulary that comes from the conventions of modules used internally, and choose names with general meaning.
- Proper names of external modules or programs may be used in files and directories close to the concrete layer.

## Tooling and Platform

- In an existing project, follow its established stack and conventions unless asked to change them.
- Check the documentation for the installed version instead of relying on memory.
- If a rule names a tool or API that has since been superseded, follow current practice and tell the user the rule is outdated.
- For new projects, check current releases and choose the tools that best fit the project at the time. Do not assume the ones covered in this repository are still the best choice.
- Write mobile apps, including those that also target the web, with a cross-platform framework by default. Use native code only when the app depends on image capture or other capabilities that cross-platform frameworks cannot serve well.
- Before changing a user interface, read the guideline for each platform it targets: [ui/web.md](ui/web.md) for browsers, and [ui/mobile.md](ui/mobile.md) for iOS and Android.

## Security

- Before adding a dependency, confirm that the package name is the intended one. For packages that are not widely used, also check the publisher, maintenance activity, known vulnerabilities, and install scripts.
- Configure the package manager to skip releases newer than 7 days, instead of checking release dates by hand.
- Commit lockfiles, and do not run install scripts or remote scripts that have not been checked.
- Accept lockfile version updates that the package manager resolves within the cooldown. Do not report, question, or revert them, even when they are unrelated to the task.
- Before using a module that connects to external services, check where it connects, what data it sends, and whether its telemetry can be disabled. Skip this for services run by public institutions or major organizations.
- When building web modules, treat all external input and responses as untrusted. Validate them at the boundary, keep secrets out of source code and client-side code, and do not weaken authentication, authorization, or transport security for convenience.

## Git

- Make one commit per theme. Keep a change in the same commit as the changes it needs to work, so that each commit leaves the project in a working state.
- Never add `Co-Authored-By: Claude` or any other AI attribution to commit messages, PR descriptions, or any other artifact, in any repository.
- In `.gitignore`, list only commonly ignored files and data files or folders that the repository's purpose clearly requires. Put everything else in `.git/info/exclude`.
