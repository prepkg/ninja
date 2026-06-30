# Ninja

[![GitHub Release](https://img.shields.io/github/v/release/prepkg/ninja)](https://github.com/prepkg/ninja/releases/latest)
[![License](https://img.shields.io/github/license/prepkg/ninja)](https://github.com/prepkg/ninja/blob/master/LICENSE)

This repository provides precompiled [Ninja](https://github.com/ninja-build/ninja) binaries for Linux. The binaries
are compiled with the [GCC Toolchain](https://github.com/prepkg/gcc-toolchain) targeting older glibc versions and musl,
ensuring compatibility across a wide range of Linux distributions. GitHub CI workflows are used to automate the build
process: pipelines run daily, but new builds are triggered only when a new Ninja release is available.

## Build Information

* GNU targets are dynamically linked with an older glibc version; musl targets are fully statically linked.
  For details, see the [GCC Toolchain](https://github.com/prepkg/gcc-toolchain).
* Statically linked with libstdc++ and libgcc.

## Precompiled Binaries

If you prefer not to build the Ninja yourself, a precompiled Ninja for each supported architecture can be
downloaded from the [releases page](https://github.com/prepkg/ninja/releases).

Replace `<target>` with one of: `x86_64-linux-gnu`, `x86_64-linux-musl`, `aarch64-linux-gnu`, `aarch64-linux-musl`,
`arm-linux-gnueabi`, `riscv64-linux-gnu`.

```shell
curl -sSL https://github.com/prepkg/ninja/releases/latest/download/ninja-<target>.tar.gz | sudo tar xz -C /usr/local/bin
```

For example:

```shell
curl -sSL https://github.com/prepkg/ninja/releases/latest/download/ninja-x86_64-linux-gnu.tar.gz | sudo tar xz -C /usr/local/bin
```

## Compilation

* Clone the repository:

```shell
git clone https://github.com/prepkg/ninja.git && cd ninja
```

* Build the Docker image:

```shell
./setup.sh build-image
```

* Build the application:

```shell
./setup.sh build-app
```

After compilation, the `tar.gz` for each architecture will be available in the `build` directory.
