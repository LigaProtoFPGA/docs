# Reference

External documentation the league works from. Vendor manuals and commercial
publications cannot be redistributed, so they are listed here by reference; the files
themselves are held in the league's Drive and are available to members on request.

## Boards

### Spartan-3E Starter Kit

| | |
| --- | --- |
| FPGA | Xilinx XC3S500E |
| Toolchain | ISE. Not supported by Vivado. |
| User guide | UG230 — https://docs.amd.com/v/u/en-US/ug230 |

Two chapters of UG230 matter to us. **Chapter 5, Character LCD**, has the timing
waveforms for the on-board display — the PicoBlaze driver reproduces them in software,
so this is required reading before touching that project. **Chapter 13, DDR SDRAM**, is
the reference for external memory controller work.

The keyboard connector is PS/2, not USB.

### Nexys 1 and Nexys 2

| | |
| --- | --- |
| FPGA | Nexys 1: Xilinx Spartan-3 (xc3s200-4ft256). Nexys 2: Xilinx Spartan-3E (xc3s1200e-4fg320) |
| Clock | 50 MHz |
| Toolchain | ISE 14.7, in a virtual machine ([setup](setup/ise_vm.md)). Not supported by Vivado |

The Nexys 2 has a 4-digit display, 4 buttons and 8 switches, which is why
projects written for it (such as the league's chronometers) use some inputs for more than
one function.

### Nexys A7

See the [Nexys A7 page](boards/nexys_a7.md): part number, reference manual, master XDC and
pin tables.

### Pmod OLED display

Used with the Nexys A7. Two datasheets apply, at different levels, and you need to know
which is which:

- **Solomon Systech SSD1331** — the controller. Defines the command set and timing, and
  is the document a driver is written against.
- **Univision UG-9664HDDAG01** (doc. SAS1-6017-B) — the module. Pinout, mechanical and
  electrical characteristics.

A reference driver for Arduino, developed at PUCRS, was provided by Prof. Ney Calazans.

Both datasheets and the driver are in the Drive.

## Soft processor cores

### PicoBlaze (KCPSM3)

8-bit RISC microcontroller core from Xilinx, by Ken Chapman. Serves as the controller
for the character LCD on the Spartan-3E Starter Kit. Around 96 FPGA slices, and up to
1024 instructions held in a single block RAM, loaded automatically during FPGA
configuration. Supports Spartan-3, Spartan-6, Virtex-5, Virtex-6 and 7 Series.

User guide: UG129 — https://docs.amd.com/v/u/en-US/ug129

The league holds the full **KCPSM3 Release 8a** package in the Drive: VHDL and Verilog
sources, the assembler, UART macros, the JTAG loader and the DATA2MEM utilities. It is
under Xilinx licence and is not published. UG129 is not part of the package — get it
from the link above.

Worth knowing: **DATA2MEM** applies a modified PicoBlaze program directly to an existing
`.bit` file, without re-synthesis.

### MIPS_S

The multi-cycle MIPS32-subset processor by Prof. Ney Calazans. Specification, slides and
VHDL sources are in
[`courses/mips_s_vhdl`](https://github.com/LigaProtoFPGA/courses/tree/main/mips_s_vhdl).

### RISC-V

Reference implementation worth studying for a future port: *RS5-SoC: A Flexible
Open-Source RISC-V Platform for Embedded Systems* — Faccenda et al., PUCRS. An
open-source RISC-V SoC from the same group Profs. Ney and Moraes come from.

## Publications

| Reference | Venue |
| --- | --- |
| U-HAWK: A Hardware-in-the-Loop Framework for Sensor-Rich Embedded Systems Testing — Domingues, Damo, Zilberknop, Bos-Mikich, Filho, Moraes, Ost, Calazans | 32nd IEEE ICECS, 2025 |
| RS5-SoC: A Flexible Open-Source RISC-V Platform for Embedded Systems — Faccenda et al., PUCRS | |

Both are IEEE publications, accessed through IEEE Xplore.

## Books

Held in the Drive; none can be republished.

- *Computer Organization and Design: The Hardware/Software Interface* — Hennessy,
  Patterson. Principal reference for the MIPS_S work. Appendix A, by James Larus, is the
  MIPS assembly reference used in the course.
- *FPGA Prototyping by Verilog Examples* — Pong P. Chu. Practical Verilog reference.
- *Introduction to Verilog* — Altera, 2006.

## Standards

- **IEEE-754** (1985, 2008, 2019) — floating-point representation.
- **MIPS32 Architecture for Programmers, Vols. I–III** — the full architecture MIPS_S
  implements a subset of. Volume II is the instruction set.
- **RISC-V unprivileged and privileged ISA** — freely redistributable.
