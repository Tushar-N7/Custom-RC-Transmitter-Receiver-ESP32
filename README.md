# Custom-RC-Transmitter-Receiver-ESP32

This project is a **DIY wireless RC system** built from scratch using **ESP32** boards and **NRF24L01+** modules.  
It consists of:
- A **transmitter** with dual joystick modules, LEDs, and switches.
- A **receiver** that controls up to 4 servo motors.  

Both circuits are powered by **LiPo batteries** with a TP4056 charging module (on the TX side), all built on perfboards after hours of soldering.

---

## ✨ Features
- Wireless joystick-based control using **NRF24L01+** modules.
- **ESP32** as the main controller for both TX and RX.
- Controls up to **4 servo motors** on the receiver.
- **LiPo-powered transmitter** with built-in charging (TP4056).
- **2 LEDs** (power & status) with resistors on both TX and RX.
- Compact **perfboard build** with capacitors for stable RF power.
- Easily extendable for robotics, RC cars, or IoT applications.

---

## 🛠 Hardware Setup

### **Transmitter Components:**
- ESP32 Dev Board  
- NRF24L01+ Module  
- 2 Joystick Modules  
- 2 LEDs + Resistors (for power & status)  
- 2 On/Off Switches (main power + mode)  
- **224J 400V MPE Capacitor** (for NRF stability)  
- LiPo Battery (3.7V)  
- TP4056 Charging Module  
- Perfboard + Soldered Connections  

### **Receiver Components:**
- ESP32 Dev Board  
- NRF24L01+ Module  
- 4 Servo Motors  
- 2 LEDs + Resistors (power & signal)  
- **224J 400V MPE Capacitor**  
- Powered directly from ESP32 (temporary — MP1495 buck converter planned)  
- Perfboard Build  

---

## 🔌 Pin Connections

### **Transmitter (ESP32):**
| Component     | Pin (ESP32)      |
|---------------|------------------|
| NRF24L01 CE   | GPIO 5           |
| NRF24L01 CSN  | GPIO 17          |
| NRF24L01 MOSI | GPIO 23          |
| NRF24L01 MISO | GPIO 19          |
| NRF24L01 SCK  | GPIO 18          |
| Joystick 1 X  | GPIO 32          |
| Joystick 1 Y  | GPIO 33          |
| Joystick 2 X  | GPIO 34          |
| Joystick 2 Y  | GPIO 35          |
| LED 1         | GPIO 25          |
| LED 2         | GPIO 26          |

### **Receiver (ESP32):**
| Component     | Pin (ESP32)      |
|---------------|------------------|
| NRF24L01 CE   | GPIO 5           |
| NRF24L01 CSN  | GPIO 17          |
| NRF24L01 MOSI | GPIO 23          |
| NRF24L01 MISO | GPIO 19          |
| NRF24L01 SCK  | GPIO 18          |
| Servo 1       | GPIO 21          |
| Servo 2       | GPIO 22          |
| Servo 3       | GPIO 25          |
| Servo 4       | GPIO 26          |
| LED 1         | GPIO 27          |
| LED 2         | GPIO 14          |

---

## ⚙️ How It Works
The transmitter ESP32 reads joystick values and sends them wirelessly through the NRF24L01+ module using SPI.  
The receiver ESP32, with another NRF24L01+, listens on the same address. When data arrives, it maps the joystick values to servo positions in real-time.

---

## 🚀 Future Plans
- Upgrade to **NRF24L01+ PA/LNA** for long-range communication (up to 1 km).  
- Add a **buck converter (MP1495)** to safely power servos on the receiver.  
- Design a **custom PCB** for both transmitter and receiver.  
- Add **OLED display** on transmitter for telemetry.  
- Explore **ELRS (ExpressLRS)** modules for advanced control in future versions.

---

## 🧠 Learnings
This project taught me about:
- Reliable **SPI communication** between ESP32 and RF modules.
- Power stability for RF modules (capacitor decoupling).  
- Mapping analog joystick values to PWM for servo control.  
- Optimizing RF24 settings for range and reliability.

---

## 📅 What’s Next?
This is **Part 1** of my custom RC project.  
In **Part 2**, I’ll share:
- A **custom PCB design** (using EasyEDA).  
- A **demo video** with servo response.  
- Possibly an **upgrade to ELRS** modules for longer range.  
