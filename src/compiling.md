# How to compile the kernel

## Prerequisites
- [cargo-binutils](https://github.com/rust-embedded/cargo-binutils)
- Rust 1.86.0-nightly
- Bochs (I use 2.8, however any relatively new version should work)
- GRUB (The build script uses `grub-install` and I use `2:2.12-3`, but any version of GRUB 2 should work).

## Actually compiling
1. Set up the config.aphro file in the kernel sub directory(use config.aphro.example as a basis)
2. Clone the repository
3. `cd` into the kernel sub directory of the repository
4. Run `./build`

## Emulation
After compiling the kernel, you should be able to simply run `./emulate`. You can also run `./build_and_emulate` to compile and emulate at once.