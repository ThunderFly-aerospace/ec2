# EC2 Debug Tools

**EC2 Tools** provide Linux and macOS support for the Silicon Laboratories EC2 serial debug adapter. This software includes command-line utilities for interacting with EC2-based microcontrollers, including reading/writing flash memory and basic debugging.

## Features

- Support for Silicon Labs [EC2 serial debug adapters](https://www.silabs.com/development-tools/mcu/8-bit/8-bit-usb-debug-adapter?tab=overview)
- Command-line tools:
  - `ec2readflash` – read target flash memory
  - `ec2writeflash` – write to target flash memory
  - `ec2device` – identify connected device
  - `ec2test-any` – test debugger/microcontroller combination
- `newcdb`: Enhanced GDB-like debugger frontend with readline support

## Requirements

### Ubuntu / Debian

```bash
sudo apt-get install libreadline-dev libusb-dev libboost-regex-dev cmake python2
````

### macOS

Install dependencies via Homebrew or MacPorts:

```bash
brew install boost libusb
```

> For MacPorts, you may need to set:
>
> ```bash
> export CFLAGS=-I/opt/local/include
> export LDFLAGS=-L/opt/local/lib
> ```

## Building from Source

```bash
git clone git@github.com:ThunderFly-aerospace/ec2.git
cd ec2
mkdir build
cd build
cmake ../src
make
```

You can run the binaries directly from the build directory without installation:

```bash
./ec2tools/ec2readflash --help
```

## Usage

Basic usage example to read flash:

```bash
./ec2tools/ec2readflash -d /dev/ttyUSB0 -o output.hex
```

Replace `/dev/ttyUSB0` with your actual device.

## License

This project is provided under an open-source GPL 2 license (check `COPYING` file for details).


