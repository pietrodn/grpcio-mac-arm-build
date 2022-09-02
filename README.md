# `grpcio` Python binary wheels for Apple Silicon

**GitHub Actions workflow: [.github/workflows/wheels.yml](.github/workflows/wheels.yml)**

This repo shows how to build binary wheels for the Python [`grpcio`](https://github.com/grpc/grpc/tree/master/src/python/grpcio) library, for the Apple Silicon architecture.

Currently (version 1.48.1), `grpcio` provides compiled binary wheels only for Intel Macs, not for Apple Silicon machines.
* 👉 [check on PyPI](https://pypi.org/project/grpcio/#files) if the situation changed!

In [this issue](https://github.com/grpc/grpc/issues/29262), I have proposed a way to cross-compile grpcio from an Intel-based CI runner, using the amazing [cibuildwheel](https://github.com/pypa/cibuildwheel) tool.

This repo contains another example, this time using GitHub Actions.