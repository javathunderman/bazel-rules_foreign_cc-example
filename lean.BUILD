load("@rules_cc//cc:defs.bzl", "cc_binary", "cc_library")
load("@rules_foreign_cc//foreign_cc:defs.bzl", "cmake")


filegroup(
    name = "lean_src",
    srcs = ["CMakeLists.txt"] + glob(["cmake/*", "src/**", "stage0/**"]), # glob(["**"]),
    visibility = ["//visibility:public"],
)

cmake(
    name = "lean4",
    lib_source = ":lean_src",
    out_binaries = select({
        "//conditions:default": ["lean"],
    }),
    build_args = ["-j128"],
    tags = ["requires-network"],
    visibility = ["//visibility:public"],
)
