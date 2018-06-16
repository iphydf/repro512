workspace(name = "toktok")

# Maven dependencies
# =========================================================

maven_jar(
    name = "org_scalacheck_scalacheck",
    artifact = "org.scalacheck:scalacheck_2.11:1.13.4",
    sha1 = "7845816647d5a80d30e5a71862b31f3fee894549",
)

# Scala toolchain
# =========================================================

RULES_SCALA_VERSION = "1865e6396ff38a9b0c4b435c683d3d7c193c4c0e"

http_archive(
    name = "io_bazel_rules_scala",
    sha256 = "0f0cdfb141304409023d7afaa53235361952e0aa26078c397f9f10b51d6808e6",
    strip_prefix = "rules_scala-%s" % RULES_SCALA_VERSION,
    urls = ["https://github.com/bazelbuild/rules_scala/archive/%s.zip" % RULES_SCALA_VERSION],
)

load("@io_bazel_rules_scala//scala:scala.bzl", "scala_repositories")
load("@io_bazel_rules_scala//scala:toolchains.bzl", "scala_register_toolchains")

scala_register_toolchains()

scala_repositories()
