# sdb

Building a Debugger, write a native x64 debugger from scratch, by Sy Brand

## Install and initialize vcpkg
```bash
$ cd ~
$ git clone https://github.com/microsoft/vcpkg.git
$ ./vcpkg/bootstrap-vcpkg.sh
```

This install the vcpkg repo in the home directory and add `~/vcpkg` directory to the `PATH` environmet variable. This only need to be done once.


## Build and run
```bash
$ cmake -B build
$ cmake --build build
$ ./tools/sdb
```

To get access to vcpkg a more complicated `cmake -B build` command is needed:

    $ cmake -B build --fresh -DCMAKE_TOOLCHAIN_FILE=$HOME/vcpkg/scripts/buildsystems/vcpkg.cmake

Save this file in a bashcript, eg `do_cmake_gen_fresh.sh`

```bash
#!/bin/bash

cmake -B build --fresh -DCMAKE_TOOLCHAIN_FILE=$HOME/vcpkg/scripts/buildsystems/vcpkg.cmake
```

and change file to executable:

    $ chmod +x do_cmake_gen_fresh.sh

