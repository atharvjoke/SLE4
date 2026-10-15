# CONTRIBUTING

Thank you for your interest in the AI Refrigerator Agent project.

This repository documents **SLE-4: Final Viva & Architecture Decision Record (ADR)** for **02AML204 – Introduction to Artificial Intelligence**.

## Contribution Guidelines
1. Read `README.md` to understand the project and its accepted architecture decision.
2. Keep changes consistent with the modular design and the separate Decision Engine.
3. Give each module a clear responsibility:
   - Input/Sensor Module
   - State Manager
   - Decision Engine
   - Action Controller
   - Alert/Output Module
4. Keep architecture documentation, diagrams, and code descriptions consistent with one another.
5. Do not describe a feature as implemented unless working code has been added and tested.
6. Do not use the SLE-2 BFS/DFS timings as performance evidence for the refrigerator agent; they belong to a separate graph experiment.
7. If adding decision rules, explain their purpose and include suitable tests where possible.

## Suggested Areas for Improvement
- Add or refine diagrams for the C4 Context, Container, Component, and Code levels.
- Implement and test the sensor-input and state-management flow.
- Define decision rules for cooling, reducing cooling, alerts, and no change.
- Test edge cases such as high temperature, an open door, and missing item-condition data.
- Document module interfaces and how actions are passed to the Action Controller.
- Add test results from representative refrigerator-agent scenarios before making performance claims.

## Reporting an Issue
When reporting an issue, include:
- A clear title.
- A description of the expected behaviour.
- The actual behaviour, if applicable.
- Steps to reproduce the issue, if applicable.

## Academic Project Note
This is an academic project. Contributions should support learning, clear design decisions, testability, and accurate documentation. The student remains responsible for reviewing and explaining submitted work.
