# EZERV AgentQ

**Experiment. Evaluate. Optimize. Trust Your AI.**

EZERV AgentQ is a planned platform for repeatable testing and evaluation of large language models, AI agents, browser-based workflows, and AI-enabled IoT applications. It is intended to help teams compare configurations using measurable outcomes rather than relying only on manual prompts or demonstrations.

> **Project status:** This repository README is based on the project concept and proposed student MVP. Implementation and setup instructions will be added as the software is developed.

## What AgentQ aims to do

- Evaluate model outputs against reference-based and rule-based checks.
- Test agent task completion, permitted tool selection, tool arguments, action sequences, and recovery from selected failures.
- Automate a controlled web application with Playwright and retain test evidence.
- Simulate IoT sensor data, device states, network conditions, and failures.
- Use Design of Computer Experiments (DoCE) and statistical analysis to compare factors such as model, prompt, and environment.
- Report quality, reliability, latency, token usage, and estimated cost.
- Explore quantum-assisted test selection or scheduling on small problems and compare results with classical baselines.

## Initial demonstration

The proposed first scenario is a **simulated smart-irrigation agent**. It receives soil-moisture readings, weather information, and water-availability status, then chooses an action through a mock pump-control API. Tests check the decision, tool call, parameters, resulting simulated device state, and behavior under selected sensor or network failures.

The initial demonstration is intended to use simulated sensors and a mock actuator. It must not control an operational pump or other safety-critical device.

## Proposed MVP

The first release is scoped around one repeatable workflow:

1. Define a project and a small set of test cases.
2. Run tests against at least two model configurations where access and budget allow.
3. Test one tool-using agent and one controlled browser application.
4. Simulate one IoT scenario, including normal and failure conditions.
5. Run a documented DoCE experiment with repeated trials and suitable statistical analysis.
6. Compare one small quantum-assisted test-selection or scheduling experiment with a classical baseline.
7. Review results in a dashboard and export a report.

## Planned technology

| Area | Proposed tools |
| --- | --- |
| User interface | Streamlit |
| Application and model adapters | Python; FastAPI is an option |
| Agent integrations | A small initial set such as LangGraph, CrewAI, or a custom adapter |
| Browser automation | Playwright |
| IoT simulation | Python; MQTT/Mosquitto is optional |
| DoCE and statistics | SciPy, Statsmodels, Pandas, and a suitable DoCE library |
| Quantum exploration | Qiskit and Qiskit Aer |
| Storage and visualization | SQLite for the MVP; Plotly or Matplotlib |
| Testing | PyTest and project-specific assertions |

These are proposed choices, not a statement that the components are already implemented.

## Evaluation principles

- Define acceptance criteria for each test and report variability across repeated runs.
- Combine deterministic checks, reference-based evaluation, and human review where appropriate.
- Treat LLM-as-judge results as an aid, not ground truth.
- Record relevant model, prompt, dataset, software, environment, and seed information.
- Compare quantum-assisted and classical methods on the same instances; do not claim quantum advantage without evidence.

## Safety and data handling

- Use isolated test environments, synthetic accounts, and non-production data for browser automation.
- Use mock IoT actuators, tool allowlists, parameter validation, and execution limits.
- Protect API keys with environment variables or a secrets manager; never commit credentials.
- Document evaluator limitations, pricing assumptions, and third-party license requirements.

## Development status

The project plan proposes a 16-week student MVP, progressing from requirements and test execution through agent and browser testing, IoT simulation, DoCE, quantum exploration, and final integration. Detailed installation, configuration, and contribution instructions will be added when the corresponding code and project tooling are available.
