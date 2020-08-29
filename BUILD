package(default_visibility = ["//visibility:public"])

java_binary(
    name = "example",
    srcs = [
        "java/src/main/io/github/gvacaliuc/example/Example.java",
    ],
    main_class = "io.github.gvacaliuc.example.Example",
    data = [":libtdjni.so"],
    jvm_flags = ["-Djava.library.path=."],
    deps = [
        ":tdclient",
    ],
)

java_library(
    name = "tdclient",
    srcs = glob(["java/src/main/org/**/*.java"]),
)

cc_library(
    name = "tdlib",
    srcs = [
        "@tdlib//:lib/libtdactor.a",
        "@tdlib//:lib/libtdclient.a",
        "@tdlib//:lib/libtdcore.a",
        "@tdlib//:lib/libtddb.a",
        "@tdlib//:lib/libtdjson_private.a",
        "@tdlib//:lib/libtdjson_static.a",
        "@tdlib//:lib/libtdnet.a",
        "@tdlib//:lib/libtdsqlite.a",
        "@tdlib//:lib/libtdutils.a",
    ],
    hdrs = [
        "@tdlib//:include/td/telegram/Client.h",
        "@tdlib//:include/td/telegram/Log.h",
        "@tdlib//:include/td/telegram/td_api.h",
        "@tdlib//:include/td/telegram/td_api.hpp",
        "@tdlib//:include/td/telegram/td_json_client.h",
        "@tdlib//:include/td/telegram/tdjson_export.h",
        "@tdlib//:include/td/telegram/td_log.h",
        "@tdlib//:include/td/tl/tl_jni_object.h",
        "@tdlib//:include/td/tl/TlObject.h",
    ],
    deps= [
        "//tools/jni:copy_jni_hdr_lib",
    ],
)

cc_binary(
    name = "libtdjni.so",
    srcs = ["cpp/td_jni.cpp"],
    deps = [":tdlib"],
    includes = ["external/tdlib/include"],
    copts = ["-std=c++14", "-DPACKAGE_NAME=\\\"org/drinkless/tdlib\\\""],
)
