# Orbital CubeSat — Flight Software Development

> **Personal development repository for my work on the Knight's Satellite Club Orbital CubeSat project at UCF.**
>
> This is not the official project repository. This repository documents my individual development work, experiments, technical contributions, and progress as a member of the Software Team.

## Mission Overview

The **Orbital CubeSat Project** is an initiative by the **Knight's Satellite Club at the University of Central Florida (UCF)** focused on designing, integrating, and ultimately launching a low-cost CubeSat into Low Earth Orbit (LEO).

A central objective of the mission is to demonstrate that meaningful satellite development and scientific research can be accomplished using a comparatively low-cost and accessible architecture. By reducing the financial and technical barriers associated with satellite development, the project can serve as a blueprint for future student, educational, and research missions.

The satellite is being developed around the **PROVES Kit**, a CubeSat platform developed by Bronco Space. Using an existing satellite platform gives the team a tested baseline from which additional mission-specific systems and payloads can be developed and integrated.

Rather than designing the spacecraft entirely from scratch, the project can therefore place greater emphasis on:

- Flight software development
- Payload integration
- Ground-to-space communications
- Scientific experimentation
- System testing and validation
- Launch preparation
- Regulatory and operational requirements

A major design goal is **modularity**. Payloads and integrated systems are intended to function as replaceable modules, allowing the CubeSat architecture to support different scientific experiments in future missions without requiring the entire spacecraft to be redesigned.

---

## Mission Objectives

The Orbital CubeSat mission aims to demonstrate a low-cost path from university satellite development to orbital operation.

Major mission objectives include:

- Build and integrate a functional CubeSat using the **PROVES platform** as the baseline architecture.
- Successfully deploy the spacecraft into **Low Earth Orbit**.
- Establish communication between the spacecraft and the **UCF ground station**.
- Maintain reliable spacecraft power and flight-software operation following deployment.
- Develop an architecture capable of supporting **interchangeable scientific payloads**.
- Collect scientific and engineering telemetry from orbit.
- Investigate the effects of the **Low Earth Orbit radiation environment on commercial microcontrollers and electronics**.
- Demonstrate an architecture that future student and research teams can adapt for additional missions.

Mission success begins with successful deployment and spacecraft startup, followed by establishing reliable communication with the ground station and receiving telemetry and scientific data.

---

## 🔬 Scientific Payload Concept

One area of investigation for the mission is the effect of the **LEO radiation environment on commercially available electronics and microcontrollers**.

Space presents a significantly different operating environment from terrestrial electronics applications. Radiation exposure can cause temporary faults, data corruption, unexpected processor behavior, and potentially permanent hardware damage.

By operating commercial electronics in orbit and monitoring their behavior, the mission can provide useful experimental data while investigating whether inexpensive, readily available hardware can be used effectively in future low-cost spacecraft.

The CubeSat is also being designed around a **modular payload philosophy**.

Payload modules may have their own:

- Physical/space requirements
- Power requirements
- Mass limitations
- Electrical interfaces
- Wiring requirements
- Data interfaces
- Software requirements

This allows future payloads to potentially be exchanged while retaining much of the underlying spacecraft architecture.

---

## Flight Software

I am working as a member of the **Orbital CubeSat Software Team**.

The flight-software stack is being developed primarily using:

**CircuitPython**

with the **PySquared** software/library ecosystem and the PROVES CubeSat architecture.

The software is responsible for coordinating spacecraft hardware and supporting autonomous satellite operation after deployment.

Flight-software development may involve areas including:

- Spacecraft initialization and boot procedures
- Hardware interfaces
- Sensor acquisition
- Telemetry collection
- Payload communication
- Radio communications
- Power monitoring
- Fault detection and recovery
- Data handling
- Mission state management
- Ground-station command processing
- Autonomous spacecraft operations

Because physical access to a satellite is impossible after deployment, reliability and fault tolerance are major considerations throughout flight-software development.

---

## 🧠 Software Architecture

The CubeSat software must coordinate multiple spacecraft subsystems while operating with limited computational resources, power, communications bandwidth, and opportunities for direct intervention.

The planned software architecture is therefore centered around predictable spacecraft behavior and clearly defined interfaces between hardware, software, communications, and payload systems.


Conceptual flow:

```
                     ┌─────────────────────┐
                     │    Ground Station   │
                     │         UCF         │
                     └──────────┬──────────┘
                                │
                         Radio Communication
                                │
                     ┌──────────▼──────────┐
                     │       CubeSat       │
                     │                     │
                     │   Flight Software   │
                     │ CircuitPython /     │
                     │     PySquared       │
                     └──────────┬──────────┘
                                │
              ┌─────────────────┼─────────────────┐
              │                 │                 │
        ┌─────▼─────┐    ┌──────▼──────┐   ┌─────▼─────┐
        │ Spacecraft│    │   Payload   │   │   Radio   │
        │  Sensors  │    │   Module    │   │  System   │
        └───────────┘    └─────────────┘   └───────────┘
```

## 📡 Communications

A functioning communication link between the spacecraft and the UCF ground station is a critical mission requirement.

The communications system will enable the team to receive spacecraft telemetry and scientific data while also supporting commands sent from the ground.

Software responsibilities associated with communications may include:

```text
Satellite
    ↓
Telemetry generation
    ↓
Packet / data preparation
    ↓
Radio transmission
    ↓
UCF Ground Station
    ↓
Telemetry processing & analysis
```

The exact communication architecture, radio configuration, frequencies, packet structure, and protocols will be documented as those systems are finalized.

---

## 🚀 Concept of Operations

Following launch and deployment, the spacecraft will transition through a sequence of operational phases.

At a high level:

```text
Launch
  ↓
Orbital Deployment
  ↓
Spacecraft Power-On
  ↓
Flight Software Initialization
  ↓
Subsystem Checks
  ↓
Ground Station Contact
  ↓
Telemetry & Mission Operations
  ↓
Payload Experiments
  ↓
Continued Orbital Operations
  ↓
Passive Deorbit
```

Each stage introduces different software and hardware requirements. Flight software must be capable of handling initialization, communication, data collection, payload operation, and unexpected spacecraft conditions with limited or no immediate human intervention.

---

## Reliability & Risk

Spacecraft software must account for failure modes that are uncommon in conventional software systems.

Potential risks include:

- Radiation-induced faults
- Unexpected resets
- Communication loss
- Sensor failures
- Payload failures
- Power limitations
- Data corruption
- Hardware communication failures
- Software deadlocks or crashes

Mitigation strategies can include watchdog systems, defensive programming, state validation, recovery procedures, redundant data, extensive ground testing, and clearly defined safe operating states.

These considerations will become increasingly important as the software progresses toward flight readiness.

---

## My Work

This repository serves as a **personal engineering log and portfolio of my contributions to the Orbital CubeSat Software Team**.

My work is currently focused on learning and developing within the project's flight-software environment, including:

- **CircuitPython**
- **PySquared**
- PROVES CubeSat software architecture
- Embedded hardware/software interfaces
- Satellite flight-software concepts
- Telemetry and spacecraft communications
- Fault-tolerant embedded software

As development progresses, this repository will contain implementations, experiments, testing, documentation, and other work that I personally contribute to the project.

---

## Knight's Satellite Club

**University of Central Florida**

**Project:** Orbital CubeSat  
**Team:** Software  
**Platform:** PROVES CubeSat  
**Flight Software:** CircuitPython / PySquared  
**Mission Environment:** Low Earth Orbit

---
