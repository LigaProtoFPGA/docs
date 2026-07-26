# Repository Map

Which repository holds what, and how to decide where something new goes.

## The repositories

Grouped by purpose.

### Learning

| Repository | Holds | Example |
| --- | --- | --- |
| [`tutorials`](https://github.com/LigaProtoFPGA/tutorials) | Guides that teach one specific task, with the reasoning written out | "Blink an LED on the Nexys A7" |
| [`courses`](https://github.com/LigaProtoFPGA/courses) | Complete course material: a sequence, an instructor, a term | Prof. Ney's MIPS_S course |
| [`study_material`](https://github.com/LigaProtoFPGA/study_material) | Lecture slides and reference material on a subject. No schedule, no sequence | Prof. Ney's slides on caches, pipelines and computer arithmetic |

### Reference

| Repository | Holds | Example |
| --- | --- | --- |
| [`docs`](https://github.com/LigaProtoFPGA/docs) | How the league works, how to set things up, and what external documentation we rely on | "Install Vivado", [`reference.md`](../hardware/reference.md), this map |

### Projects

One repository per project, named `proj_<name>`, owned by the team working on it. The
prefix keeps them together in the
[Repositories](https://github.com/orgs/LigaProtoFPGA/repositories) tab, so there is no
list to maintain anywhere.

Separate repositories, rather than one shared one, because each team then controls write
access to its own work, the history stays readable, and a finished project can be
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

5. **Does it teach a subject, with no schedule attached — slides, notes, reference
   presentations?**
   → `study_material`

6. **Is it work by a league team?**
   → its own `proj_` repository

7. **Is it your own coursework, or a personal project?**
   → your own GitHub account. It is your work, not the league's.

8. **Is it internal — minutes, proposals, personal data?**
   → Not on GitHub. Drive.

### Cases that trip people up

**A tutorial or a course?** A tutorial is done in an afternoon. A course has a sequence,
a term and someone teaching it.

**A course or study material?** A course is something the league runs: it has an
instructor, a term and a sequence you work through. Study material is a library — slides
and notes you consult when a project needs the subject. Same author, different use.

**A datasheet.** Never committed anywhere. It goes in `reference.md` as an entry, with a
note on which chapter matters, and the file stays in the Drive.

**Code written for a course.** Stays with the course, in `courses`.

**A league project or your own work?** A league project is worked on by a team and
outlives whoever started it — it belongs in the organization. Coursework and personal
projects stay in the author's own account, where the contribution history stays with
them. Members can pin organization repositories to their personal profile, so working on
a league project is visible there too.

## Rules that apply everywhere

- **Naming**: snake_case, no spaces, no accents. See the [style guide](style_guide.md).
- **Every folder gets a README.md** saying what is in it.
- **Copyright**: do not commit vendor documentation, books, paywalled papers or
  proprietary IP cores. Ask before committing anything you did not write — removing a
  file from git history is much harder than not adding it.
- **Personal data**: no CPFs, addresses, phone numbers or private documents in any
  public repository.
