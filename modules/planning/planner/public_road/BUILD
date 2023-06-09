load("@rules_cc//cc:defs.bzl", "cc_library", "cc_test")
load("//tools:cpplint.bzl", "cpplint")

package(default_visibility = ["//visibility:public"])

cc_library(
    name = "public_road_planner",
    srcs = ["public_road_planner.cc"],
    hdrs = ["public_road_planner.h"],
    copts = ["-DMODULE_NAME=\\\"planning\\\""],
    deps = [
        "//cyber",
        "//modules/common_msgs/basic_msgs:pnc_point_cc_proto",
        "//modules/common/status",
        "//modules/common/util",
        "//modules/common/util:util_tool",
        "//modules/common/vehicle_state:vehicle_state_provider",
        "//modules/map/hdmap",
        "//modules/planning/common:planning_common",
        "//modules/planning/common:planning_gflags",
        "//modules/planning/constraint_checker",
        "//modules/planning/math/curve1d:quartic_polynomial_curve1d",
        "//modules/planning/planner",
        "//modules/common_msgs/planning_msgs:planning_cc_proto",
        "//modules/planning/reference_line",
        "//modules/planning/reference_line:qp_spline_reference_line_smoother",
        "//modules/planning/tasks:task",
        "//modules/planning/tasks/deciders/path_decider",
        "//modules/planning/tasks/deciders/speed_decider",
        "//modules/planning/tasks/optimizers:path_optimizer",
        "//modules/planning/tasks/optimizers:speed_optimizer",
        "//modules/planning/tasks/optimizers/path_time_heuristic:path_time_heuristic_optimizer",
        "@com_github_gflags_gflags//:gflags",
        "@eigen",
    ],
)

cc_test(
    name = "public_road_planner_test",
    size = "small",
    srcs = ["public_road_planner_test.cc"],
    linkopts = ["-lgomp"],
    deps = [
        ":public_road_planner",
        "@com_google_googletest//:gtest_main",
    ],
    linkstatic = True,
)

cpplint()
