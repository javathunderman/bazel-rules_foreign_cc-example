# example code is taken from https://github.com/Akagi201/learning-cmake/tree/master/hello-world-lib
# for test only

load("@rules_cc//cc:defs.bzl", "cc_binary")
load("@rules_foreign_cc//foreign_cc:defs.bzl", "cmake")

filegroup(
    name = "srcs",
    srcs = glob(["**"]),
    visibility = ["//visibility:public"],
)
exports_files([
    "main.c",
])
cc_binary(
    name = "lean4_test",
    # includes just hello.h, include directory: "include/version123"
    srcs = ["main.c"],
    # deps = select({
    #     "//:windows": [":libhello_win"],
    #     "//conditions:default": [":libhello"],
    # }),
)