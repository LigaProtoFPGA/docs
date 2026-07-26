# Repository Map

Which repository holds what, and how to decide where something new goes.

## The repositories

Grouped by purpose.

### Learning

| Repository | Holds | Example |
| --- | --- | --- |
| [`tutorials`](https://github.com/LigaProtoFPGA/tutorials) | Guides that teach one specific task, with the reasoning written out | "Blink an LED on the Nexys A7" |
| [`courses`](https://github.com/LigaProtoFPGA/courses) | Complete course material: a sequence, an instructor, a term | Prof. Ney's MIPS_S course |
| `examples` | Working designs to clone and run. Code without narration | Coursework, finished modules, reference implementations |

### Reference

| Repository | Holds | Example |
| --- | --- | --- |
| [`docs`](https://github.com/LigaProtoFPGA/docs) | How the league works, how to set things up, and what external documentation we rely on | "Install Vivado", [`reference.md`](../hardware/reference.md), this map |

### Projects

One repository per project, named `proj_<name>`, owned by the team working on it.

| Repository | Team | Status |
| --- | --- | --- |
| | | |

Separate repositories, rather than one shared one, because each team then controls
write access to its own work, the history stays readable, and a finished project can be
archived without disturbing anything else.

### Institutional

| Repository | Holds |
| --- | --- |
| [`.github`](https://github.com/LigaProtoFPGA/.github) | The organization profile page |

## Where does this go?

Ask the questions in order and stop at the first yes.

1. **Is it about the league itself — how we work, how to set up, our standards?**
   → `docs`

2. **Was it written by someone outside the league, and can we not republish it?**
   (vendor manual, book, paywalled paper)
   → a reference entry in [`reference.md`](../hardware/reference.md). Never the file itself.

3. **Is it a complete course, with a sequence and an instructor?**
   → `courses`

4. **Does it teach one specific task, with the reasoning explained?**
   → `tutorials`

5. **Is it code that works, offered without explanation?**
   → `examples`

6. **Is it ongoing work by a team?**
   → its own `proj_` repository

7. **Is it internal — minutes, proposals, personal data?**
   → Not on GitHub. Drive.

### Cases that trip people up

**A tutorial or an example?** A tutorial teaches — it explains why each step is what it
is, and you read it. An example demonstrates — you clone it and run it. Same code, but
if the explanation is missing on purpose, it is an example.

**A tutorial or a course?** A tutorial is done in an afternoon. A course has a sequence,
a term and someone teaching it.

**A datasheet.** Never committed anywhere. It goes in `reference.md` as an entry, with a
note on which chapter matters, and the file stays in the Drive.

**Code written for a course.** Stays with the course, in `courses`. It moves to
`examples` only if it becomes useful on its own, outside the course.

## Rules that apply everywhere

- **Naming**: snake_case, no spaces, no accents. See the [style guide](style_guide.md).
- **Every folder gets a README.md** saying what is in it.
- **Copyright**: do not commit vendor documentation, books, paywalled papers or
  proprietary IP cores. Ask before committing anything you did not write — removing a
  file from git history is much harder than not adding it.
- **Personal data**: no CPFs, addresses, phone numbers or private documents in any
  public repository.
