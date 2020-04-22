cc_library(
    name = "pdpi",
    srcs = ["pdpi.cc",
            "util.cc"],
    hdrs = ["pdpi.h",
            "util.h"],
    deps = [
      "@com_github_p4lang_p4runtime//:p4info_cc_proto",
      "@com_github_p4lang_p4runtime//:p4runtime_cc_proto",
      "@com_google_absl//absl/strings:strings",
      "@com_google_absl//absl/algorithm:container",
    ],
)

cc_test(
    name = "pdpi_test",
    size = "small",
    srcs = ["pdpi_test.cc"],
    data = ["testdata"],
    deps = [
        "pdpi",
        "pd_cc_proto",
        "@com_google_googletest//:gtest_main",
    ],
)

proto_library(
    name = "p4common_p4_proto",
    srcs = ["testdata/pdpi_p4common.proto"],
)

cc_proto_library(
    name = "p4common_p4_cc_proto",
    deps = [":p4common_p4_proto"],
)

proto_library(
    name = "pd_proto",
    srcs = ["testdata/pdpi_proto_p4.proto"],
    deps = [":p4common_p4_proto"],
)

cc_proto_library(
    name = "pd_cc_proto",
    deps = [":pd_proto"]
)