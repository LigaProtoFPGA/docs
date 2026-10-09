# Which software do I need?

It depends on the board.

| Board | FPGA | Toolchain | Runs on | Guide |
| --- | --- | --- | --- | --- |
| Nexys A7 | Artix-7 | Vivado | Windows or Linux | [Vivado](vivado.md) |
| Nexys 1 / Nexys 2 | Spartan-3 / Spartan-3E | ISE 14.7, inside a virtual machine | Windows (the guide is written for Windows hosts) | [ISE VM](ise_vm.md) |

Vivado does not support Spartan-3 or Spartan-3E devices, which is why the older boards
need ISE.

Neither tool runs natively on macOS. On a Mac, use the lab PCs.

Everyone also needs Git: see the [Git guide](git.md).
