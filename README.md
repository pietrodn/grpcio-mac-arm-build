# `grpcio` Python binary wheels for Apple Silicon

👩🏻‍💻 **GitHub Actions workflow: [.github/workflows/wheels.yml](.github/workflows/wheels.yml)**

This repo provides daily builds of binary wheels for the Python [`grpcio`](https://github.com/grpc/grpc/tree/master/src/python/grpcio) library, for the Apple Silicon architecture.

A GitHub actions workflow checks every day if there is a new `grpcio` release. If that is the case, it builds the binaries and uploads them in a new [release](https://github.com/pietrodn/grpcio-mac-arm-build/releases).

📦 **[Releases](https://github.com/pietrodn/grpcio-mac-arm-build/releases)**

## Motivation

Currently (version 1.48.1), `grpcio` provides compiled binary wheels only for Intel Macs, not for Apple Silicon machines.
* 👉 [check on PyPI](https://pypi.org/project/grpcio/#files) if the situation changed!

Google Cloud's client libraries for Python depend on `grpcio`, and without a binary release of `grpcio` it becomes hard to install them on a local development environment.

😰 Not having a binary wheel for `grpcio` severely impairs the developer experience of M1/M2 Mac users: when they do `pip install grpcio`, pip downloads for them the source tarball and attempts to compile the library.

Compiling grpcio on Mac is slow, and [notoriously hard](https://github.com/grpc/grpc/issues/25082) and, in my experience, users become frustrated after the 10th attempt with some combination of environment variables, dependencies, and compilation flags (`brew install` random stuff, `LDFLAGS`, `CFLAGS`, `GRPC_PYTHON_BUILD_SYSTEM_OPENSSL`, ...). A downloadable binary wheel would enable a much more pleasant user experience.

In [this issue](https://github.com/grpc/grpc/issues/29262), I proposed a way to cross-compile grpcio from an Intel-based CI runner, using the amazing [cibuildwheel](https://github.com/pypa/cibuildwheel) tool.

This repo contains another example, that uses GitHub Actions.


## Licensing

The [grpc](https://github.com/grpc/grpc/blob/master/LICENSE) project is licensed under the Apache License 2.0, BSD 3-Clause License, and Mozilla Public License Version 2.0. You can find the updated license text [at this link](https://github.com/grpc/grpc/blob/master/LICENSE).

These binaries are provided by me personally and not endorsed by the original authors of the grpc library, nor the company I work for.
The binaries are released under the same license terms of the original source code.

No guarantees of any sort are provided: use this software at your own risk!
