# Bazel code generation example

    $ bazel build -s //:foo_test
    $ bazel run //:foo_test

If there are changes to

* `foo.hpp.template`
* `foo.cpp.template`
* `code_generator.py`

then `code_generator.py` will be re-run. Compilation of the generated code will
*only* occur if the generated files themselves change. Typically, this means
that changes to `code_generator.py` that don't result in different file
contents in the generated files will not result in a re-compilation. Any
targets that depend directly, or transitively, upon the generated library, be
updated in the same fashion as a normal (i.e., non-generated) library would.
