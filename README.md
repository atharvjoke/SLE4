# SLE4
# AI Refrigerator Agent — SLE-4

## Overview
The **AI Refrigerator Agent** monitors refrigerator temperature, door status, and item-condition information, then chooses an appropriate action such as cooling, reducing cooling, issuing an alert, or making no change.

This repository documents **SLE-4: Final Viva & Architecture Decision Record (ADR)** for the course **02AML204 – Introduction to Artificial Intelligence**.

## Student Details
- **Name:** Atharv Jindatta Joke
- **PRN:** 25UAM047
- **Division:** A
- **SLE-4 Date:** 12 October 2026

## Architecture Decision Record (ADR)
**Decision:** Use a modular architecture with a separate Decision Engine.  
**Status:** Accepted

The Decision Engine evaluates the current refrigerator state and selects an action. Other modules handle input collection, state management, action execution, and user alerts.

### Main Modules
1. **Input/Sensor Module** — collects temperature, door-status, and item-condition information.
2. **State Manager** — maintains the current refrigerator state.
3. **Decision Engine** — evaluates the state and chooses the next action.
4. **Action Controller** — performs or requests the selected refrigerator action.
5. **Alert/Output Module** — displays status and sends user alerts.

### Alternatives Considered
- **Monolithic design:** input, rules, and actions handled in one function or module.
- **Direct sensor-to-action flow:** sensor readings trigger actions without a separate current-state model.
- **Modular design without a separate Decision Engine:** decision rules are mixed into input or action handling.

### Rationale
- Each module has a clear responsibility, making the design easier to explain and test.
- The State Manager allows decisions to use the current refrigerator state rather than isolated sensor readings.
- The separate Decision Engine makes decision rules easier to review or change without redesigning input collection or action execution.
- The component design separates decision-making into the State Evaluator, Rule/Condition Checker, Goal/Safety Checker, and Action Selector.

### Consequences and Trade-offs
**Benefits**
- Decision rules can be changed with less impact on other modules.
- Modules can be explained and tested separately.
- The data flow is easier to follow.

**Trade-offs**
- Additional modules require clear interfaces and communication.
- Modularity does not itself prove faster execution; representative tests would be needed to measure performance.

## SLE Journey
- **SLE-1:** Selected the AI Refrigerator Agent as the project.
- **SLE-2:** Profiled BFS and DFS on the same small directed graph over 1,000 runs. The report recorded BFS at **0.003387 ms** average runtime with 9 nodes expanded, and DFS at **0.009296 ms** with 6 nodes expanded. These are graph-experiment results, not refrigerator-agent performance benchmarks.
- **SLE-3:** Documented the agent using the four C4 levels: Context, Container, Component, and Code.
- **SLE-4:** Recorded the decision to keep the Decision Engine separate for clarity and independent testing.

## Viva Preparation
- **Why separate the Decision Engine?** It keeps decision rules independent from sensor input and action execution.
- **Why use a State Manager?** Decisions should consider the current refrigerator state, not only one sensor reading.
- **Which alternatives were rejected?** A monolithic design, direct sensor-to-action logic, and mixing decisions into other modules.
- **What did SLE-2 show?** BFS had lower measured average runtime, while DFS expanded fewer nodes on that particular graph. The small test should not be over-interpreted.
- **What is needed to claim better performance?** Test the refrigerator agent with representative inputs under consistent conditions.

## AI Contribution Note
ChatGPT helped organize the ADR, explain alternatives and trade-offs, and align the document with the SLE-4 structure. The student selected the project, reviewed the proposed modules and design, and is responsible for understanding and defending the decision during the viva.

## Project Status
This repository documents the SLE-4 architecture decision and viva preparation. The report does not, by itself, establish that a complete working refrigerator-agent implementation is included.
