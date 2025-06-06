# Copyright 2018 The JAX Authors.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     https://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

load(
    "//jaxlib:jax.bzl",
    "jax2tf_deps",
    "py_deps",
)

licenses(["notice"])

package(
    default_applicable_licenses = [],
    default_visibility = ["//visibility:private"],
)

py_library(
    name = "jax2tf",
    srcs = ["__init__.py"],
    srcs_version = "PY3",
    visibility = ["//visibility:public"],
    deps = [":jax2tf_internal"],
)

py_library(
    name = "jax_export",
    srcs = [
        "jax_export.py",
        "shape_poly.py",
    ],
    srcs_version = "PY3",
    # TODO: b/255503696: enable pytype
    tags = ["pytype_unchecked_annotations"],
    visibility = ["//visibility:public"],
    deps = [
        "//jax",
    ] + py_deps("numpy"),
)

py_library(
    name = "jax2tf_internal",
    srcs = [
        "call_tf.py",
        "impl_no_xla.py",
        "jax2tf.py",
    ],
    srcs_version = "PY3",
    # TODO: b/255503696: enable pytype
    tags = ["pytype_unchecked_annotations"],
    deps = [
        ":jax_export",
        "//jax",
    ] + py_deps("numpy") + py_deps("tensorflow_core") + jax2tf_deps,
)
