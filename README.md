# ZigPython

An extensible Python interpreter written in Zig.

## Subsystems/aspects

|                                                                                                      |     |
| ---------------------------------------------------------------------------------------------------- | --- |
| tokenize-and-parse Python code                                                                       |     |
| AST JSON schema                                                                                      |     |
| AST structs / defined memory layout                                                                  |     |
| exec/eval an AST node in a [Frame](https://docs.python.org/3/reference/datamodel.html#frame-objects) |     |
| call Zig/C/WASM functions from Python                                                                |     |
| generate Python code from an AST node                                                                |     |
| add extensions/plugins, including AST modification                                                   |     |

## Origin

Consider Akin's 39th [Law of Spacecraft Design](https://spacecraft.ssl.umd.edu/akins_laws.html):

> Any exploration program which "just happens" to include a new launch vehicle is, de facto, a launch vehicle program.

Likewise, any software project whose scope just happens to include the evaluation of Python code is at risk of becoming, de facto, a Python interpreter project.

ZigPython is the de-facto-Python-interpreter-project that arose from the [artc format project](https://artcformat.org/).

## Status: 🚧

My top priority is getting the basics of [artc format](https://artcformat.org/) done.

Sometime after that, ZigPython will be factored out, documented, and released under an FSF-approved FLOSS license.

## Supported platforms

- WASM, arm, x64, ...

## Some of the initial limitations

- no `global`, `with`, `del`, `try`/`catch`
- no decorators
- no generators / `yield`
- no coroutines / `async` / `await`
- no type annotations
- minimal subset of Python built-ins
- minimal subset of the Python stdlib
- values of type `int` are backed by `i64`s — arbitrary-precision integers are not yet supported
