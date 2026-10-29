# Robot Motor Driver Component Selection

## 1. Motor Subsystem – H-Bridge

| Option | Pros | Cons | Photo | Link | Cost |
|---|---|---|---|---|---|
| **L298N Dual H-Bridge (Arduino Albers)** | Inexpensive dual-channel driver; controls two brushed DC motors independently; supports forward and reverse; widely used with many tutorials and wiring diagrams; straightforward to interface with a microcontroller; includes flyback protection circuitry on common modules; many modules include a 5V regulator. | Large voltage drop (often around 1.5–2V or more under load) reduces motor voltage and torque; inefficient bipolar-transistor design generates heat; practical continuous current depends on cooling and module design; bulky compared with modern MOSFET drivers; onboard 5V regulator may not suit every power arrangement. | <img width="1094" height="838" alt="image" src="https://github.com/user-attachments/assets/d0c63f44-d727-4319-92a6-e70d9907a7ce" />| [Product link](#) | $15.39 |
| **DRV8833 – KOOBOOK Dual H-Bridge** | Efficient MOSFET design; supports two brushed DC motors; forward/reverse and PWM speed control; 2.7–10.8V motor supply range; low standby power; compact size; suitable for smaller battery-powered robots. | **Not suitable for a 12V motor supply** because its motor voltage limit is 10.8V; current capacity depends on the module, package, and cooling; may not handle motors with high stall current; small pins require careful wiring; typically has no onboard 5V regulator. | <img width="624" height="666" alt="image" src="https://github.com/user-attachments/assets/2dd1bbcb-0858-44e8-822f-749a3353fedb" /> | [Product link](#) | $8.99 |
| **A3909GLYTR-T – Allegro MicroSystems** | Compact dual H-bridge IC; supports two small brushed DC motors; efficient MOSFET output stage; useful for compact embedded designs; PWM control enables speed adjustment; low-power design. | Bare surface-mount IC is difficult to solder by hand; low-voltage motor supply makes it unsuitable for 12V motors; current capability is limited compared with larger motor-driver boards; requires external components and careful PCB layout; no screw terminals on the bare IC. | <img width="386" height="414" alt="image" src="https://github.com/user-attachments/assets/83a7dbca-5bbd-4a81-a1da-3e6850afaeb0" /> | [Product link](#) | $1.82 |
| **Cytron MDD10A – 10A, 5–30V Dual-Channel DC Motor Driver** | Controls two brushed DC motors independently; supports forward and reverse; PWM speed control; 5–30V motor supply range; rated for up to 10A continuous per channel under specified operating conditions; 3.3V logic HIGH is compatible with the PIC18F57Q43; suitable for many medium-current robotics drive motors. | More expensive than basic driver modules; no reverse-polarity protection; requires careful wiring and power connections; actual current capability depends on operating conditions and cooling; motor stall current must be checked before use; does not eliminate the need for a battery capable of supplying the complete system's current. | <img width="1104" height="822" alt="image" src="https://github.com/user-attachments/assets/e9c5fa31-6f02-44d4-a96a-352f15d1e25b" /> | [RobotShop – Cytron MDD10A](https://www.robotshop.com/products/cytron-10a-5-30v-dual-channel-dc-motor-driver) |

### Motor Driver Recommendation

**Preferred candidate: Cytron MDD10A**

**Rationale:** The Cytron MDD10A can control both 12V wheel motors independently, allowing the robot to move forward, reverse, turn, and adjust wheel speed using PWM. Its 5–30V motor supply range and 3.3V-compatible logic make it a promising option for the PIC18F57Q43 Curiosity Nano.

Before purchasing, verify the exact motors' stall current and confirm that the battery, wiring, and driver can safely support the combined load. The advertised driver current rating does not mean the battery can supply that current.

---

## 2. Right/Left DC Motor Subsystem

| Option | Pros | Cons | Photo | Link | Cost |
|---|---|---|---|---|---|
| **24V – 1800 RPM Slow-Speed DC Motor** | Potentially inexpensive; lightweight and compact depending on model; high rotational speed may be useful for certain mechanisms; widely available in hobby and industrial marketplaces. | 1800 RPM is generally too fast for direct wheel drive without substantial gear reduction; torque and current may be unsuitable for a loaded robot; specifications must be verified because the stated 24V rating conflicts with the original 3–12V description; no encoder unless explicitly included; quality and lifespan vary. | <img width="238" height="226" alt="image" src="https://github.com/user-attachments/assets/82377e43-b6d8-49b2-a918-d1c28c0c4910" /> | [Product link](#) | $19.95 |
| **JOHNSON ELECTRIC – C4557-60003 / HC615LG / 65701 (6–18V DC)** | Potentially useful for robotics if the exact model's torque and speed are appropriate; established motor manufacturer; may be suitable for compact mechanisms; potentially compatible with several DC supply voltages within its specified rating. | Exact torque, RPM, rated current, and stall current must be verified for the specific model; may require a gearbox for wheel drive; mounting dimensions must be checked; encoder availability is uncertain; current draw could exceed a small motor driver's limits. | <img width="192" height="194" alt="image" src="https://github.com/user-attachments/assets/72e029d7-9238-49c1-af9d-adc5e83d1289" /> | [Product link](#) | $8.98 |
| **BOJACK Type 130 EK1450 Mini DC Motors (3–6V)** | Multi-pack can be useful for experiments and replacements; standardized small motor format; inexpensive; useful for small fans and lightweight prototypes; compatible with low-voltage drivers such as the DRV8833 when operated within specifications. | Low torque compared with geared wheel motors; generally unsuitable for directly driving a full-size robot vacuum; not designed for a 9–12V supply; no encoder unless separately fitted; detailed torque and stall-current specifications may be unavailable. | <img width="184" height="296" alt="image" src="https://github.com/user-attachments/assets/76b060cc-ea4e-4596-85a0-6a9db3917e7d" /> | [Product link](#) | $8.98 |
| **Greartisan 12V 100RPM Gear Motor – 37mm Gearbox, Centric Output Shaft** | 12V rated voltage; approximately 100 RPM no-load output speed; gearbox helps provide useful wheel torque; published rated torque of approximately 4.5 kg·cm; published rated current of approximately 1,100 mA; suitable candidate for a differential-drive robot when correctly sized. | Exact stall current has not been verified; startup current can exceed rated current; no encoder unless included in the purchased version; gearbox and shaft dimensions must match the wheel and chassis; two motors plus the suction motor may exceed the selected battery's output-current rating. | <img width="188" height="204" alt="image" src="https://github.com/user-attachments/assets/1c38d677-6f2a-45c4-be5f-53556687f590" /> |9.99 |

### DC Motor Recommendation

**Preferred candidate: Two Greartisan 12V 100RPM gear motors**

**Rationale:** These geared motors are a more appropriate starting point for the robot's left and right drive wheels than a high-speed, non-geared motor. Each motor has a published rated current of approximately 1,100 mA, giving a combined rated current of approximately 2,200 mA (2.2A) for both drive motors.

The rated current is not the same as the stall current. Obtain the exact motor's stall-current specification before finalizing the battery and driver. Consider encoder-equipped motors if closed-loop speed control or accurate distance measurement is required.

---

## 3. Voltage Regulator Subsystem – Logic Power Rail

| Option | Pros | Cons | Photo | Link | Price |
|---|---|---|---|---|---|
| **Microchip LDO Regulator (SOT-23-5)** | Small footprint; can provide stable regulated voltage for low-current electronics; low-noise options are useful for sensitive circuits; many models include thermal and current-limit protection; suitable for compact PCB designs when the exact model matches the required voltage. | Exact part number is required to verify input voltage, output voltage, and current rating; linear regulators waste power when dropping a large voltage; heat increases with current and voltage difference; typically unsuitable for powering motors; may not provide enough current for every peripheral. | <img width="374" height="408" alt="image" src="https://github.com/user-attachments/assets/ff374109-a11d-4219-b714-c4a54fbd4c2a" />| [Product link](#) | $2.41 |
| **Automotive-Grade 5V Regulator** | Potentially robust under temperature and electrical transients; suitable models offer overcurrent and thermal protection; useful for regulated logic power in demanding environments; some models tolerate high input voltages. | Specifications depend on the exact part number; not every automotive regulator supports a 12V battery input or the desired output current; linear types can waste significant power and generate heat; generally not appropriate for driving motors; may cost more than a basic regulator. | <img width="346" height="524" alt="image" src="https://github.com/user-attachments/assets/94ebe7ff-c578-4461-b373-c614fa000508" />| [Product link](#) | $8.99 |



## 4. Final Component Choices

**Motor Driver Choice:** Cytron MDD10A – 10A, 5–30V Dual-Channel DC Motor Driver

**Reason:** Provides two independently controlled motor channels, forward/reverse operation, and PWM speed control. Its motor voltage range includes the 12V drive motors, and its logic inputs are compatible with the PIC18F57Q43's 3.3V outputs. Confirm stall-current limits and cooling requirements before use.

**Right/Left DC Motor Choice:** Two Greartisan 12V 100RPM geared DC motors

**Reason:** Geared output is appropriate for a small differential-drive robot. The approximately 100RPM no-load output speed is a reasonable starting point for wheel-drive prototyping. Confirm wheel diameter, expected robot weight, required torque, and stall current before finalizing the selection.

**Voltage Regulator Choice:** To be determined after confirming the Curiosity Nano power-input requirements and the current needs of all logic components. Mainly looking into microchip regulator for similar knowledge, and modern pins.

**Rationale:** The logic power system must provide the correct voltage and sufficient current without exposing the microcontroller to the 12V motor supply.

---

## 5. Power Supply Compatibility and Safety
Assuming that were along the lines of the same battery, I have simple lithium battery pack for lightweight package. Ranging between 6V - 12V Power Supply.

## 6. Product Reference Links

- [Cytron MDD10A – RobotShop](https://www.robotshop.com/products/cytron-10a-5-30v-dual-channel-dc-motor-driver)
- [Greartisan 12V 100RPM Gear Motor – Amazon](https://www.amazon.com/dp/B072R57C56)
- [DRV8833 Motor Driver Search](https://www.amazon.com/s?k=DRV8833+dual+motor+driver)
- [L298N Motor Driver Search](https://www.amazon.com/s?k=L298N+dual+H-bridge+motor+driver)
- [12V 100RPM Gear Motors with Encoders](https://www.amazon.com/s?k=12V+100RPM+37mm+gear+motor+encoder)
