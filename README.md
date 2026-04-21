This repository provides the reproducibility materials for the paper:

**Industrial Log Analysis Revisited: A Task-Oriented Evaluation of Parsing and Anomaly Detection under Real-World Constraints**

## Overview

Log analysis in industrial software systems presents unique challenges that are often underrepresented in public benchmark datasets. Compared with widely used public repositories such as LogHub, industrial logs typically exhibit higher structural diversity, stronger context dependence, greater semantic ambiguity, and more severe privacy constraints. These characteristics make it difficult to directly reproduce empirical studies based on proprietary industrial datasets.

To address reproducibility concerns as much as possible, we have taken several concrete steps.

First, in collaboration with our industrial partners, we release a set of **representative anonymized log samples** that preserve key structural and semantic characteristics of the original industrial datasets. These samples are intentionally selected to reflect **higher complexity** and **greater divergence from public benchmarks such as LogHub**, thereby capturing essential properties of real-world industrial logs.

Second, we make publicly available the **complete implementation details of our experimental pipeline**, including:

- implementations of log parsing methods,
- implementations of anomaly detection models, and
- an explanatory document (`industrial_log_samples_explanation`) that provides detailed descriptions and summaries of the released industrial log samples.

## Why Industrial Log Analysis Matters

Industrial log analysis is an essential component of modern software-intensive operations because logs often serve as the most direct and persistent record of system behavior during execution. In real-world industrial environments, logs are not merely auxiliary debugging artifacts; they are deeply tied to safety monitoring, fault diagnosis, operational auditing, process coordination, and system recovery. When failures occur in manufacturing lines, process control systems, or critical infrastructure platforms, engineers frequently depend on logs to reconstruct event sequences, identify abnormal transitions, and trace the interaction between software components and physical processes. As a result, the reliability of log parsing and anomaly detection has direct implications for system availability, maintenance efficiency, and operational trustworthiness.

The importance of industrial log analysis is further amplified by the fact that industrial systems usually operate under constraints that are not well represented in public benchmark datasets. Compared with conventional benchmark logs, industrial logs often exhibit higher heterogeneity in formatting, denser domain-specific semantics, stronger coupling with device states and operator actions, and stricter privacy restrictions. These properties make industrial log analysis not only a technical pattern recognition problem but also a practical software engineering challenge shaped by operational context. In particular, errors introduced during parsing can distort event templates, suppress anomaly cues, or misrepresent critical variables, which in turn may propagate to downstream anomaly detection and reduce the practical usefulness of the overall pipeline.

### Dataset Summary

| Dataset | Abbr. | Type | Total Logs | Event Templates | Subset Logs | Anomalies in Subset | Avg. Length (Chars) |
|---|---|---|---:|---:|---:|---:|---:|
| LogHub Subset Benchmark | LHSB | Benchmark | 1,437,705 (6.87% anom.) | 2,472 | 9,040 | 964 (10.7%) | 172.4 |
| Factory Assembly Line Logs | FALL | Industrial | 32,615 (9.56% anom.) | 2,290 | 7,190 | 992 (13.8%) | 227.5 |
| Process Industry Management System Logs | PIMS | Industrial | 871,243 (9.93% anom.) | 4,508 | 14,382 | 1,249 (8.7%) | 312.6 |
| Supervisory Control and Data Acquisition System Logs | SCADA-X | Industrial | 902,377 (12.37% anom.) | 6,039 | 15,110 | 1,013 (6.7%) | 351.1 |

To support a more realistic evaluation setting, our study includes four datasets with clearly differentiated characteristics. The **LogHub Subset Benchmark (LHSB)** is used as the benchmark reference and contains **1,437,705 logs**, with **6.87% anomalies**, **2,472 event templates**, a subset of **9,040 logs**, **964 anomalous instances**, and an average log length of **172.4 characters**. By comparison, the three industrial datasets are structurally richer and semantically more diverse. **FALL (Factory Assembly Line Logs)** contains **32,615 logs** with **9.56% anomalies**, **2,290 event templates**, a subset of **7,190 logs**, **992 anomalous instances**, and an average length of **227.5 characters**. **PIMS (Process Industry Management System Logs)** contains **871,243 logs** with **9.93% anomalies**, **4,508 event templates**, a subset of **14,382 logs**, **1,249 anomalous instances**, and an average length of **312.6 characters**. **SCADA-X (Supervisory Control and Data Acquisition System Logs)** contains **902,377 logs** with **12.37% anomalies**, **6,039 event templates**, a subset of **15,110 logs**, **1,013 anomalous instances**, and an average length of **351.1 characters**. These differences indicate that industrial datasets are not only longer on average, but also substantially more complex in template diversity and operational semantics than the benchmark subset.

The released representative anonymized samples further illustrate why industrial logs deserve dedicated study. In **FALL**, the logs reflect assembly-line software behavior involving motion control, vision inspection, conveyor coordination, operator commands, sensor deviations, and request path failures. In **PIMS**, the logs capture process-state updates, flow regulation, safety checks, integrity failures, sustained numerical drift, scheduler inconsistencies, and authorization problems in process industry management. In **SCADA-X**, the logs describe telemetry synchronization, access sessions, alarm clearance, industrial protocol handshakes, network failures, unauthorized access, and escalation events in supervisory control settings. Together, these examples show that industrial anomalies are rarely expressed as simple textual irregularities; instead, they are often embedded in control logic, timing deviations, parameter inconsistencies, protocol failures, or state-transition conflicts. This is precisely why evaluating industrial log analysis requires attention to both parsing fidelity and downstream detection behavior.

Taken together, these four datasets provide a task-oriented evaluation setting that spans benchmark-style logs and multiple forms of real-world industrial software logs. The benchmark dataset offers a useful reference point, while FALL, PIMS, and SCADA-X expose the kinds of structural diversity, semantic density, and anomaly complexity that make industrial log analysis uniquely challenging. By combining representative industrial samples with the full experimental pipeline, this repository aims to support more realistic replication, more meaningful comparison across methods, and future work on robust log parsing and anomaly detection under real-world constraints.

We hope these resources can support future research on industrial log analysis and provide a practical basis for replication, comparison, and extension.
