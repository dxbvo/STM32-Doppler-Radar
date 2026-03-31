# 📡 STM32 Doppler Radar Speed Measurement

Real-time speed measurement system using a 24 GHz Doppler radar, designed to measure the velocity of a hockey puck.

The system combines RF hardware, analog signal conditioning, and digital signal processing on a microcontroller to estimate object velocity from Doppler frequency shifts.

## 🚀 Overview

This project implements a complete Doppler radar measurement pipeline:

- Acquisition of I/Q signals from a 24 GHz radar module
- Analog signal conditioning (filtering and amplification)
- Digital signal processing using FFT
- Velocity estimation from Doppler frequency
- Display of measured speed on a user interface

The system was designed to measure puck speeds up to **200 km/h** with high accuracy. 

## ⚙️ System Architecture

### Hardware

- **Radar module:** RFbeam K-LC5 (24 GHz)
- **Microcontroller:** STM32L476 Discovery board
- **Analog front-end:**
  - High-pass filter for DC removal
  - Amplifier with a gain of about 1000
  - Band-pass filtering for the expected Doppler range

The radar module provides **I** and **Q** signals, representing the real and imaginary components of the Doppler signal. The hardware was designed for a Doppler frequency range of approximately **445 Hz to 8895 Hz**. 

### Software

The software processes the digitized I/Q signals and estimates object speed by:

1. Combining I and Q into a complex signal
2. Performing an FFT
3. Applying `fftshift`
4. Finding the dominant Doppler frequency
5. Calculating the corresponding velocity

## 🎯 Project Goals

The main requirements of the system were:

- Measure the velocity of moving objects
- Detect whether the target is moving toward or away from the device
- Measure puck speed up to **200 km/h**
- Achieve an accuracy of **±0.3 km/h**
- Display the maximum velocity on a user interface
- Support connectivity to share data with external devices
- Explore the use of a **3D-printed dielectric lens** for focusing the radar signal :contentReference[oaicite:4]{index=4}

## 🖥️ User Interface

The user interface concept includes:

- A **start/measure button**
- A display showing the measured speed
- Export of measurement data to an external device
- Tracking of previous and maximum measured speeds

The report also describes possible extensions such as Bluetooth or cable-based data transfer for later analysis. :contentReference[oaicite:5]{index=5}

## 🛠️ Tech Stack

- **Embedded C/C++**
- **STM32L476 Discovery**
- **24 GHz RF Doppler radar**
- **FFT-based signal processing**
- **Analog filter and amplifier design**

## 📄 Documentation

A concept design report for the project is included in this repository:

- `ConceptDesignReport.pdf`

## 📌 Notes

This project was developed in the context of an engineering course, with a strong focus on combining:

- embedded systems
- signal processing
- radar-based measurement
- hardware/software integration
