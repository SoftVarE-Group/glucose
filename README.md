# Glucose SAT solver

This is the release 3.0 of the glucose SAT solver. 
It is based on [Minisat 2.2][minisat]

## Installation

### Prerequisites

 - [CMake][cmake]
 - [zlib][zlib]

### Building

Configure the project to build in the directory `build` (which will be created):

```
cmake -B build
```

Optionally, a generator (such as [Ninja][ninja]) can be specified:

```
cmake -G Ninja -B build
```

Once configured, build the project:

```
cmake --build build
```

By default, the `glucose` binary is not built.
To build it, pass `--target binary` to the build process:

```
cmake --build build --target binary
```

## Usage

To run the binary, use:

```
./build/glucose BENCHNAME
```

[minisat]: http://minisat.se/MiniSat.html
[cmake]: https://cmake.org
[zlib]: https://zlib.net
[ninja]: https://github.com/ninja-build/ninja
