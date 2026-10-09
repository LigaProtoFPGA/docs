# Nexys A7

The board most league projects use. It is a rebrand of the Nexys 4 DDR, so Nexys 4 DDR
documentation applies with minimal deviation.

| | |
| --- | --- |
| FPGA | AMD Artix-7 **xc7a100tcsg324-1** (Nexys A7-100T). A 50T variant also exists |
| Toolchain | Vivado ([setup](../setup/vivado.md)). Not supported by the Digilent Adept utility |
| Clock | 100 MHz oscillator on pin **E3** (10 ns period) |
| Reference manual | https://digilent.com/reference/programmable-logic/nexys-a7/reference-manual |
| Master XDC | https://github.com/Digilent/digilent-xdc/blob/master/Nexys-A7-100T-Master.xdc |

## Things that catch everyone the first time

- **The 7-segment display is active-low.** A segment (CA–CG, DP) lights up with `0`, and
  a digit is selected with `0` on its anode (AN0–AN7). Your decoder table has to be
  inverted.
- **The display is multiplexed.** All 8 digits share the same 7 segment wires: light one
  digit at a time and switch about every 1 ms, and the eye sees all of them at once.
- **CPU RESET is active-low** (`CPU_RESETN` reads `0` when pressed). The five other
  buttons read `1` when pressed. LEDs light up with `1`.
- **SW8 and SW9 use `LVCMOS18`**, every other pin here uses `LVCMOS33`. Copy their
  lines from the master XDC instead of editing another switch's line.
- **Buttons bounce.** One press produces several edges for a few milliseconds. Debounce
  any button that drives a counter or a state machine.
- **Port names in the XDC must match the entity's ports.** Use the same spelling in both.
- **The master XDC has every line commented out.** Uncomment only the pins your design
  uses.

## Pins

All `LVCMOS33` unless noted.

### Clock and buttons

| Signal | Pin | Signal | Pin |
| --- | --- | --- | --- |
| CLK100MHZ | E3 | BTNU | M18 |
| CPU_RESETN | C12 | BTNL | P17 |
| BTNC | N17 | BTNR | M17 |
| | | BTND | P18 |

### Switches

| SW | Pin | SW | Pin | SW | Pin | SW | Pin |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | J15 | 4 | R17 | 8 | T8 (`LVCMOS18`) | 12 | H6 |
| 1 | L16 | 5 | T18 | 9 | U8 (`LVCMOS18`) | 13 | U12 |
| 2 | M13 | 6 | U18 | 10 | R16 | 14 | U11 |
| 3 | R15 | 7 | R13 | 11 | T13 | 15 | V10 |

### LEDs

| LED | Pin | LED | Pin | LED | Pin | LED | Pin |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | H17 | 4 | R18 | 8 | V16 | 12 | V15 |
| 1 | K15 | 5 | V17 | 9 | T15 | 13 | V14 |
| 2 | J13 | 6 | U17 | 10 | U14 | 14 | V12 |
| 3 | N14 | 7 | U16 | 11 | T16 | 15 | V11 |

### 7-segment display

| Segment | Pin | Anode | Pin |
| --- | --- | --- | --- |
| CA (a) | T10 | AN0 | J17 |
| CB (b) | R10 | AN1 | J18 |
| CC (c) | K16 | AN2 | T9 |
| CD (d) | K13 | AN3 | J14 |
| CE (e) | P15 | AN4 | P14 |
| CF (f) | T11 | AN5 | T14 |
| CG (g) | L18 | AN6 | K2 |
| DP | H15 | AN7 | U13 |

AN0 is the rightmost digit.

For Pmod connectors, RGB LEDs, VGA, audio, the sensors and the memories, see the master
XDC and the reference manual.

## Example XDC lines

```tcl
## Clock
set_property -dict { PACKAGE_PIN E3  IOSTANDARD LVCMOS33 } [get_ports { CLK100MHZ }];
create_clock -add -name sys_clk_pin -period 10.00 -waveform {0 5} [get_ports { CLK100MHZ }];

## A switch, an LED and a button
set_property -dict { PACKAGE_PIN J15 IOSTANDARD LVCMOS33 } [get_ports { sw[0] }];
set_property -dict { PACKAGE_PIN H17 IOSTANDARD LVCMOS33 } [get_ports { led[0] }];
set_property -dict { PACKAGE_PIN N17 IOSTANDARD LVCMOS33 } [get_ports { BTNC }];
```

Complete, working projects for this board (counter, debounce, display driver, state
machines) are in
[`courses/fpga_intro_saec2026/hdl`](https://github.com/LigaProtoFPGA/courses/tree/main/fpga_intro_saec2026/hdl).
