# DC Motor Speed Control Using PI Controller and Encoder Feedback

## Overview
This project demonstrates a closed-loop DC motor speed control system utilizing a Proportional-Integral (PI) controller and encoder-based feedback. The system maintains precise motor speed under varying loads by comparing a reference input with actual speed feedback and dynamically adjusting the motor drive signal.

## Features
- **Closed-loop control** for precise speed regulation
- **Encoder-based feedback** for accurate speed measurement
- **PI controller** for fast response and elimination of steady-state error
- **Voltage clamping** to protect motor driver circuitry
- **Motor driver (L298N)** to handle power requirements
- Implemented using **operational amplifiers (LM324/TL082)**, resistors, capacitors, and a **555 timer** for signal conditioning.

## Circuit Components
- **Arduino Uno** – Generates reference PWM signal (desired speed)
- **Encoder** – Measures actual motor speed (generates pulses)
- **Error Amplifier** – Compares reference and feedback voltages
- **PI Controller** – Processes error signal with proportional and integral terms
- **Zener Diode (1N4733A)** – Limits PI controller output to safe voltage
- **Motor Driver (L298N)** – Drives DC motor
- **555 Timer + RC Filter** – Converts encoder pulses to voltage feedback
- **Low-pass filters, Differentiator, Inverter** – Signal conditioning

## Working Principle
1. **Reference Generation**: Arduino sets desired speed as PWM signal, converted to reference voltage.
2. **Feedback Measurement**: Encoder measures actual speed; pulses converted to DC voltage using 555 timer and RC filter.
3. **Error Calculation**: Error amplifier computes difference between reference and feedback voltages.
4. **PI Control**: Proportional action provides immediate response; integral action corrects persistent errors.
5. **Voltage Clamping**: Zener diode limits control voltage to prevent overdriving motor driver.
6. **Motor Driving**: L298N adjusts motor speed based on control voltage.
7. **Closed Loop**: Continuous feedback and correction maintain target speed.

## How to Run
1. **Set up the hardware** with the components listed above.
2. **Program Arduino** to generate reference PWM signal.
3. **Build the circuit** including PI controller, error amplifier, 555 timer, and motor driver.
4. **Test system** by varying load on the motor and observing speed stabilization.
5. **Fine-tune resistor/capacitor values** for optimal response.

## Results
- Motor speed maintained within ±2% of setpoint under load changes.
- Smooth startup and dynamic response.
- Encoder feedback improved accuracy over simple voltage-based methods.

## Future Improvements
- Implement **digital PI controller** in software (Arduino).
- Add **adaptive gain tuning** for dynamic performance.
- Replace 555 timer with dedicated **frequency-to-voltage converter IC**.

## Authors
- Maharishi Sonwani (23JE0531)
- M Abhishek (23JE0525)

## License
This project is open-source and free to use for educational purposes.
