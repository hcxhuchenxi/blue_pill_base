# windows 10 and VSCode
## 1. Install git, if you don't have it
curl -A MS https://webinstall.dev/git | powershell

## 2. Install vcpkg
git clone https://github.com/microsoft/vcpkg
.\vcpkg\bootstrap-vcpkg.bat

## 3. Install OpenOCD
https://gnutoolchains.com/arm-eabi/openocd/

## 4. Install gcc-arm-none-eabi toolchain
https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads

## 5. Install rust
https://rustup.rs for Windows 10.

## 6. Add the ARM Cortex-M toolchain
rustup target install thumbv7m-none-eabi

## 7. Install the ftdi USB driver
vcpkg install libftdi1:x64-windows-static-md libusb:x64-windows-static-md

## 8. Install cargo flash
cargo install cargo-flash
cargo install cargo-embed

## 9. STLink Driver
https://www.st.com/en/development-tools/stsw-link009.html

## 10. STLink Firmware Upgrate
https://www.st.com/en/development-tools/stsw-link007.html

## 11. Build the sample code
cd blue-pill-base

## 12. You have two options:
### A) cargo flash (will build and deploy)
cargo flash --release --chip STM32F103RC

### B) cargo embed (will open debug console)
cargo embed --release

### (you will need to hit ctrl+c to quit)

