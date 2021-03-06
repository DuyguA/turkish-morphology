# Copyright 2019 The Google Research Authors.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

workspace(name = "google_research_turkish_morphology")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# Google protocol buffers.
http_archive(
    name = "com_google_protobuf",
    sha256 = "512e5a674bf31f8b7928a64d8adf73ee67b8fe88339ad29adaa3b84dbaa570d8",
    strip_prefix = "protobuf-3.12.4",
    urls = [
        "https://github.com/protocolbuffers/protobuf/archive/v3.12.4.tar.gz",
    ],
)

load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")

protobuf_deps()

# Bazel Python rules.
http_archive(
    name = "rules_python",
    sha256 = "b6d46438523a3ec0f3cead544190ee13223a52f6a6765a29eae7b7cc24cc83a0",
    urls = [
        "https://github.com/bazelbuild/rules_python/releases/download/0.1.0/rules_python-0.1.0.tar.gz",
    ],
)

# gRpc (only used for detecting and configuring local Python).
http_archive(
    name = "com_github_grpc_grpc",
    sha256 = "58eaee5c0f1bd0b92ebe1fa0606ec8f14798500620e7444726afcaf65041cb63",
    strip_prefix = "grpc-1.33.1",
    urls = [
        "https://github.com/grpc/grpc/archive/v1.33.1.tar.gz",
    ],
)

load(
    "@com_github_grpc_grpc//third_party/py:python_configure.bzl",
    "python_configure",
)

python_configure(name = "local_config_python")

# Google i18n language resources.
http_archive(
    name = "language_resources",
    sha256 = "8e2efff1123c07577c13b01e5ec6123cb02793fcbbc940fe5b70aa7be47f5c92",
    strip_prefix = "language-resources-db54aa5e8dcdd65d22a45124edf6ec009fc7ad7d",
    urls = [
        "https://github.com/google/language-resources/archive/db54aa5.tar.gz",
    ],
)

# OpenFst.
http_archive(
    name = "openfst",
    build_file = "@//third_party:openfst.BUILD",
    sha256 = "eb57e469201b4813479527f0d4661ce3459e282ff7af643613ebe3ea71c79f27",
    strip_prefix = "openfst-1.7.2",
    urls = [
        "https://github.com/mjansche/openfst/archive/1.7.2.tar.gz",
    ],
)

# Thrax.
http_archive(
    name = "thrax",
    build_file = "@//third_party:thrax.BUILD",
    sha256 = "40caa83dc083abdb1b8603a7f74eccb6348877279ab37296a68a570469e3ecfb",
    strip_prefix = "thrax-c65fb3d51f9bd0299503f3289a124f52c3431eeb",
    urls = [
        "https://github.com/mjansche/thrax/archive/c65fb3d.tar.gz",
    ],
)

# PyPi dependencies.
load("@rules_python//python:pip.bzl", "pip_install")

pip_install(
    name = "turkish_morphology_deps",
    requirements = "//:requirements.txt",
)
