py_library(
    name = "quantization_lib",
    srcs = [
        "quantization/quantize_util.py",
    ],
    srcs_version = "PY2AND3",
)

py_library(
    name = "converter_lib",
    srcs = [
        "convert_util.py",
        "converter_tool/base_converter.py",
        "converter_tool/caffe_converter.py",
        "converter_tool/hexagon_converter.py",
        "converter_tool/onnx_converter.py",
        "converter_tool/shape_inference.py",
        "converter_tool/tensorflow_converter.py",
        "converter_tool/transformer.py",
        "graph_util.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        ":quantization_lib",
        "//mace/proto:mace_py",
        "//third_party/caffe:caffe_py",
    ],
)

py_library(
    name = "model_saver_lib",
    srcs = [
        "model_saver.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        "//mace/proto:mace_py",
    ],
)

py_binary(
    name = "converter",
    srcs = ["converter.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":converter_lib",
        ":model_saver_lib",
        "//mace/python/tools/visualization:visualization_lib",
        "@six_archive//:six",
    ],
)

py_binary(
    name = "archive_static_lib",
    srcs = ["archive_static_lib.py"],
    srcs_version = "PY2AND3",
    visibility = ["//visibility:public"],
)

py_binary(
    name = "layers_validate",
    srcs = [
        "layers_validate.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        ":converter_lib",
        ":model_saver_lib",
    ],
)
