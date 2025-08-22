# MineNet: Bare-Metal Mesh Telemetry for Mining Helmets

## Overview
MineNet is a purpose-built communication and telemetry system for underground mining operations.  
It combines bare-metal embedded programming, mesh networking, and real-time telemetry to enable reliable communication between mining helmets, even in signal-dead underground environments.

---

## Breakdown of Key Terms

### 1. MineNet
- Why it matters: Indicates the system is designed specifically for mining, not a generic IoT solution.  
- Processor & Comms: Suggests custom hardware + protocol tailored to hostile underground environments.

### 2. Bare-Metal
- Why it matters: No operating system, no pre-built Wi-Fi or BLE stacks.  
- Processor view: Direct register-level coding on the microcontroller (timers, UART, SPI).  
- Signals & Comms view: You build your own protocol → packet framing, timing sync, collision handling.

### 3. Mesh
- Why it matters: Every helmet can act as a relay (helmet → helmet → base).  
- Processor view: Requires memory management for packet forwarding.  
- Signals & Comms view: Stronger fault tolerance; communication persists even if one path fails.

### 4. Telemetry
- Why it matters: Structured continuous data (gas levels, motion, environment).  
- Processor view: Data packed into frames before transmission.  
- Signals & Comms view: Transmission efficiency, low-latency encoding, error detection.

### 5. Mining Helmets
- Why it matters: Integrates into PPE, ensuring practical usage.  
- Processor view: Limited space/power, so firmware must be optimized.  
- Signals & Comms view: Dust, reflections, multipath propagation must be handled in protocol design.

---

## Processor Perspective
- Direct bare-metal control → efficient and deterministic timing.
- Microcontrollers act as both sensor managers and packet routers.
- Protocol stack designed from scratch → full ownership of MAC & PHY layer behaviors.

## Signals & Communication Perspective
- Custom PHY: timing, modulation, and error coding tuned for underground propagation.  
- Mesh routing: ensures packets can hop between helmets to overcome dead zones.  
- Reliability mechanisms: ACKs, retransmissions, and collision handling improve robustness.  
- Range extension: more helmets = stronger network, even without line-of-sight.

---

## Summary
MineNet is a bare-metal, mesh-based telemetry system embedded into mining helmets.  
It delivers:
- Robust underground comms (mesh topology bypasses dead zones).  
- Custom lightweight protocol (low power, low overhead).  
- Real-time safety telemetry (gas, motion, environment).  
- Scalability and fault tolerance (more miners = stronger network).  

This approach highlights Processor & Controller (P&C) expertise (register-level protocol design) and Signals & Communication Systems innovation (custom PHY/MAC, mesh routing in harsh conditions).

---
