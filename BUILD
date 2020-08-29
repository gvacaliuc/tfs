java_binary(
    name = "example",
    srcs = [
        "src/main/io/github/gvacaliuc/example/Example.java",
    ],
    main_class = "io.github.gvacaliuc.example.Example",
    deps = [
        ":tdlib_wrapper",
    ],
)


java_library(
    name = "tdlib_wrapper",
    srcs = glob(["src/main/org/**/*.java"]),
    data = [
        "@tdlib//:lib",
    ],
)
