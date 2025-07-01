# Embedded RC Car 🚗 | ATmega32-based Embedded System

This repository contains the implementation of a custom-built **Remote-Controlled Car** using the **ATmega32 microcontroller**. The system supports both **manual (Bluetooth)** and **autonomous (obstacle-avoiding)** operation modes. It demonstrates practical applications of motor control, UART communication, ultrasonic sensing, and embedded C development in real-time systems.

---

## 📌 Project Overview

This embedded system is developed to:

- Control the motion of an RC car manually via Bluetooth or autonomously using sensor input.
- Read and process real-time distance measurements via ultrasonic sensors.
- Manage speed and direction using an L298N motor driver.
- Demonstrate a clean separation of software modules for maintainability and scalability.

---

## 🚀 Key Features

| Feature                   | Description                                                                 |
|---------------------------|-----------------------------------------------------------------------------|
| ✅ Manual Driving Mode     | Control the car using commands via a Bluetooth terminal or mobile app.     |
| ✅ Autonomous Driving Mode | Obstacle detection and avoidance using ultrasonic sensors.                 |
| ✅ UART Communication      | Receive and process commands via Bluetooth using UART protocol.            |
| ✅ Modular Architecture    | Code is divided into reusable modules (sensors, motors, communication).    |
| ✅ Real-Time Sensing       | Distance measurement and responsive navigation logic.                      |

---

## 🔧 Hardware Components

| Component            | Description                                       |
|----------------------|---------------------------------------------------|
| **Microcontroller**  | ATmega32 (AVR architecture, 8MHz internal clock)  |
| **Bluetooth Module** | HC-05 (UART-based serial communication)           |
| **Ultrasonic Sensor**| 4× HC-SR04 (front, back, left, right)             |
| **Motor Driver**     | L298N Dual H-Bridge                                |
| **DC Motors**        | 2 or 4 motor drive (depending on chassis used)    |
| **Power Supply**     | Battery Pack (e.g., 3.7V Li-ion or equivalent)    |

---

## 📁 Repository Structure

```
Embedded-RC-Car/
│
├── include/                  # Header files
│   ├── ultrasonic.h          # Ultrasonic sensor API
│   ├── motor.h               # Motor control API
│   ├── uart.h                # UART communication API
│   └── macros.h              # Global macros and configuration
│
├── src/                      # Source files
│   ├── main.c                # Application entry point
│   ├── ultrasonic.c          # Distance measurement logic
│   ├── motor.c               # Motor control implementation
│   └── uart.c                # UART communication functions
│
├── Makefile                  # Build script (AVR-GCC toolchain)
└── README.md                 # Project documentation
```

---

## ⚙️ System Operation

### Manual Mode
- Controlled via Bluetooth commands sent from a mobile app or terminal.
- Supported commands:  - `f`: move forward
  - `b`: move backward
  - `l`: turn left
  - `r`: turn right
  - `s`: stop

### Autonomous Mode
- Distance measured using four ultrasonic sensors.
- Car makes real-time decisions to avoid obstacles.
- Priority given to the safest direction based on distance data.

---

## 🔨 Build & Flash Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/Adham-amr-1/Embedded-RC-Car.git
   cd Embedded-RC-Car
   ```

2. Compile using AVR-GCC:
   ```bash
   make all
   ```

3. Flash the compiled `.hex` to ATmega32 using avrdude:
   ```bash
   avrdude -c usbasp -p m32 -U flash:w:main.hex
   ```

> 💡 Ensure your fuse bits and clock settings are correct for 8MHz operation.

---

## 📜 License

This project is licensed under the [MIT License](LICENSE), allowing reuse with attribution.

---
