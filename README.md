# DE10-Lite FPGA Projects

Welcome to my FPGA project collection using the [DE10-Lite development board](https://www.terasic.com.tw/cgi-bin/page/archive.pl?Language=English&CategoryNo=205&No=1046). This repository is designed to serve as both a personal learning journey and a showcase of practical applications using Verilog and the Quartus development environment.

## 📘 About This Repository

This project archive is focused on learning and demonstrating the capabilities of Field-Programmable Gate Arrays (FPGAs) using the DE10-Lite, a low-cost board based on the Intel MAX 10 FPGA. All designs are coded in **Verilog**, a hardware description language used to model digital systems.

The goal of this repository is to:
- Practice digital design fundamentals and FPGA workflows
- Understand how to configure and use FPGA hardware (via switches, LEDs, clocks, etc.)
- Build up a library of example projects showing real-world applications
- Document and reinforce core FPGA concepts such as sequential logic, state machines, timing, and synthesis

## 🔧 Tools Used

- **Board**: Terasic DE10-Lite (Intel MAX 10 FPGA)
- **Language**: Verilog HDL
- **IDE**: Quartus Prime Lite Edition
- **Programmer**: USB-Blaster

## 📂 Project List

Each folder inside `projects/` contains a complete Quartus project with:
- `source/` – Verilog files and/or block diagrams
- `project.qpf` and `project.qsf` – Project files and pin assignments
- `README.md` – Description and instructions for the project

## 🧠 What You'll Learn

By exploring these projects, you can gain experience with:
- FPGA toolchain (synthesis, fitting, timing analysis, programming)
- Using Verilog for RTL (Register-Transfer Level) design
- Pin mapping and constraint files (`.qsf`)
- Using switches, LEDs, and clocks on the DE10-Lite board
- Designing combinational and sequential logic circuits
- Modularity and reuse of code blocks

## 📎 Getting Started

To try out a project:
1. Open Quartus Prime Lite Edition
2. Navigate to a `project/` folder (e.g., `projects/blinking_led`)
3. Open the `.qpf` file to launch the project
4. Assign FPGA pins via `Assignments > Pin Planner` if needed
5. Compile and program the board using the USB-Blaster

## 📚 Further Resources

- [Nandland FPGA tutorials](https://www.nandland.com/)
- [Digital Design and Computer Architecture – Harris & Harris](https://www.amazon.com/dp/0128200650)
- [Terasic DE10-Lite User Manual](https://www.terasic.com.tw/cgi-bin/page/archive_download.pl?Language=English&No=1046&FID=5f7d4a0b05d30de1)

---

Stay tuned as I continue adding new designs and documenting more advanced concepts.

