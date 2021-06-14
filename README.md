# windows 10
## 1. Install git, if you don't have it
curl -A MS https://webinstall.dev/git | powershell

## 2. Install vcpkg
git clone https://github.com/microsoft/vcpkg
.\vcpkg\bootstrap-vcpkg.bat

## 3. Install rust
https://rustup.rs for Windows 10.

## 4. Add the ARM Cortex-M toolchain
rustup target install thumbv7m-none-eabi

## 5. Install the ftdi USB driver
vcpkg install libftdi1:x64-windows-static-md libusb:x64-windows-static-md

## 6. Install cargo flash
cargo install cargo-flash
cargo install cargo-embed

## 7. STLink Driver
https://www.st.com/en/development-tools/stsw-link009.html

## 8. STLink Firmware Upgrate
https://www.st.com/en/development-tools/stsw-link007.html

## 9. Build the sample code
cd blue-pill-base

## 10. You have two options:
### A) cargo flash (will build and deploy)
cargo flash --release --chip STM32F103RC

### B) cargo embed (will open debug console)
cargo embed --release

### (you will need to hit ctrl+c to quit)

