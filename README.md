# Obstacle-Avoidance & Line-Following Robotic Car

> **Status:** In Development (Work in Progress)
> **Author:** Toluwanimi Jesusina
> **Year:** 2024 – Present

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Status](https://img.shields.io/badge/Status-WIP-orange)]()

---

## 1. What is this?

A robotic vehicle incorporating DC motors, ultrasonic sensors, and IR line-following modules. The system implements a Finite State Machine (FSM) control architecture for autonomous decision-making logic, enabling the robot to navigate dynamic environments by avoiding obstacles and following a predefined line path.

---

## 2. Why was it built?

To develop practical skills in:
- Finite State Machine (FSM) design
- Sensor fusion (ultrasonic + IR)
- Real-time control of DC motors
- Autonomous decision-making

---

## 3. Objectives

| # | Objective | Status |
|---|-----------|--------|
| 1 | Design FSM control architecture | 🔄 In Progress |
| 2 | Interface ultrasonic sensor | 🔄 In Progress |
| 3 | Interface IR line-following module | 🔄 In Progress |
| 4 | Implement motor control (H-Bridge) | 🔄 In Progress |
| 5 | Test in dynamic environment | ⏳ Pending |

---

## 4. System Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    OBSTACLE-AVOIDANCE ROBOT                                 │
│                                                                             │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐                       │
│  │  Ultrasonic  │  │  IR Line     │  │  Motor       │                       │
│  │  Sensor      │  │  Sensors     │  │  Driver      │                       │
│  │  (HC-SR04)   │  │  (Array)     │  │  (L298N)     │                       │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘                       │
│         │                 │                 │                               │
│         └─────────────────┴─────────────────┘                               │
│                                    │                                        │
│                          ┌─────────▼─────────┐                              │
│                          │  Microcontroller  │                              │
│                          │  (Arduino/STM32)  │                              │
│                          │                   │                              │
│                          │  FSM Logic:       │                              │
│                          │  - IDLE           │                              │
│                          │  - LINE_FOLLOW    │                              │
│                          │  - AVOID_OBSTACLE │                              │
│                          │  - STOP           │                              │
│                          └─────────┬─────────┘                              │
│                                    │                                        │
│                          ┌─────────▼─────────┐                              │
│                          │  2x DC Motors     │                              │
│                          │  (with Wheels)    │                              │
│                          └───────────────────┘                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 5. FSM State Design

| State | Description | Transition Condition |
|-------|-------------|---------------------|
| IDLE | Robot stationary | Start button pressed → LINE_FOLLOW |
| LINE_FOLLOW | Follow line using IR sensors | Obstacle detected → AVOID_OBSTACLE |
| AVOID_OBSTACLE | Stop, reverse, turn | Path clear → LINE_FOLLOW |
| STOP | Emergency stop | Reset → IDLE |

---

## 6. Hardware

| Component | Specification |
|-----------|--------------|
| Microcontroller | Arduino UNO / STM32 |
| Motor Driver | L298N |
| Motors | 2x DC Gear Motors |
| Ultrasonic | HC-SR04 |
| IR Sensors | 2x (left/right) |
| Chassis | 2WD Acrylic |

---

## 7. Implementation Status

- [x] Chassis assembly
- [x] Motor driver wiring
- [x] Ultrasonic sensor interface
- [x] IR sensor interface
- [ ] FSM implementation
- [ ] Testing and tuning
- [ ] Documentation

---

## 8. Limitations (Current)

1. **Incomplete** — FSM logic not fully implemented.
2. **No Code Uploaded** — Source code pending.
3. **No Test Results** — Testing not yet conducted.

---

## 9. Future Development

| Priority | Enhancement |
|----------|-------------|
| 1 | Complete FSM implementation |
| 2 | Test obstacle avoidance |
| 3 | Test line following |
| 4 | Optimize motor control (PID) |
| 5 | Add Bluetooth control |

---

## 10. Media

*[Pending — no photos/videos available yet]*

---

## 11. Repository Structure

```
obstacle-avoidance-line-following-car/
├── README.md
├── LICENSE
├── src/
│   └── main.ino
├── docs/
│   ├── FSM_Design.md
│   └── Testing.md
└── media/
```

---

## 12. License

MIT License — see [LICENSE](LICENSE) for details.

---

## 13. Contact

**Toluwanimi Jesusina**
- Email: [your.email@example.com](mailto:your.email@example.com)
- LinkedIn: [linkedin.com/in/toluwanimi-jesusina](https://linkedin.com/in/your-profile)
```
