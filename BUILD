# example code is taken from https://github.com/Akagi201/learning-cmake/tree/master/hello-world-lib
# for test only
load("@rules_foreign_cc//foreign_cc:defs.bzl", "cmake")

filegroup(
    name = "srcs",
    srcs = glob(["src/**"]),
    visibility = ["//visibility:public"],
)

cmake(
    name = "libhello",
    cache_entries = {
        "CMAKE_MACOSX_RPATH": "True",
    },
    lib_source = ":srcs",
    out_binaries = select({
        "//conditions:default": ["hello"],
    }),
)

filegroup(
    name = "binary",
    srcs = [":libhello"],
    output_group = select({
        "//conditions:default": "hello",
    }),
)