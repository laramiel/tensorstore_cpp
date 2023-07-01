workspace(
    name = "tensorstore_cpp",
)


load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")


###############################################################################
# Bazel Skylib
###############################################################################

http_archive(
    name = "bazel_skylib",
    sha256 = "f24ab666394232f834f74d19e2ff142b0af17466ea0c69a3f4c276ee75f6efce",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-skylib/releases/download/1.4.0/bazel-skylib-1.4.0.tar.gz",
        "https://github.com/bazelbuild/bazel-skylib/releases/download/1.4.0/bazel-skylib-1.4.0.tar.gz",
    ],
)

load("@bazel_skylib//:workspace.bzl", "bazel_skylib_workspace")

bazel_skylib_workspace()

###############################################################################
# Perl
###############################################################################

http_archive(
        name = "rules_perl",
        urls = [
            "https://storage.googleapis.com/tensorstore-bazel-mirror/github.com/bazelbuild/rules_perl/archive/7f10dada09fcba1dc79a6a91da2facc25e72bd7d.tar.gz",  # main(2023-02-02)
        ],
        sha256 = "391edb08802860ba733d402c6376cfe1002b598b90d2240d9d302ecce2289a64",
        strip_prefix = "rules_perl-7f10dada09fcba1dc79a6a91da2facc25e72bd7d",
    )

load("@rules_perl//perl:deps.bzl", "perl_register_toolchains", "perl_rules_dependencies")

perl_rules_dependencies()
perl_register_toolchains()

###############################################################################
# TensorStore
###############################################################################

http_archive(
    name = "tensorstore",
    strip_prefix = "tensorstore-27d221b98073a46b6436aca09bb3cdc578b10d61",
    url = "https://github.com/google/tensorstore/archive/27d221b98073a46b6436aca09bb3cdc578b10d61.tar.gz",
)

load("@tensorstore//:external.bzl", "tensorstore_dependencies")

tensorstore_dependencies()
