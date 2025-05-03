# 🧠 DE10-Lite FPGA Board – Pin Assignment Cheat Sheet

> This is a full reference of essential pin mappings for projects using the Terasic DE10-Lite development board.

---

## ⏱ Clock Inputs
| Signal Name      | FPGA Pin | Description                     | I/O Standard |
|------------------|----------|----------------------------------|--------------|
| `ADC_CLK_10`     | PIN_N5   | 10 MHz clock for ADC            | 3.3V LVTTL   |
| `MAX10_CLK1_50`  | PIN_P11  | 50 MHz clock (main system clk)  | 3.3V LVTTL   |
| `MAX10_CLK2_50`  | PIN_N14  | 50 MHz clock (alt)              | 3.3V LVTTL   |

---

## 🔘 Push Buttons
| Name    | FPGA Pin |
|---------|----------|
| `KEY0`  | PIN_B8   |
| `KEY1`  | PIN_A7   |

---

## 🎚 Slide Switches (SW0–SW9)
| Switch | Pin       |
|--------|-----------|
| SW0    | PIN_C10   |
| SW1    | PIN_C11   |
| SW2    | PIN_D12   |
| SW3    | PIN_C12   |
| SW4    | PIN_A12   |
| SW5    | PIN_B12   |
| SW6    | PIN_A13   |
| SW7    | PIN_A14   |
| SW8    | PIN_B14   |
| SW9    | PIN_F15   |

---

## 💡 Red LEDs (LEDR0–LEDR9)
| LED    | Pin       |
|--------|-----------|
| LEDR0  | PIN_A8    |
| LEDR1  | PIN_A9    |
| LEDR2  | PIN_A10   |
| LEDR3  | PIN_B10   |
| LEDR4  | PIN_D13   |
| LEDR5  | PIN_C13   |
| LEDR6  | PIN_E14   |
| LEDR7  | PIN_D14   |
| LEDR8  | PIN_A11   |
| LEDR9  | PIN_B11   |

---

## 🔢 7-Segment Display (HEX0–HEX5)
Each display uses 7 segments [0–6]. Active-low (common anode).

<details>
<summary>Click to view HEX segment pin assignments</summary>

### HEX0
- HEX0[0] → PIN_C14
- HEX0[1] → PIN_E15
- HEX0[2] → PIN_C15
- HEX0[3] → PIN_C16
- HEX0[4] → PIN_E16
- HEX0[5] → PIN_D17
- HEX0[6] → PIN_C17

### HEX1
- HEX1[0] → PIN_C18
- HEX1[1] → PIN_D18
- HEX1[2] → PIN_E18
- HEX1[3] → PIN_B16
- HEX1[4] → PIN_A17
- HEX1[5] → PIN_A18
- HEX1[6] → PIN_B17

### HEX2
- HEX2[0] → PIN_B20
- HEX2[1] → PIN_A20
- HEX2[2] → PIN_B19
- HEX2[3] → PIN_A21
- HEX2[4] → PIN_B21
- HEX2[5] → PIN_C22
- HEX2[6] → PIN_B22

### HEX3
- HEX3[0] → PIN_F21
- HEX3[1] → PIN_E22
- HEX3[2] → PIN_E21
- HEX3[3] → PIN_C19
- HEX3[4] → PIN_C20
- HEX3[5] → PIN_D19
- HEX3[6] → PIN_E17

### HEX4
- HEX4[0] → PIN_F18
- HEX4[1] → PIN_E20
- HEX4[2] → PIN_E19
- HEX4[3] → PIN_J18
- HEX4[4] → PIN_H19
- HEX4[5] → PIN_F19
- HEX4[6] → PIN_F20

### HEX5
- HEX5[0] → PIN_J20
- HEX5[1] → PIN_K20
- HEX5[2] → PIN_L18
- HEX5[3] → PIN_N18
- HEX5[4] → PIN_M20
- HEX5[5] → PIN_N19
- HEX5[6] → PIN_N20

</details>

---

## 🧭 Accelerometer (ADXL345 over I2C)
| Signal         | Pin      | Description               |
|----------------|----------|---------------------------|
| `I2C_SDA`      | PIN_J16  | Data                      |
| `I2C_SCL`      | PIN_J15  | Clock                     |
| `CS_n`         | PIN_G16  | Chip select (tie high)    |
| `SDO`          | PIN_F16  | Addr select (I2C LSB bit) |
| `INT1`         | PIN_H15  | Optional interrupt        |
| `INT2`         | PIN_H16  | Optional interrupt        |

---

## 🧠 SDRAM Interface (16-bit)
- `DRAM_CLK`   → PIN_L14
- `DRAM_DQ[0–15]`  → e.g. DQ0 = PIN_Y21 to DQ15 = PIN_F22
- `DRAM_ADDR[0–12]`, `WE_N`, `RAS_N`, `CAS_N`, `CS_N`, etc.

📘 Refer to Table 3-8 in the DE10-Lite manual for full SDRAM pin list.

---

## 🖥 VGA Output (4-bit per channel DAC)
| Signal      | Pin     |
|-------------|---------|
| VGA_R[0-3]  | AA1, V1, Y2, Y1 |
| VGA_G[0-3]  | W1, T2, R2, R1 |
| VGA_B[0-3]  | P1, T1, P4, N2 |
| VGA_HS / VS | N3, N1   |

---

## 🔌 GPIO Header (JP1 / JP2)
| GPIO Pin | Notes                  |
|----------|------------------------|
| GPIO[0]  | PIN_V10                |
| GPIO[1]  | ... up to              |
| GPIO[35] | PIN_AA2                |

📘 See DE10-Lite Manual Table 3-9 for all JP header mappings.

---

### 📎 Notes:
- All I/O standards: **3.3V LVTTL**
- HEX displays are **common anode** (LOW turns ON a segment)
- Use `MAX10_CLK1_50` (PIN_P11) as your default system clock

---

### ✅ Last Updated
May 2025 — based on official [DE10-Lite User Manual](https://www.terasic.com.tw/cgi-bin/page/archive.pl?Language=English&CategoryNo=139&No=1046)

