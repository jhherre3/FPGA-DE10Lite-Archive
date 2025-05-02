![LED Wave Demo](https://github.com/jhherre3/FPGA-DE10Lite-Archive/blob/main/images-gifs/LED_WAVE-ezgif.gif?raw=true)



# DE10-Lite LED Wave Direction Control (Verilog)

## 🔧 Project Overview

This FPGA project showcases a dynamic LED wave pattern on the DE10-Lite development board using **pure Verilog HDL**, without any external components. The design demonstrates how to manipulate digital outputs (LEDs) using onboard inputs (switches) and a clock-driven finite state machine. Refer to Test_.zip file

The system lights up one LED at a time in a wave-like sequence. The user can toggle a hardware switch (`SW[0]`) to reverse the wave direction in real time, allowing bidirectional movement across the 10 red LEDs.

---

## 🎯 Project Goals

- Use the DE10-Lite's onboard **clock**, **switches**, and **LEDs** with Verilog.
- Demonstrate **clock division**, **FSM logic**, and **interactive control** via switches.
- Showcase how simple state-based behavior can simulate time-based animation.
- Provide a foundation for more advanced projects such as PWM lighting, timing logic, or animation control.

---

## ⚙️ Hardware Used

- **Board:** Terasic DE10-Lite (MAX 10 FPGA)
- **Inputs:** `SW[0]` – direction control (forward/reverse)
- **Outputs:** `LEDR[9:0]` – 10 red LEDs, wave animation
- **Clock:** 50 MHz onboard clock (`CLOCK_50`)

---

## 🧠 How It Works

The LED movement is driven by a 50 MHz system clock divided down using a counter to generate a visible delay (~0.25s). The `position` register tracks the currently active LED, while the `dir` signal (derived from `SW[0]`) determines whether to increment or decrement the LED index.

### State Machine Logic

- **States:** Represent LED positions (0 through 9)
- **Transitions:** Controlled by direction (forward/reverse)
- **Input:** `SW[0]` — live toggle, sampled during every tick

### Clock Division

A `25-bit` counter is incremented on every positive edge of the 50 MHz clock. Once it reaches a threshold (e.g., 12 million), it triggers a state change and resets.

---

## 📈 Advanced Analysis

While this project is simple in appearance, it demonstrates several key concepts in FPGA digital design:

### 1. **Hardware Clock Management**
   - Dividing a 50 MHz clock to a human-visible refresh rate illustrates how hardware timers and counters are essential in embedded systems.
   - This mimics real-time control loops in robotics or UI systems.

### 2. **Synchronous Finite State Machine (FSM)**
   - The LED index acts as a state register.
   - Directional control adds conditional logic based on real-time input sampling.

### 3. **Edge-Sensitive Design**
   - All timing is synchronized to `posedge CLOCK_50`, making the design safe and deterministic across hardware.

### 4. **Interactive IO with Minimal Latency**
   - Input (`SW[0]`) is debounced implicitly due to sampling on slower time intervals (~0.25s). In real systems, proper debounce logic would be required for higher-speed switches.

---
