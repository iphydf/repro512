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

RULES_SCALA_VERSION = "master"

http_archive(
    name = "io_bazel_rules_scala",
    sha256 = "48c9e1fc6f3dbc58d0971bb7abb104a8f129e69ab0fd2892f67ac2fe5e2c2339",
    strip_prefix = "rules_scala-%s" % RULES_SCALA_VERSION,
    urls = ["https://github.com/bazelbuild/rules_scala/archive/%s.zip" % RULES_SCALA_VERSION],
)

load("@io_bazel_rules_scala//scala:scala.bzl", "scala_repositories")
load("@io_bazel_rules_scala//scala:toolchains.bzl", "scala_register_toolchains")

scala_register_toolchains()

scala_repositories()
