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
| Is it a project worked on by a league team? | Its own repository, named `proj_<name>` |
| Is it your own coursework or a personal project? | Your own GitHub account |
| Is it internal: minutes, proposals, personal data? | The league's Drive, not GitHub |

Code written for a course stays with the course.

## Rules for every repository

- **Names:** snake_case, no spaces, no accents (`binary_counter`, not `BinaryCounter` or
  `binary counter`).
- **Every folder has a `README.md`** saying what is in it and how to use it.
- **Language:** repository documentation is in English. Course material can stay in the
  language it was taught in; say so in the README.
- **Copyright:** never commit vendor documentation, books, paywalled papers or proprietary
  IP. Ask before committing anything you did not write. Removing a file from git history
  is much harder than not adding it.
- **Privacy:** no CPFs, addresses, phone numbers, license server details or private
  documents in a public repository.

## Hardware projects

A layout that works well for a VHDL or Verilog project:

```
proj_<name>/
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
