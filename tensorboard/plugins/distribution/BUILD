# Description:
# TensorBoard plugin for distributions

package(default_visibility = ["//tensorboard:internal"])

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

## Distributions Plugin ##
py_library(
    name = "distributions_plugin",
    srcs = ["distributions_plugin.py"],
    srcs_version = "PY2AND3",
    visibility = ["//visibility:public"],
    deps = [
        ":compressor",
        "//tensorboard/backend:http_util",
        "//tensorboard/plugins:base_plugin",
        "//tensorboard/plugins/histogram:histograms_plugin",
        "@org_pocoo_werkzeug",
    ],
)

py_test(
    name = "distributions_plugin_test",
    size = "small",
    srcs = ["distributions_plugin_test.py"],
    main = "distributions_plugin_test.py",
    srcs_version = "PY2AND3",
    deps = [
        ":compressor",
        ":distributions_plugin",
        "//tensorboard/compat:tensorflow",
        "//tensorboard/backend:application",
        "//tensorboard/backend/event_processing:event_accumulator",
        "//tensorboard/backend/event_processing:event_multiplexer",
        "//tensorboard/plugins:base_plugin",
        "//tensorboard/plugins/histogram:summary",
        "@org_pocoo_werkzeug",
        "@org_pythonhosted_six",
    ],
)

py_library(
    name = "compressor",
    srcs = ["compressor.py"],
    srcs_version = "PY2AND3",
    visibility = ["//visibility:public"],
    deps = ["//tensorboard:expect_numpy_installed"],
)

py_test(
    name = "compressor_test",
    size = "small",
    srcs = ["compressor_test.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":compressor",
        "//tensorboard/compat:tensorflow",
    ],
)
