# Goals of Aphrodite

- Load and run ELF executables
- Run on many different architectures
- Fail gently under as many circumstances as possible(i.e. not just crash silently when an issue crops up)
- Support primitive software multitasking
- Possible support hardware multitasking
- Load and unload kernel modules on the fly, similar to linux
- Use FAT12, FAT32, btrfs, and/or ext4
- Have everything well documented
- Have good tests for everything
- Be written in rust as much as possible
- Require as few dependencies as possible
- Build quick. May be sacrificied if necessary.
