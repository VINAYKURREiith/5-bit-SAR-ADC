
# ⚡ SAR ADC using D Flip-Flops

This project implements a **Successive Approximation Register (SAR) Analog-to-Digital Converter (ADC)** using basic digital logic components—primarily **D Flip-Flops**, a **comparator**, and an **R-2R DAC**. The design is intended for educational and prototyping purposes and can be implemented on a breadboard or simulated digitally.

---

## 📌 Overview

The SAR ADC converts an analog input voltage to a digital output using binary search. The circuit uses:

- **D Flip-Flops** to store and control the SAR logic
- **R-2R Ladder DAC** to generate the reference voltage
- **Comparator** (e.g., LM741 or equivalent) to compare the input voltage with DAC output
- **Clock pulse** to trigger the bit-by-bit approximation

---

## 🔧 Key Components

| Component         | Description                           |
|------------------|---------------------------------------|
| D Flip-Flops      | Store each bit of the ADC result      |
| R-2R Ladder DAC   | Converts SAR output to analog         |
| Comparator        | Compares DAC output with input signal |
| Vref              | Reference voltage (e.g., 5V)          |
| Clock             | Drives the SAR step-by-step           |

---

## 📐 Circuit Diagram

> Upload and link your schematic image here:
![SAR ADC Schematic](./images/schematic.png)

---

## 🧠 Working Principle

1. **Start**: MSB is set to 1, rest are 0.
2. **Compare**: DAC output is compared with input voltage.
3. **Decision**: If DAC > Vin → clear MSB, else keep it.
4. **Shift**: Move to next lower bit and repeat.
5. **Result**: After all bits are tested, output holds digital equivalent of Vin.

---

## 💻 Folder Structure

```

sar-adc-dff/
├── images/               # Schematic and breadboard images
├── hardware/             # Photos of physical build
├── README.md             # This file

````

---

## 🚀 How to Use

### Hardware Setup

1. Build the R-2R DAC circuit.
2. Connect SAR logic using D flip-flops (IC 7474 or equivalent).
3. Feed input voltage (Vin) to comparator.
4. Use Arduino or pulse generator to provide the clock.
5. Observe digital output bits (e.g., LEDs or on logic analyzer).

### Simulation (Optional)

If implemented in Verilog:
```bash
# Compile
iverilog -o sar sar_adc.v testbench.v

# Run
vvp sar
```

---

## 📈 Output Example

> Insert photo/screenshot here:
> ![Output Demo](./images/output.png)

---

## 🧠 Learnings

* Implemented SAR ADC without using microcontrollers
* Understood internal SAR logic via D flip-flops
* Integrated analog and digital components in real-time decision loop

---

## 📚 References

* [Analog Devices SAR ADC Guide](https://www.analog.com/en/analog-dialogue/articles/how-a-successive-approximation-adc-works.html)
* Digital Design by M. Morris Mano
* Lab Notes / Datasheets (LM741, 7474 IC, etc.)

---

## 📜 License

This project is open for academic and learning use. Please cite the repo if used in reports or tutorials.

```

---

Let me know if you want to add [schematic images](f), [Verilog code](f), or [testbench simulations](f) in the README.
```
