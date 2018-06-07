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

RULES_SCALA_VERSION = "eeee4679d07eed3a12666361aecbc556047a4f17"

http_archive(
    name = "io_bazel_rules_scala",
    #sha256 = "351f8838716733ae2f3cfb561fa46b9882d47dec7ced780d47f612f7cfb3ef24",
    strip_prefix = "rules_scala-%s" % RULES_SCALA_VERSION,
    urls = ["https://github.com/bazelbuild/rules_scala/archive/%s.zip" % RULES_SCALA_VERSION],
)

load("@io_bazel_rules_scala//scala:scala.bzl", "scala_repositories")
load("@io_bazel_rules_scala//scala:toolchains.bzl", "scala_register_toolchains")
load("@io_bazel_rules_scala//scala_proto:scala_proto.bzl", "scala_proto_repositories")

scala_register_toolchains()

scala_repositories()

scala_proto_repositories()
