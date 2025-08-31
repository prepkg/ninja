# Ninja

This repository provides precompiled [Ninja](https://github.com/ninja-build/ninja) binaries for Linux. The binaries
are compiled with the [GCC Toolchain](https://github.com/prepkg/gcc-toolchain) targeting older glibc versions, ensuring
compatibility across a wide range of Linux distributions. GitHub CI workflows are used to automate the build process:
pipelines run daily, but new builds are triggered only when a new Ninja release is available.

## Build Information

* Dynamically linked with old glibc version. For details, see the [GCC Toolchain](https://github.com/prepkg/gcc-toolchain).
* Statically linked with libstdc++ and libgcc.

## Precompiled Binaries

If you prefer not to build the Ninja yourself, a precompiled Ninja for each supported architecture can be
downloaded from the [releases page](https://github.com/prepkg/ninja/releases).

* x86_64-linux-gnu:

```shell
sudo curl -sSLo /usr/local/bin/ninja https://github.com/prepkg/ninja/releases/latest/download/ninja-x86_64-linux-gnu
sudo chmod a+x /usr/local/bin/ninja
```

* aarch64-linux-gnu:

```shell
sudo curl -sSLo /usr/local/bin/ninja https://github.com/prepkg/ninja/releases/latest/download/ninja-aarch64-linux-gnu
sudo chmod a+x /usr/local/bin/ninja
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

After compilation, the binaries for each architecture will be available in the `build` directory.
