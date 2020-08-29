workspace(name = "rules_foreign_cc_usage_example")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# Group the sources of the library so that CMake rule have access to it
all_content = """filegroup(name = "all", srcs = glob(["**"]), visibility = ["//visibility:public"])"""

# Rule repository
http_archive(
   name = "rules_foreign_cc",
   strip_prefix = "rules_foreign_cc-master",
   url = "https://github.com/bazelbuild/rules_foreign_cc/archive/master.zip",
)

load("@rules_foreign_cc//:workspace_definitions.bzl", "rules_foreign_cc_dependencies")
# https://github.com/bazelbuild/rules_foreign_cc/blob/master/workspace_definitions.bzl#L66-L69
rules_foreign_cc_dependencies()

# tdlib
http_archive(
   name = "tdlib",
   build_file_content = all_content,
   strip_prefix = "td-1.6.0",
   urls = ["https://github.com/tdlib/td/archive/v1.6.0.tar.gz"]
)
