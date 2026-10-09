# Contributing

How the league's repositories are organized, and the few rules that apply to all of them.

## Where does it go?

Stop at the first yes.

| Question | Where |
| --- | --- |
| Is it about the league itself: setup, boards, how we work? | [`docs`](https://github.com/LigaProtoFPGA/docs) |
| Is it someone else's material we cannot republish (vendor manual, book, paywalled paper)? | An entry in [`reference.md`](reference.md). Never the file itself |
| Is it a complete course, with an instructor and a sequence? | [`courses`](https://github.com/LigaProtoFPGA/courses), one folder per course |
| Does it teach one specific task, doable in an afternoon? | [`tutorials`](https://github.com/LigaProtoFPGA/tutorials) |
| Is it slides or notes on a subject, with no schedule? | [`study_material`](https://github.com/LigaProtoFPGA/study_material) |
| Is it a hardware project the league builds or reuses? | Its own repository (see [projects](#projects)) |
| Is it a personal project nobody else in the league works on or uses? | Your own GitHub account |
| Is it internal: minutes, proposals, personal data? | The league's Drive, not GitHub |

Code written for a course the league runs stays with the course, in `courses`.

## Projects

Each project gets its own repository, so the team working on it controls its history and
the repository can be archived when the work ends. These are the league's projects today:

| Repository | What it is |
| --- | --- |
| [`mips-s-multiplier`](https://github.com/LigaProtoFPGA/mips-s-multiplier) | Booth radix-4 multiplier for the MIPS_S processor, compared with the original serial one |
| [`FPGA-Based-IEEE-754-vs.-Posit-vs.-Takum-Arithmetic-`](https://github.com/LigaProtoFPGA/FPGA-Based-IEEE-754-vs.-Posit-vs.-Takum-Arithmetic-) | Research in progress: IEEE-754, Posit and Takum arithmetic compared in hardware |
| [`vhdl_chronometers`](https://github.com/LigaProtoFPGA/vhdl_chronometers) | Countdown timer and basketball game clock, Nexys 1/2 |
| [`mips_s_text_peripheral`](https://github.com/LigaProtoFPGA/mips_s_text_peripheral) | Memory-mapped peripheral that copies and displays a text on MIPS_S, Nexys 2 |

The last two started as coursework for the Hardware Description Languages course and
stayed in the organization because the league builds on them: the basketball clock, for
example, was ported to the Nexys A7 for the SAEC 2026 mini-course.

A project belongs here when it is league work (a research line, a hardware improvement,
something presented in the league's name) or when other members are expected to build on it. Add it to the table above when you create it.

## Rules for every repository

- **Names:** short, lowercase, no spaces and no accents. Prefer snake_case for new
  repositories, files and folders (`binary_counter`, not `BinaryCounter` or
  `binary counter`). Existing repositories keep their names.
- **Every folder has a `README.md`** saying what is in it and how to use it.
- **Language:** repository documentation is in English. Course material can stay in the
  language it was taught in; say so in the README.
- **Copyright:** never commit vendor documentation, books, paywalled papers or proprietary
  IP. Ask before committing anything you did not write. Removing a file from git history
  is much harder than not adding it.
- **Privacy:** no CPFs, addresses, phone numbers, license server details or private
  documents in a public repository.

## Project layout

A layout that works well for a VHDL or Verilog project (see `mips-s-multiplier`):

```
<project>/
├── README.md   what it does, which board, how to simulate and build
├── rtl/        design sources (.vhd, .v)
├── sim/        testbenches
├── xdc/        constraints
└── docs/       diagrams, results, waveforms
```

When a tool needs files side by side (a testbench that opens a file by relative path, for
example), keep them flat and say why in the README.

In the code, pick one language (English or Portuguese) for names and comments and keep it
throughout the project, and start each file with a short header: what it is, who wrote it,
and when.

## Sending changes

See the [Git guide](setup/git.md). If you cannot push to a repository, ask a board member
to add you as a collaborator.
