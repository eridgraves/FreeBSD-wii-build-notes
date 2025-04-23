# FreeBSD-wii-build-notes
Notes from building FreeBSD for Wii, on a Linux Host.

## Resources
- [FreeBSD/Wii](https://wiki.freebsd.org/Wii) - existing instructions for build on BSD.
- [Handbook 26.8. Building on non-FreeBSD Hosts](https://docs.freebsd.org/en/books/handbook/cutting-edge/#building-on-non-freebsd-hosts) - instructions on building FreeBSD on Linux/mac host.

## Build Process
1. Clone FreeBSD Sources - `git clone -b releng/14.2 https://git.freebsd.org/src.git`
2. Ensure build prerequisites are set/known:
   - llvm is installed (including ld).
   - Make a freebsd object directory.
   - Wii HW is 32 bit powerpc architecture.
3. Run the build using the **make.py** script - `MAKEOBJDIRPREFIX=$HOME/freebsd-obj ./tools/build/make.py buildworld KERNCONF=WII TARGET=powerpc TARGET_ARCH=powerpc --cross-bindir=/usr/lib/llvm-14/bin`

# Host Specs
```
Linux eric-desktop 6.8.0-57-generic #59~22.04.1-Ubuntu SMP PREEMPT_DYNAMIC Wed Mar 19 17:07:41 UTC 2 x86_64 x86_64 x86_64 GNU/Linux

MemTotal:       131579876 kB

Architecture:             x86_64
  CPU op-mode(s):         32-bit, 64-bit
  Address sizes:          46 bits physical, 48 bits virtual
  Byte Order:             Little Endian
CPU(s):                   28
  Model name:             13th Gen Intel(R) Core(TM) i7-13850HX
    Thread(s) per core:   2
    CPU max MHz:          5300.0000
```
