# KUKA FRI Library

#### This repo contains a (slightly) modified version of the KUKA FRI library.

## Compilation with waf

```sh
cd /source/directory
git clone https://github.com/epfl-lasa/kuka_fri.git
cd kuka_fri
./waf configure
./waf
sudo ./waf install
```

The default installation directory is `/usr/local/`. You can change by passing a `--prefix` argument in the configure process: `./waf configure --prefx=/path/to/install/dir`.

## Compilation with CMake

```sh
cd /source/directory
git clone https://github.com/epfl-lasa/kuka_fri.git
cd kuka_fri && mkdir build && cd build
cmake .. && sudo make install
```

## Authors

- Author/Maintainer: Konstantinos Chatzilygeroudis

<!-- ## LICENSE

[CeCILL]

[CeCILL]: http://www.cecill.info/index.en.html -->