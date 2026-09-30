# ⚡ Smart Energy Monitoring System

## 📌 Project Overview

The Smart Energy Monitoring System is an IoT-based system developed to monitor electrical energy parameters of single-phase AC loads in real time.

The system uses an ESP8266 NodeMCU along with voltage and current sensors to measure RMS voltage and RMS current. The measured parameters are processed to calculate power and energy consumption.

The readings are displayed locally on a 16x2 I2C LCD and transmitted over Wi-Fi to the Blynk IoT platform for remote monitoring.

## 🎯 Objectives

- Measure RMS voltage of AC loads
- Measure RMS current
- Calculate electrical power
- Monitor cumulative energy consumption
- Display readings locally using an LCD
- Monitor parameters remotely using Blynk IoT
- Generate an alert when current exceeds the defined threshold

## 🧰 Hardware Components

- ESP8266 NodeMCU
- ACS712 Current Sensor
- ZMPT101B Voltage Sensor
- ADS1115 16-bit ADC
- 16x2 I2C LCD
- AC Load
- Breadboard and connecting wires

## 💻 Software and Technologies

- Embedded C/C++
- Arduino IDE
- ESP8266
- I2C
- Blynk IoT
- ADC
- RMS Signal Processing

## ⚙️ Working

1. The ZMPT101B voltage sensor measures the AC voltage.
2. The ACS712 measures the load current.
3. The ADS1115 provides high-resolution analog-to-digital conversion.
4. The ESP8266 processes the sampled sensor signals.
5. RMS voltage and current are calculated.
6. Electrical power is calculated from the measured parameters.
7. Energy consumption is accumulated over time.
8. The readings are displayed on the LCD.
9. The ESP8266 sends the readings to the Blynk IoT platform through Wi-Fi.
10. An overcurrent notification is generated when the current crosses the defined threshold.

## 📊 Parameters Monitored

- RMS Voltage
- RMS Current
- Power
- Energy Consumption

## 📱 Blynk IoT

The Blynk dashboard is used for remote monitoring of:

- Voltage
- Current
- Power
- Energy

The system also provides an overcurrent notification through the mobile application.

## 👥 Team Members

### J. Nanda Vardhan
- Hardware assembly
- Circuit integration
- Prototype development

### M. Bhargav
- Firmware development
- ADC sampling
- RMS voltage and current calculations
- Noise filtering

### M. Monalisa
- Blynk IoT integration
- Mobile dashboard
- Push notification system

### 🤝 Teamwork

All three team members collaboratively contributed to:

- System architecture
- Component selection
- Hardware integration
- Calibration
- Testing and debugging
- Documentation

## 🧪 Testing

The prototype was tested using resistive loads and compared against a calibrated digital multimeter.

The project included testing for:

- Voltage measurement
- Current measurement
- Power calculation
- System stability
- Overcurrent notification

## 🚀 Future Scope

Possible future improvements include:

- Three-phase energy monitoring
- Improved power-factor measurement
- Dedicated energy-metering IC
- Machine-learning-based energy analysis
- Non-Intrusive Load Monitoring
- Local data storage using SD card

## 📷 Project Images

Project prototype and Blynk dashboard images can be added here.

## 📚 Project Documentation

The project report can be added to the repository after removing any private or sensitive information.
