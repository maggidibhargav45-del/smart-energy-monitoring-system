# ⚡ Smart Energy Monitoring System

An IoT-based energy monitoring system developed using **ESP8266, ADS1115, ACS712, ZMPT101B and Blynk** for real-time monitoring of electrical parameters and electricity cost estimation.

## 📌 Project Overview

The Smart Energy Monitoring System measures and monitors:

* ⚡ Voltage
* 🔌 Current
* 💡 Power
* 📊 Energy consumption
* 💰 Electricity cost estimation
* 🚨 Overcurrent alerts

The measured data is displayed locally on a **16×2 I2C LCD** and transmitted through Wi-Fi to the **Blynk IoT platform** for remote monitoring and visualization.

## 🏗️ System Architecture

```text
AC Supply
   │
   ├── ZMPT101B ──► Voltage Measurement
   │
   └── ACS712 ────► Current Measurement
                         │
                         ▼
                    ADS1115 ADC
                         │
                         ▼
                  ESP8266 NodeMCU
                    │          │
                    │          └──► 16×2 I2C LCD
                    │
                    ▼
                  Wi-Fi
                    │
                    ▼
               Blynk IoT Cloud
                    │
                    ▼
             Mobile Dashboard
```

## 🔧 Hardware Components

| Component          | Purpose                                 |
| ------------------ | --------------------------------------- |
| ESP8266 NodeMCU    | Main controller and Wi-Fi communication |
| ACS712             | Current sensing                         |
| ZMPT101B           | AC voltage sensing                      |
| ADS1115            | 16-bit ADC for sensor measurement       |
| 16×2 I2C LCD       | Local display                           |
| AC Load            | Load for testing                        |
| Breadboard & wires | Circuit prototyping                     |

## 💻 Software & Technologies

* Embedded C/C++
* Arduino IDE
* ESP8266
* Blynk IoT
* I2C Communication
* ADC Signal Processing
* Voltage and Current Measurement
* Energy Monitoring

## ⚙️ Working Principle

1. The **ZMPT101B** senses the AC voltage.
2. The **ACS712** senses the load current.
3. The sensor signals are acquired using the **ADS1115 ADC**.
4. The ESP8266 processes and filters the measurements.
5. Voltage and current values are calculated.
6. Power is estimated using:

```text
Power = Voltage × Current
```

7. Energy consumption is accumulated over time.
8. Energy in Wh is converted into units:

```text
1 unit = 1 kWh = 1000 Wh
```

9. Electricity cost is estimated using:

```text
Cost = Energy Units × Unit Price
```

10. The values are displayed on the LCD and sent to the Blynk dashboard through Wi-Fi.

## 📱 Blynk Dashboard

The system sends the following parameters to Blynk:

| Virtual Pin | Parameter |
| ----------- | --------- |
| V0          | Voltage   |
| V1          | Current   |
| V2          | Power     |
| V3          | Energy    |
| V4          | Cost      |

An overcurrent notification is generated when the measured current exceeds the configured safety threshold.

## 🧮 Cost Estimation

The current implementation uses a configurable electricity rate:

```cpp
float unitPrice = 7.0;
```

The estimated cost is calculated as:

```text
Energy Units = Energy (Wh) / 1000
Cost = Energy Units × Unit Price
```

The value of the unit price can be changed according to the applicable electricity tariff.

## 🧪 Testing

The system was tested using electrical loads such as:

* 100 W bulb
* 1000 W heater

Measurements were compared with a calibrated digital multimeter to evaluate the system's measurement accuracy.

## ⚠️ Important Note

The current implementation estimates power using:

```text
P = V × I
```

This is suitable for approximately resistive loads. For inductive loads such as motors and fans, power factor should be considered for more accurate real-power measurement.

## 🚀 Future Scope

Possible improvements include:

* True RMS voltage and current measurement
* Power-factor measurement
* Three-phase energy monitoring
* SD-card/cloud backup
* Non-Intrusive Load Monitoring (NILM)
* Machine-learning-based load identification
* Dedicated energy-metering IC integration
* Improved calibration and signal conditioning

## 👥 Team Members

* **J. Nanda Vardhan** — Hardware assembly, circuit integration and prototyping
* **M. Bhargav** — Firmware development, ADC processing, filtering, voltage/current calculation and energy tracking
* **M. Monalisa** — Blynk IoT integration, dashboard development and notifications

The team collaboratively worked on system architecture, component selection, integration, calibration, testing, debugging and documentation.

## 📂 Repository Structure

```text
smart-energy-monitoring-system/
│
├── README.md
│
├── src/
│   └── Smart_Energy_Monitoring.ino
│
├── hardware/
│   ├── prototype.jpg
│   └── circuit_diagram.png
│
├── results/
│   └── blynk_dashboard.jpg
│
└── docs/
    └── project_report.pdf
```

## 🔐 Credentials

For security, Wi-Fi credentials and Blynk authentication tokens are **not included in this repository**.

Before running the code, replace the placeholders in the Arduino sketch with your own credentials:

```cpp
#define BLYNK_AUTH_TOKEN "YOUR_BLYNK_AUTH_TOKEN"

char ssid[] = "YOUR_WIFI_NAME";
char pass[] = "YOUR_PASSWORD";
```

**Never commit real passwords, authentication tokens or API keys to a public repository.**
