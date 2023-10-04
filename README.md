Reproduction of https://github.com/smeijer/unimported/issues/187

Showing that `unimported` is accidentally traversing and parsing node_modules
resulting in reporting on unresolved dependencies that exist within those
modules and separate from application code. This then has a penalty due to the
overhead of traversing the potentially many files in node_modules.

1. Clone this repo
2. Run `npx unimported`
3. See that `test-module-B` is reported as unresolved, despite coming from within the node_modules/ folder
