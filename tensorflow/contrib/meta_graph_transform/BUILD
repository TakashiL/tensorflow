# Description:
#   Utility for applying the Graph Transform tool to a MetaGraphDef.

package(default_visibility = ["//visibility:public"])

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

load(
    "//tensorflow:tensorflow.bzl",
    "py_test",
)

py_library(
    name = "meta_graph_transform",
    srcs = [
        "__init__.py",
        "meta_graph_transform.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/core:protos_all_py",
        "//tensorflow/python:ops",
        "//tensorflow/python/saved_model:constants",
        "//tensorflow/tools/graph_transforms:transform_graph_py",
    ],
)

py_test(
    name = "meta_graph_transform_test",
    size = "small",
    srcs = ["meta_graph_transform_test.py"],
    srcs_version = "PY2AND3",
    visibility = ["//visibility:private"],
    deps = [
        ":meta_graph_transform",
        "//tensorflow/python:client_testlib",
    ],
)

filegroup(
    name = "py_srcs",
    data = glob([
        "**/*.py",
    ]),
)

filegroup(
    name = "all_files",
    srcs = glob(
        ["**/*"],
        exclude = [
            "**/METADATA",
            "**/OWNERS",
        ],
    ),
    visibility = ["//tensorflow:__subpackages__"],
)
