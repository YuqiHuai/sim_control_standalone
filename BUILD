load("@rules_cc//cc:defs.bzl", "cc_library", "cc_binary")
load("//tools:cpplint.bzl", "cpplint")

package(default_visibility = ["//visibility:public"])

cc_library(
    name = "sim_control",
    srcs = ["sim_control.cc"],
    hdrs = [
        "sim_control.h",
        "sim_control_interface.h",
    ],
    alwayslink = True,
    # copts = ['-DMODULE_NAME=\\"dreamview\\"'],
    deps = [
        "//cyber",
        "//modules/common/adapters:adapter_gflags",
        "//modules/common/util:util_tool",
        "//modules/dreamview/backend/common:dreamview_gflags",
        "//modules/dreamview/backend/map:map_service",
        "//modules/map/relative_map/proto:navigation_cc_proto",
        "//modules/planning/proto:planning_cc_proto",
        "//modules/prediction/proto:prediction_obstacle_cc_proto",
        "//modules/prediction/proto:scenario_cc_proto",
        "@com_google_googletest//:gtest",
    ],
)

cc_binary(
    name = "main",
    srcs = ["main.cc"],
    deps = [
        "//modules/dreamview/backend/map:map_service",
        "//modules/sim_control_standalone:sim_control"
    ],
)


cpplint()