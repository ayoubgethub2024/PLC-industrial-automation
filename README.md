# PLC-industrial-automation
Industrial automation PLC code in mnemonic format. Includes analog temperature control, safety system, and Delta ISPSoft/WPLSoft exports
# Tempering Machine PLC Program - Mnemonic Code

Delta PLC program for 80kg tempering machine with nickel temperature control.

## Program Overview

This mnemonic file contains the complete ladder logic for an industrial tempering machine.

| Item | Detail |
|------|--------|
| PLC Brand | Delta |
| Program Type | Ladder Diagram (exported as mnemonic) |
| File Format | CSV / Mnemonic text |

## Key Functions Identified

| Function | Instructions Used |
|----------|-------------------|
| Safety System | LDI, AND, ANI, MPS/MRD/MPP |
| Nickel Temperature Control | FROM/TO (analog I/O), MOV, ADD, SUB |
| Timer/Counter Logic | TMR (implied), ZRST |
| Interlocking | SET, RST, ANDF/LDF (falling/rising edge) |

## Analog I/O Configuration

| Instruction | Module | Register | Description |
|-------------|--------|----------|-------------|
| TO K0 K1 HF000 K1 | Analog Output | CH1 | Configure analog output |
| FROM K0 K18 D511 K1 | Analog Input | CH1 | Temperature reading 1 |
| FROM K0 K19 D521 K1 | Analog Input | CH2 | Temperature reading 2 |
| FROM K0 K20 D531 K1 | Analog Input | CH3 | Temperature reading 3 |

## Main Control Registers

| Register | Function |
|----------|----------|
| D510 | Temperature setpoint |
| D511 | Actual temperature 1 |
| D521 | Actual temperature 2 |
| D531 | Actual temperature 3 |
| Y0 | Heater control |
| Y1 | Conveyor control |
| Y2 | Cooling control |
| Y4 | Alarm output |

## Program Structure

The program uses MPS/MRD/MPP (stack operations) for branching logic, implementing:
- Multi-condition interlocking
- Hysteresis control for temperature
- Auto/manual mode selection
- Safety shutdown conditions

## How to Import to WPLSoft

1. Open Delta WPLSoft
2. Create new project or open existing
3. Go to **File** → **Import** → **Program Mnemonic**
4. Select this CSV/txt file
5. Compile and verify

## Version

| Version | Date | Description |
|---------|------|-------------|
| 1.0 | 2024 | Tempering machine control with nickel temp regulation |

## Author

Embedded Systems & Industrial Automation Engineer
