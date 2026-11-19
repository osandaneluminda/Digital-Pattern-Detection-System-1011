# Digital Pattern Detection System Design – 1011

## Project Overview

The **Digital Pattern Detection System** is a synchronous digital system designed to generate, transmit, and detect a specific four-bit binary sequence.

The assigned pattern for this project is **1011**.

The system consists of three main functional modules:

1. Random Pattern Generator
2. Parallel-In Serial-Out (PISO) Shift Register
3. Finite State Machine (FSM) Pattern Detector

The modules operate using a common clock signal. The generated four-bit data is loaded into the PISO register and transmitted serially to the FSM, which detects the assigned sequence 1011.

## System Architecture

The overall data flow is:

**Random Pattern Generator → PISO Shift Register → FSM Pattern Detector → Detection Output**

### 1. Random Pattern Generator

- Generates four-bit pseudo-random binary data.
- Uses D-type flip-flops and XOR feedback logic.
- Requires a non-zero initial state.

### 2. PISO Shift Register

- Uses four D-type flip-flop stages.
- Loads four-bit parallel data.
- Shifts the stored data serially according to the clock.
- Sends serial data to the FSM detector.

### 3. FSM Pattern Detector

- Implements a four-state Mealy finite state machine.
- Uses two state bits.
- Detects the binary sequence 1011.
- Activates the detection output when the complete pattern is received.

## FSM Design

The assigned sequence is:

`1011`

The FSM uses the following state encoding:

| State | Encoding | Description |
|---|---|---|
| S0 | 00 | No relevant pattern matched |
| S1 | 01 | Sequence 1 matched |
| S2 | 10 | Sequence 10 matched |
| S3 | 11 | Sequence 101 matched |

The detection output becomes HIGH when the FSM is in state S3 and receives input 1.

### Boolean Expressions

The simplified next-state equations are:

```text
D0 = X

D1 = Q0X' + Q1Q0'X

DETECT = Q1Q0X
```

Where:
- Q1 and Q0 are the present-state bits.
- X is the serial input.
- D1 and D0 are the next-state inputs.

## Hardware and Components

The design uses digital logic components including:

- D-type flip-flops (74HC74)
- XOR gates
- AND gates (74HC08)
- OR gates (74HC32)
- NOT gates (74HC04)
- Resistors
- LEDs
- Capacitors
- Clock source
- Power supply and connectors

The exact component selection and connections should follow the final circuit schematic.

## Design and Simulation Tools

- Proteus Design Suite – circuit design and simulation
- KiCad – schematic capture and PCB design

## Simulation and Testing

The project includes simulation and testing of:

- Random pattern generation
- PISO parallel loading
- PISO serial shifting
- FSM pattern detection
- Incorrect pattern testing
- Complete system integration
- Clock and detection-output timing waveforms

The integrated system was observed using the Proteus oscilloscope.

### Oscilloscope Signals

- Yellow – Common clock signal
- Blue – PISO serial output
- Pink – FSM detection output

The detection output changes from LOW to HIGH when the complete sequence is detected.

## PCB Design

PCB layouts were developed using KiCad for the following functional blocks:

1. Random Pattern Generator
2. PISO Shift Register
3. FSM Pattern Detector (1011)

The PCB design includes component footprints, connectors, resistors, capacitors, and routed tracks.

## Project Documentation

The complete project report includes:

- System architecture
- FSM state diagram and transition table
- Boolean expressions and Karnaugh maps
- Logic gate implementation
- Proteus circuit simulation
- Oscilloscope timing waveforms
- KiCad PCB layouts
- Testing and analysis

## Project Team

Developed as a group assignment for **Digital Systems Design (IE3004)** at Sri Lanka Institute of Information Technology (SLIIT).

## Key Learning Outcomes

- Sequential logic circuit design
- D-type flip-flop operation
- Shift-register implementation
- Finite State Machine design
- Mealy pattern detection
- Boolean algebra and Karnaugh map simplification
- Clock synchronization
- Digital circuit simulation
- PCB schematic and layout design

---

**Note:** This is an academic digital systems design project developed for educational purposes.