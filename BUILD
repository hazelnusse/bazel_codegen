load("//:codegen.bzl", "cc_gen_library")

py_binary(
    name = "code_generator",
    srcs = ["code_generator.py"]
)

cc_gen_library(
    library_name = "foo",
    code_gen = ":code_generator",
    header_template = "foo.hpp.template",
    source_template = "foo.cpp.template",
)

cc_binary(
    name = "foo_test",
    srcs = ["foo_test.cpp"],
    deps = [":foo"]
)
