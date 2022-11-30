# daedalus
After developing a few emulators, completing [nand2tetris](https://www.nand2tetris.org/), gaining some embedded software experience, and finally consuming the [Operating Systems: Three Easy Pieces](https://pages.cs.wisc.edu/~remzi/OSTEP/) textbook, I feel like I now have the building blocks to write my own simple operating system. Since this will be meant as a learning experience, it will not offer anything an existing OS doesn't already offer, but hopefully it will be fun regardless.

## Plan
Since I already have some background in ARM architecture, and will likely continue to work with ARM in the future, I'd like for this OS to target ARM-based devices. Having said that, developing specifically for the Raspberry Pi seems like the natural choice since it's powerful enough to actually support a multitasking OS while still being cheap to work with.

I want to keep this as minimal as possible at first, so that I can at least have something resembling a modern OS without getting overwhelmed with all the true complexity found in something like Linux and Windows. Thus I decided on these core features:

- Basic round-robin scheduler that spaces time between tasks equally  
- Simple virtual memory model that uses base/bounds concepts  
- Provides a basic file-system for an SD card  
- Single-core support only  
- Serial interface with minimal shell

In the future I'd hopefully experiment with things such as a more optimal scheduling algorithm, full-blown memory paging, multi-threading support, etc but baby steps first.

## Steps
1. Find a Raspberry Pi (which seems impossible nowadays) or get an emulator such as QEMU working.
2. Get a bit more familiar with the ARM archiecture and see specifically what OS-related hardware support is available.
3. Get a simple bare-metal C program running on the Pi which can communicate over UART/serial.
4. Implement an ASM/C startup file that sets up interrupts, timers, etc.
5. Implement context-switching (saving/loading CPU state).
6. Implement the scheduler.
7. Implement the virtual memory model.
8. Implement a simple shell.
9. Implement the file system.

Ultimately these steps/plans are likely to change as I encounter many road-blocks and problems along the way.
