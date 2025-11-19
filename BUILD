load("@rules_cc//cc:defs.bzl", "cc_binary", "cc_library")
load("@rules_foreign_cc//foreign_cc:defs.bzl", "cmake")


filegroup(
    name = "lean_src",
    srcs = ["lean4-4.25.1/CMakeLists.txt"] + glob(["lean4-4.25.1/cmake/*", "lean4-4.25.1/src/**", "lean4-4.25.1/stage0/**"]), # glob(["lean-4.25.1/**"]),
    visibility = ["//visibility:public"],
)

filegroup(
    name = "main_src",
    srcs = glob(["src/**"]),
    visibility = ["//visibility:public"],
)
cmake(
    name = "lean4",
    lib_source = ":lean_src",
    out_binaries = select({
        "//conditions:default": ["lean"],
    }),
    tags = ["requires-network"],
    # cache_entries = {
    #     "CMAKE_C_FLAGS": "--preset release",
    # },
)

cc_binary(
    name = "lean_test",
    # includes just hello.h, include directory: "include/version123"
    srcs = ["//static:main.c"],
    deps = [":lean4"],
)
