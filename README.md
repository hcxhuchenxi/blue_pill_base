windows 10
1. Install basic compiler tools
# Install git, if you don't have it
curl -A MS https://webinstall.dev/git | powershell

# Install vcpkg
git clone https://github.com/microsoft/vcpkg
.\vcpkg\bootstrap-vcpkg.bat

2. Install rust
https://rustup.rs for Windows 10.

3. Add the ARM Cortex-M toolchain
rustup target install thumbv7m-none-eabi

4. Install the ftdi USB driver
# Install ftdi
vcpkg install libftdi1:x64-windows-static-md libusb:x64-windows-static-md

5. Install cargo flash for Rust 1.46.0
cargo install cargo-flash
cargo install cargo-embed

6. STLink Driver
https://www.st.com/en/development-tools/stsw-link009.html

6. STLink Firmware Upgrate
https://www.st.com/en/development-tools/stsw-link007.html

7. Build the sample code
cd blue-pill-base

# You have two options:
# A) cargo flash (will build and deploy)
cargo flash --release --chip STM32F103RC

# B) cargo embed (will open debug console)
#    (relies on the Embed.toml)
cargo embed --release

#    (you will need to hit ctrl+c to quit)

