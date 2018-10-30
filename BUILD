load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library")
load("@bazel_gazelle//:def.bzl", "gazelle")

# gazelle:prefix github.com/th0br0/vault-auth-plugin-example
gazelle(name = "gazelle")

go_library(
    name = "go_default_library",
    srcs = ["main.go"],
    importpath = "github.com/th0br0/vault-auth-plugin-example",
    visibility = ["//visibility:private"],
    deps = [
        "@com_github_hashicorp_vault//helper/pluginutil:go_default_library",
        "@com_github_hashicorp_vault//logical:go_default_library",
        "@com_github_hashicorp_vault//logical/framework:go_default_library",
        "@com_github_hashicorp_vault//logical/plugin:go_default_library",
    ],
)

go_binary(
    name = "vault-auth-plugin-example",
    embed = [":go_default_library"],
    visibility = ["//visibility:public"],
)
