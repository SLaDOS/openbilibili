load(
    "@io_bazel_rules_go//proto:def.bzl",
    "go_proto_library",
)

package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
)

proto_library(
    name = "quality_proto",
    srcs = ["quality.proto"],
    tags = ["automanaged"],
    deps = ["@gogo_special_proto//github.com/gogo/protobuf/gogoproto"],
)

go_proto_library(
    name = "quality_go_proto",
    compilers = ["@io_bazel_rules_go//proto:gogofast_proto"],
    importpath = "go-common/app/job/bbq/recall/proto/quality",
    proto = ":quality_proto",
    tags = ["automanaged"],
    deps = ["@com_github_gogo_protobuf//gogoproto:go_default_library"],
)

go_library(
    name = "go_default_library",
    srcs = [],
    embed = [":quality_go_proto"],
    importpath = "go-common/app/job/bbq/recall/proto/quality",
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
    deps = [
        "@com_github_gogo_protobuf//gogoproto:go_default_library",
        "@com_github_gogo_protobuf//proto:go_default_library",
    ],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
