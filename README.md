# arm-cortex_a7-linux-gnueabihf
crosstool-ng config for Cortex A7 CPU / Rust Arm v7 target (armv7-unknown-linux-gnueabihf)

This is intended for linking cross-compiled Rust `armv7-unknown-linux-gnueabihf` on macOS/Linux. Add it to your [crosstool-ng](https://github.com/crosstool-ng/crosstool-ng) samples folder.

### For original Raspberry Pi or Zero

```
$ rustup target install arm-unknown-linux-gnueabi
$ ct-ng arm-cortex_a7-linux-gnueabihf
$ ct-ng menuconfig -> set all path to your preconfigured /Volume 
$ ct-ng build
```
[Detailed guide for MacOS](https://medium.com/coinmonks/setup-gcc-8-1-cross-compiler-toolchain-for-raspberry-pi-3-on-macos-high-sierra-cb3fc8b6443e)

### Rust


`.cargo/config`
```toml
[target.armv7-unknown-linux-gnueabihf]
linker = "/Volumes/crosstool-ng/x-tools/arm-cortex_a7-linux-gnueabihf/bin/arm-cortex_a7-linux-gnueabihf-gcc"
```

```
$ rustup target install armv7-unknown-linux-gnueabihf
$ cargo build --target armv7-unknown-linux-gnueabihf
```

