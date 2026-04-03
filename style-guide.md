# Style Guide - VHDL/Verilog and Repository

This guide provides a suggested structure for organizing projects within the repository. While not mandatory to follow strictly, maintaining a common pattern improves navigation and collaboration for everyone.

---

## Repository Folder Structure

- `/tutorials` — step-by-step introductory guides
- `/examples` — ready-to-run example projects
- `/templates` — standard templates for new projects
- `/docs` — general league documentation
- `/resources` — shared resources (drivers, IPs for Ethernet, displays, etc.)

Every folder should ideally contain a **README.md** file explaining its contents.

---

## File and Folder Naming

- Use **snake_case** — lowercase letters separated by underscores.
- Avoid spaces, accents, or special characters.

✅ `binary_counter`
✅ `adder_4bits`
✅ `vhdl_intro_tutorial`

❌ `BinaryCounter`
❌ `adder 4 bits`
❌ `Intro-Tutorial`

---

## Project Structure

Suggested organization for individual projects:

- `/project_name`
    - `README.md` — project description and usage
    - `src/` — source files (.vhd or .v)
    - `sim/` — simulation files (testbenches)
    - `constraints/` — constraint files (.xdc or .sdc)

---

## README Template for Projects

Suggested model for your project's **README.md**:

# Project Name

## Description
A 2-3 line summary of what this project does.

## Board
Example: Nexys A7 (Artix-7)

## Language
VHDL / Verilog

## How to Simulate
Steps to run the simulation (e.g., in Vivado or ModelSim).

## How to Synthesize
Steps to generate the bitstream and program the board.

## Author
Name — Date

---

## Coding Conventions

**Entity and Module Names**
Use snake_case with descriptive names. Choose one language (English or Portuguese) and maintain it throughout the project.

✅ `entity binary_counter is`
✅ `module adder_4bits`

**Indentation**
Use 2 or 4 spaces. Pick one and remain consistent throughout the file. Avoid mixing spaces and tabs.

**Comments**
Include a header comment at the top of every file:

```vhdl
-- Project: 4-bit Binary Counter
-- Author: Your Name
-- Date: DD/MM/YYYY
-- Description: Synchronous counter with asynchronous reset
