# Railway Level-Crossing Control System (ARLCCS)

## Project Overview

The Automated Railway Level-Crossing Control System (ARLCCS) is a safety-critical software system designed to automatically control road traffic whenever a train approaches, passes through, or clears a railway crossing.

### System Components

- **Train-detection sensors** — Detect approaching, passing, and cleared trains
- **Road barriers** — Physical barriers that close/open to control traffic
- **Warning lights & audible alarms** — Alert road users of approaching trains
- **Traffic signals** — Control road traffic flow
- **Safety-monitoring unit** — Monitors system state and failures
- **Control-center interface** — Allows human operators to monitor and override

### Primary Safety Objective

**Prevent road traffic from entering the crossing while a train is approaching, passing through, or while the system cannot safely confirm that the crossing is clear.**

### Normal Operation Sequence

1. Train approaches → Detection triggers
2. Warning signals activate (lights + alarms)
3. Road barriers close
4. Barriers remain closed while train passes
5. Train completely clears crossing
6. System confirms crossing is clear
7. Barriers open

### Abnormal Situations Handled

- Sensor failures
- Barrier failures
- Communication loss
- Incorrect sensor readings
- Emergency conditions

---

## Verification Tasks

This repository contains a formal constraint analysis covering:

- **Task 1** — Identify Constraints (12 constraints)
- **Task 2** — Formalize Constraints (10 formal expressions)
- **Task 3** — Identify Constraint Violations (violation scenarios)

See **[Constraint Analysis](docs/Constraint_Analysis.md)** for the complete analysis.

---

## Key Safety Principles

1. **When in doubt, choose safety** — If sensor information is unreliable, keep the barrier closed
2. **Confirm before opening** — The barrier must not open until the system has confirmed the train has completely cleared
3. **Detect failures actively** — The system must verify that commanded actions (like barrier closure) actually occurred
4. **Maintain safe state on communication loss** — Loss of control-center communication does not excuse unsafe operation
5. **Emergency overrides all** — Emergency conditions require immediate safety response

---

## Document Structure

```
Railway-Level-Crossing-Control-System/
│
├── README.md (this file)
└── docs/
    └── Constraint_Analysis.md (full formal analysis)
```

---

## Author

Software Verification Team

## Date

2024
