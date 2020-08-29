workspace(name = "tfs")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "io_tweag_rules_nixpkgs",
    strip_prefix = "rules_nixpkgs-dc24090573d74adcf38730422941fd69b87682c7",
    urls = ["https://github.com/tweag/rules_nixpkgs/archive/dc24090573d74adcf38730422941fd69b87682c7.tar.gz"],
)

load("@io_tweag_rules_nixpkgs//nixpkgs:repositories.bzl", "rules_nixpkgs_dependencies")
rules_nixpkgs_dependencies()

load("@io_tweag_rules_nixpkgs//nixpkgs:nixpkgs.bzl", "nixpkgs_git_repository", "nixpkgs_package")

nixpkgs_git_repository(
    name = "nixpkgs",
    revision = "20.03",
)

nixpkgs_package(
    name = "tdlib",
    repositories = { "nixpkgs": "@nixpkgs//:default.nix" },
)
