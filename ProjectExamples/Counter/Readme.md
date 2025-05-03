![LED Wave Demo]([images-gifs/counter-ez.gif](https://github.com/jhherre3/FPGA-DE10Lite-Archive/blob/main/images-gifs/counter-ez.gif)

# ⏱ Six-Digit Timer – DE10-Lite FPGA Project

This Verilog module implements a **six-digit decimal timer** using a **50 MHz clock** input on the [Terasic DE10-Lite FPGA board](https://www.terasic.com.tw/cgi-bin/page/archive.pl?CategoryNo=234&Language=English&No=1021). The timer counts seconds and displays the result in **BCD (binary-coded decimal)** format across six 7-segment displays.

---

## 📘 Project Overview

This project showcases how to:

- Use **clock division** to generate a 1 Hz signal from a 50 MHz input.
- Implement a **multi-digit BCD counter**.
- Drive **six 7-segment displays** using a BCD to 7-segment decoder.
- Maintain clean modular hardware logic design in Verilog.

This timer can count up to **999999 seconds**, which equals about 11.5 days.

---

## 🧠 How It Works

### 🔁 1. Clock Divider – 50 MHz to 1 Hz

A 26-bit counter (`clk_div`) is used to divide the 50 MHz input clock down to a 1 Hz tick (`one_sec_tick`):

```verilog
if (clk_div == 50_000_000 - 1)
```

Every time this threshold is reached (i.e., every second), a tick is generated and the counter resets.

---

### 🔢 2. BCD Digit Counter

There are 6 BCD digits represented by a 2D register array `digit[5:0]`. On each 1-second tick:

- `digit[0]` (rightmost) increments.
- If any digit overflows (reaches `10`), it resets to 0 and carries over to the next digit.
- Overflow past `999999` is capped at `999999` (optional logic).

---

### 🧮 3. BCD to 7-Segment Decoder

A Verilog `function` maps BCD values to 7-segment display codes:

```verilog
4'd0: bcd_to_7seg = 7'b100_0000; // Displays 0
...
4'd9: bcd_to_7seg = 7'b001_0000; // Displays 9
```

This function drives all six HEX outputs (`HEX0` to `HEX5`), displaying the current count in real time.

---

## 🧪 Demonstrated Concepts

| Concept                       | Description |
|------------------------------|-------------|
| **Clock Division**           | Custom divider to slow down clock speed. |
| **Sequential Logic**         | Uses rising edge of the clock for all counters. |
| **Multi-digit BCD Counting** | Simulates real-world digital timers (like clocks, counters). |
| **Combinational Logic**      | Converts BCD digits to 7-segment display format. |
| **FPGA GPIO Mapping**        | Directly controls HEX outputs on the DE10-Lite board. |

---

## 🔧 Hardware Requirements

- **DE10-Lite FPGA Board**
- **Intel Quartus Prime Lite (16.1 or later)**
- 6 onboard 7-segment HEX displays (HEX0–HEX5)
- 50 MHz system clock (MAX10_CLK1_50 → PIN_P11)

---

## 📂 File Structure

```
six_digit_timer.v       # Verilog source file for timer logic
README.md               # Project documentation (this file)
```

---

## 🧩 Possible Extensions

- Add a **reset button** to reset the counter.
- Add a **pause/resume toggle**.
- Display in **HH:MM:SS** format.
- Add audio or LED indicators for specific times.

---

## 📈 Applications

- Digital clocks
- Event timers
- Lab counters
- Learning exercises for sequential logic and display driving

---

## ✅ Summary

This project provides a clean and functional demonstration of time-based counting and display driving using basic Verilog constructs. It's a great entry point for working with sequential logic, BCD encoding, and interfacing with onboard FPGA peripherals.

> Designed as part of my FPGA learning path with the DE10-Lite. Feel free to fork or expand this timer module into your own clock, stopwatch, or digital display system.
```
