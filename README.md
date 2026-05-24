# PLC Industrial Automation

Delta PLC ladder logic programs for industrial automation applications.

## Repository Contents

| File | Description |
|------|-------------|
| `tempering_machine_mnemonics.csv` | Complete ladder logic for 80kg tempering machine with nickel temperature control |
| `LICENSE` | MIT License |

## Program Overview - Tempering Machine

This mnemonic file contains the complete ladder logic for an industrial tempering machine with:
- Nickel temperature control system
- Master safety system
- Analog I/O processing (FROM/TO instructions)
- Multi-zone temperature monitoring

### Program Statistics

| Item | Detail |
|------|--------|
| PLC Brand | Delta |
| Programming Software | WPLSoft / ISPSoft |
| Total Steps | 551 |
| Instructions | LD, AND, OR, SET, RST, MOV, FROM, TO, ZRST, ADD, SUB, MPS/MRD/MPP |

### Key Instructions Used

| Instruction | Purpose |
|-------------|---------|
| `FROM K0 K18 D511 K1` | Read analog input (Temperature sensor 1) |
| `FROM K0 K19 D521 K1` | Read analog input (Temperature sensor 2) |
| `FROM K0 K20 D531 K1` | Read analog input (Temperature sensor 3) |
| `TO K0 K1 HF000 K1` | Configure analog output |
| `ZRST Y0 Y4` | Reset output zone |
| `MOV K5 D550` | Move constant to register |

### Main Control Registers

| Register | Function |
|----------|----------|
| D510 | Temperature setpoint |
| D511 | Actual temperature channel 1 |
| D521 | Actual temperature channel 2 |
| D531 | Actual temperature channel 3 |
| Y0 | Heater control output |
| Y1 | Conveyor/motor control |
| Y4 | Alarm output |

### Program Structure

The program uses MPS/MRD/MPP stack operations for complex branching logic, implementing:
- Hysteresis temperature control (AND<, AND>, AND<=, AND>=)
- Edge detection (ANDP, ANDF, LDP, LDF)
- Interlocking safety conditions
- Auto/manual mode selection

## How to View This Program

### Option 1: View on GitHub
The CSV file displays as a formatted table directly in GitHub.

### Option 2: Import to WPLSoft
1. Open Delta WPLSoft
2. Click **File** → **Import** → **Program Mnemonic**
3. Select `tempering_machine_mnemonics.csv`
4. Compile and switch to Ladder Diagram view

### Option 3: Import to ISPSoft
1. Open Delta ISPSoft
2. Create a new project
3. Click **Tools** → **Ladder Logic Editor**
4. Copy/paste the mnemonic text

## Related Projects

| Repository | Description |
|------------|-------------|
| [embedded-industrial-automation](https://github.com/ayoubgethub2024/-embedded-industrial-automation) | ESP8266 firmware, WebSocket dashboard, IoT monitoring |

## Author

Embedded Systems & Industrial Automation Engineer

## License

MIT License
