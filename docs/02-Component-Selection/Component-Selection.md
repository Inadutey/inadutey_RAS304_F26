---
title: Component Selection
---

# Motor Driver Subsystem – H‑Bridge

| Option | Pros | Cons | Photo | Link | Cost |
|--------|------|------|-------|------|------|
| **L298N Dual H‑Bridge (Arduino Albers)** | Inexpensive dual‑channel driver; can control two DC motors (Left + Right) with forward/reverse. Widely used and documented. Tons of tutorials, wiring diagrams, and example code online. Built‑in flyback diodes protect the driver from motor inductive spikes. Simple to interface with PIC, Arduino, Raspberry Pi. On‑board 5V regulator. | Large voltage drop (~2V) → motors receive less voltage, reducing torque and speed. Low efficiency (bipolar transistors) → runs hot and wastes power. Limited current capability (0.8–1.2A continuous). Old design replaced by MOSFET drivers (TB6612FNG, DRV8833, BTS7960). Bulky module. Weak 5V regulator → often must be disabled. | *(add image)* | product link | $15.39 |
| **DRV8833 – KOOBOOK 1.5A Dual H‑Bridge** | Modern MOSFET design → far more efficient than L298N (almost no voltage drop). Low heat generation → runs cool under load. Wide voltage range (2.7V–10.8V). Dual motor support (forward/reverse). High efficiency → better motor torque. Low standby current → ideal for low‑power embedded systems. | Lower maximum current (1.5A peak, ~1A continuous). Not ideal for large or high‑torque motors. Not suitable for 12V motors. Small module size → easier to damage. Requires careful wiring (small pins). No built‑in 5V regulator. | *(add image)* | product link | $8.99 |
| **A3909GLYTR‑T (Allegro)** | Modern MOSFET design → highly efficient, minimal voltage drop. Dual H‑bridge → can independently drive two DC motors or one stepper. Wide voltage range (2.4V–5.5V). Low power consumption → excellent for battery‑powered devices. High PWM frequency → smooth motor control, low audible noise. | Very small QFN package → extremely difficult to solder by hand. Low voltage limit (max ~5.5V). Lower current capability (500–700mA per channel). Requires external components (decoupling caps, layout). Bare IC → no screw terminals or breakout board. | *(add image)* | product link | $1.82 |

---

# Right/Left DC Motor

| Option | Pros | Cons | Photo | Link | Cost |
|--------|------|------|-------|------|------|
| **24V – 1800 RPM Slow‑Speed DC Motor** | Very inexpensive → great for budget builds or prototypes. Lightweight and compact → easy to mount. High RPM → good for lightweight applications. Easy to power (3–12V). Widely available. | Low torque → struggles with heavier loads. No datasheet → specs vary widely. Inconsistent quality (eBay). No encoder → cannot measure speed/position. Short lifespan → brushes wear quickly. RPM fluctuates with voltage. | *(add image)* | product link | $19.95 |
| **JOHNSON ELECTRIC – C4557‑60003 – HC615LG – 65701 (6–18VDC)** | Higher torque → better for wheels, lifting loads, pushing weight. Metal housing → more durable. Better suited for real robotics → handles friction and load. More stable RPM under load. | Higher current draw → may exceed limits of DRV8833/TB6612FNG. No datasheet → exact torque, RPM, stall current unknown. Bulkier and heavier → requires stronger mounting. Quality varies (eBay). No encoder. May require heatsinking. | *(add image)* | product link | $8.98 |
| **BOJACK Type 130 EK1450 Mini DC Motors (3–6V)** | Comes in a multi‑pack → good for testing or replacing motors. Standardized size (130) → easy to find mounts. Decent RPM → good for small robots or fans. Runs on 3–6V → compatible with DRV8833. Better consistency than random eBay motors. | Low torque → not suitable for heavy loads. Still lacks detailed datasheets. No encoder → cannot measure rotation or speed. Not designed for 9–12V systems → may overheat or burn out. Not ideal for long‑term robotics → hobby‑grade. | *(add image)* | product link | $8.98 |

---

# Voltage Regulator (5V Rail)

| Option | Pros | Cons | Photo | Link | Price |
|--------|------|------|-------|------|-------|
| **Microchip LDO (SOT‑23‑5)** | Ultra‑low dropout → maintains stable 5V output even when input voltage is only slightly higher. Very low quiescent current → excellent for battery‑powered systems. High output accuracy → tight regulation for sensitive logic circuits. Built‑in protection (thermal shutdown + current limiting). Small footprint → ideal for compact PCBs. Low noise output → good for analog circuits and microcontroller logic. | Low current capability (300–500mA) → not enough for motors. Requires careful PCB layout. Linear regulator → inefficient when dropping from high input voltages (9V→5V). Generates heat under load. Not ideal for electromechanical systems → best for logic only. | *(add image)* | product link | $2.41 |
| **Automotive‑Grade 5V Regulator** | Automotive‑grade reliability → designed for harsh environments, vibration, temperature extremes. Very stable 5V output → excellent regulation. Low dropout voltage. High input voltage tolerance (up to 40V). Built‑in protections (overcurrent, thermal shutdown, reverse‑battery). Good for embedded systems → robust and predictable. | Lower current capability (150–300mA). Linear regulator → inefficient for high voltage drops (12V→5V). Requires heatsinking under moderate load. More expensive than basic LDOs. Not ideal for powering electromechanical components → best for logic. | *(add image)* | product link | $8.99 |

---

# Final Choices (Fill these in)

**Motor Driver Choice:**  
**Rationale:**  

**DC Motor Choice:**  
**Rationale:**  

**Voltage Regulator Choice:**  
**Rationale:**  


# Voltage Regulator (5V Rail)

| Option | Pros | Cons | Photo | Link | Price |
|--------|------|------|-------|------|-------|
| Microchip LDO | ... | ... | ![](images/ldo.png) | [Product link](#) | $2.41 |
| Automotive‑Grade Regulator | ... | ... | ![](images/regulator.png) | [Product link](#) | $8.99 |

**Choice:** Microchip LDO  
**Rationale:** (your explanation here)
