# Class-D-audio-amplifier-using-NE555-AND-TRANSISTORS
The project that i have built to make the class-D ammplifier more efficient and high noise tolerable,With the combination of  switching technique using the MOS transistors,LC filter and the error block ,along with the high efficient output block .
1. Overall Working Principle

The circuit works in four main stages:

Audio Input & Signal Conditioning

PWM Generation (Comparator + Carrier)

Power Switching Stage (MOSFET Half-Bridge)

2.Output LC Filter & Load
Audio Input (V1)

V1 is a sine wave source representing the audio input signal.

Frequency is in the audio range.

A small series resistance models a real signal source.

Biasing & Scaling

Resistors like R1, R10, and R6 are used to:

Set proper bias levels

Scale the input signal

Prevent loading of the source

This ensures the audio signal is correctly centered and compatible with the PWM generation stage.
3. Carrier Signal Generation (NE555 Timer)
NE555 (U1)

The NE555 timer is configured as an astable oscillator.

It generates a high-frequency triangular / sawtooth waveform, which acts as the carrier signal for PWM.

This carrier frequency is much higher than the audio frequency to allow accurate modulation.

Timing Components

R3, R4, C1, and C3 define the oscillator frequency.

The frequency is chosen high enough to:

Reduce audible distortion

Improve filtering at the output

4. PWM Generation (Comparator Stage)
Comparator (U2 / A1)

The audio signal and the carrier signal are fed into a comparator.

When the audio signal is higher than the carrier, the output goes HIGH.

When it is lower, the output goes LOW.

This produces a Pulse Width Modulated (PWM) signal whose duty cycle represents the instantaneous amplitude of the audio signal.

Supporting Components

R7, R8, R9, R11, C5, and C7:

Stabilize the comparator

Reduce noise

Shape transitions to avoid false triggering

5. Gate Driver & Power Stage
MOSFET Half-Bridge

M1 (PMOS) and M2 (NMOS) form a complementary half-bridge.

They switch alternately based on the PWM signal.

The switching happens at high frequency, minimizing power loss.

Power Supply

V2 provides the DC supply for the power stage.

C9 acts as a decoupling capacitor to reduce supply ripple and noise.

Gate Resistors

R13 limits gate current and protects the MOSFETs.

Helps control switching speed and reduce EMI.

6. Output LC Low-Pass Filter
Purpose of the Filter

The PWM output is a high-frequency square wave.
The LC filter removes the switching frequency and reconstructs the original audio waveform.

Components

L1 (Inductor)

C6 and C10 (Capacitors)

Together, they form a low-pass filter that:

Passes audio frequencies

Blocks high-frequency switching components

7. Load & Output
Load Resistor

R14 represents the speaker load (8 Ω).

The filtered signal across this resistor is the final amplified audio output.

Output Node

The node labeled “output” is where the clean audio signal can be measured.

8. Protection & Stability Components

R12 provides controlled grounding and current stability.

Small capacitors throughout the circuit suppress:

High-frequency noise

Oscillations

Switching spikes

These components are essential for realistic and stable simulation behavior.

9. Why Class-D?

Advantages of this design:

Very high efficiency (minimal heat loss)

Suitable for battery-powered systems

Compact and modern amplifier topology

Trade-offs:

Requires careful filtering

More complex than linear amplifiers

Sensitive to layout and switching noise (important in real hardware)

10. Simulation Notes

The circuit is simulated using LTspice transient analysis.

PWM behavior, switching transitions, and filtered output can be observed by probing:

Comparator output

MOSFET switching node

Final output node

Conclusion

This project demonstrates a complete Class-D amplifier workflow, starting from an analog input signal and ending with a filtered, high-power audio output.
It combines analog signal processing, digital-like PWM control, and power electronics into a single efficient system.

This makes it an excellent learning project for:

Power electronics

Audio amplification

Mixed-signal circuit design.
