workspace(name = "toktok")

# Protobuf
# =========================================================

# proto_library rules implicitly depend on @com_google_protobuf//:protoc,
# which is the proto-compiler.
# This statement defines the @com_google_protobuf repo.
http_archive(
    name = "com_google_protobuf",
    sha256 = "4ffd420f39f226e96aebc3554f9c66a912f6cad6261f39f194f16af8a1f6dab2",
    strip_prefix = "protobuf-3.5.2",
    urls = ["https://github.com/google/protobuf/archive/v3.5.2.tar.gz"],
)

# Maven dependencies
# =========================================================

maven_jar(
    name = "com_google_guava_guava",
    artifact = "com.google.guava:guava:19.0",
    sha1 = "6ce200f6b23222af3d8abb6b6459e6c44f4bb0e9",
)

maven_jar(
    name = "com_intellij_annotations",
    artifact = "com.intellij:annotations:12.0",
    sha1 = "bbcf6448f6d40abe506e2c83b70a3e8bfd2b4539",
)

maven_jar(
    name = "com_typesafe_scala_logging_scala_logging",
    artifact = "com.typesafe.scala-logging:scala-logging_2.11:3.7.2",
    sha1 = "5015fe84c5aec4f8eb3daa2d1663d447d65f8c02",
)

maven_jar(
    name = "junit_junit",
    artifact = "junit:junit:4.12",
    sha1 = "2973d150c0dc1fefe998f834810d68f278ea58ec",
)

maven_jar(
    name = "log4j_log4j",
    artifact = "log4j:log4j:1.2.17",
    sha1 = "5af35056b4d257e4b64b9e8069c0746e8b08629f",
)

maven_jar(
    name = "org_apache_commons_commons_lang3",
    artifact = "org.apache.commons:commons-lang3:3.4",
    sha1 = "5fe28b9518e58819180a43a850fbc0dd24b7c050",
)

maven_jar(
    name = "org_bytedeco_javacpp",
    artifact = "org.bytedeco:javacpp:1.4",
    sha1 = "6e9062d70f863a4e55b3827d42d302f94e89d7e5",
)

maven_jar(
    name = "org_bytedeco_javacpp_presets_ffmpeg",
    artifact = "org.bytedeco.javacpp-presets:ffmpeg:3.4.1-1.4",
    sha1 = "bf46f2d74014475c948f1a8e063fae50ab724520",
)

maven_jar(
    name = "org_bytedeco_javacpp_presets_opencv",
    artifact = "org.bytedeco.javacpp-presets:opencv:3.4.0-1.4",
    sha1 = "b82eeed2295f30369044b2520937d764efeb3e1e",
)

maven_jar(
    name = "org_bytedeco_javacv",
    artifact = "org.bytedeco:javacv:1.4",
    sha1 = "c443d8c648fb7e53428837e469ced47369a297af",
)

maven_jar(
    name = "org_bytedeco_javacv_platform",
    artifact = "org.bytedeco:javacv-platform:1.4",
    sha1 = "9a674bb8266e02f6c85b6f5644b7eab13119f14e",
)

maven_jar(
    name = "org_scalacheck_scalacheck",
    artifact = "org.scalacheck:scalacheck_2.11:1.13.4",
    sha1 = "7845816647d5a80d30e5a71862b31f3fee894549",
)

maven_jar(
    name = "org_scalactic_scalactic",
    artifact = "org.scalactic:scalactic_2.11:2.2.6",
    sha1 = "f7307ba050244832ae5751b221493cb923942984",
)

maven_jar(
    name = "org_slf4j_slf4j_api",
    artifact = "org.slf4j:slf4j-api:1.7.25",
    sha1 = "da76ca59f6a57ee3102f8f9bd9cee742973efa8a",
)

maven_jar(
    name = "org_slf4j_slf4j_android",
    artifact = "org.slf4j:slf4j-android:1.7.22",
    sha1 = "74825860214ed889b38d0fc865b89af18f4e95a7",
)

maven_jar(
    name = "org_slf4j_slf4j_log4j12",
    artifact = "org.slf4j:slf4j-log4j12:1.7.22",
    sha1 = "3bb94b26c2ad2f8755302aa9bf96f03b23a76639",
)

# Scala toolchain
# =========================================================

#RULES_SCALA_VERSION = "4afc7abc73e4fb688e7c95e7aec43005feb44b0b"
RULES_SCALA_VERSION = "eeee4679d07eed3a12666361aecbc556047a4f17"

http_archive(
    name = "io_bazel_rules_scala",
    #sha256 = "351f8838716733ae2f3cfb561fa46b9882d47dec7ced780d47f612f7cfb3ef24",
    strip_prefix = "rules_scala-%s" % RULES_SCALA_VERSION,
    urls = ["https://github.com/bazelbuild/rules_scala/archive/%s.zip" % RULES_SCALA_VERSION],
)
#RULES_SCALA_VERSION = "1d31d255e5f1e5d40bb27c8b3cf71f3741d69be3"
#
#http_archive(
#    name = "io_bazel_rules_scala",
#    sha256 = "2402bf9a4624d8557f7fd8e457e65d677e900345759f719a24d27241767623d5",
#    strip_prefix = "rules_scala-%s" % RULES_SCALA_VERSION,
#    urls = ["https://github.com/bazelbuild/rules_scala/archive/%s.zip" % RULES_SCALA_VERSION],
#)

load("@io_bazel_rules_scala//scala:scala.bzl", "scala_repositories")
load("@io_bazel_rules_scala//scala:toolchains.bzl", "scala_register_toolchains")
load("@io_bazel_rules_scala//scala_proto:scala_proto.bzl", "scala_proto_repositories")

scala_register_toolchains()

scala_repositories()

scala_proto_repositories()

git_repository(
    name = "gmaven_rules",
    commit = "3f430f197ff1c96ec7a4794a2b9f81c521dc65fe",
    remote = "https://github.com/aj-michael/gmaven_rules",
)

load("@gmaven_rules//:gmaven.bzl", "gmaven_rules")

gmaven_rules()
