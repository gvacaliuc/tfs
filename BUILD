load("@rules_foreign_cc//tools/build_defs:cmake.bzl", "cmake_external")

cmake_external(
   name = "tdlib",
   # Values to be passed as -Dkey=value on the CMake command line;
   # here are serving to provide some CMake script configuration options
   cache_entries = {
       "TD_ENABLE_JNI": "ON",
   },
   lib_source = "@tdlib//:all",

   # We are selecting the resulting static library to be passed in C/C++ provider
   # as the result of the build;
   # However, the cmake_external dependants could use other artefacts provided by the build,
   # according to their CMake script
   static_libraries = ["tdlib.a"],
)
