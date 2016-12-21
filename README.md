# RISC-V GNU Compiler Toolchain with Xvec Extension Support

## Author

* André Bannwart Perina
* Guilherme Bileki

## Introduction

This is a fork from riscv-llvm project (https://github.com/riscv/riscv-gnu-toolchain), with
support to Xvec instructions. This means that the GNU assembler and linker will recognise
assembly files (.s) with instructions such as ```addv```, ```subv```, etc. An implementation
of an Xvec-enabled RISC-V processor is available at https://github.com/comododragon/vscale.

## Licence

This project holds the original licence from the original project (see LICENSE file).

## Installation

1. Get the repositories:

	```
	$ git clone https://github.com/riscv/riscv-gnu-toolchain
	$ cd riscv-gnu-toolchain
	$ git submodule update --init --recursive
	```

2. Install needed packages. For example, in Ubuntu:

	```
	$ sudo apt-get install autoconf automake autotools-dev curl libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc
	```

3. In order to compile files to the RV32IXvec architecture of VScale, compile for 32-bit:

	```
	./configure --prefix=/path/to/install --with-arch=rv32g --with-abi=ilp32d
	make linux
	```

	Where ```/path/to/install``` is your desired installation folder.

4. After compilation, 32-bit GNU binaries will have the ```riscv32-unknown-linux-gnu-``` prefix.

Refer to the original repository documentation for further instructions on how to compile and use.
The original ```README.md``` for this repository is available as ```README.orig.md```.
