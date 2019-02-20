workspace(name = "org_dnosproject_dnos_tools_python")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")


load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

git_repository(
    name = "io_bazel_rules_python",
    remote = "https://github.com/bazelbuild/rules_python.git",
    commit = "a558949cce478e537c6474c3bc5848a7d90e42c0",
)

# Only needed for PIP support:
load("@io_bazel_rules_python//python:pip.bzl", "pip_import","pip_repositories")

pip_repositories()


## Python third-party libraries


### Python third part libraries
## python-openflow library
pip_import(
    name = "python-openflow",
    requirements = "//:requirements.txt",
)

load("@python-openflow//:requirements.bzl", _python_openflow_install = "pip_install")

_python_openflow_install()


## Ryu
pip_import(
    name="ryu",
    requirements = "//:requirements.txt"
)
load("@python-openflow//:requirements.bzl", _ryu_install = "pip_install")

_ryu_install()