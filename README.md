# Comparative Analysis of Current-Starved Ring VCOs

### 3-Stage, 5-Stage and 7-Stage VCOs Using GPDK 180nm CMOS Technology

## Overview

This project presents a comparative analysis of **3-stage, 5-stage, and 7-stage Current-Starved Ring VCOs** designed and simulated using **Cadence Virtuoso** with **GPDK 180nm CMOS technology**.

The study focuses on the effect of **number of stages on oscillation frequency and tuning characteristics**.

- **Technology:** GPDK 180nm CMOS
- **Supply Voltage:** 1.8 V
- **Design Tool:** Cadence Virtuoso
- **Simulator:** Spectre

## Objectives

- Design 3-stage, 5-stage, and 7-stage Current-Starved Ring VCOs.
- Analyze the effect of stage count on oscillation frequency.
- Study frequency variation with respect to control voltage.
- Compare the performance of the three architectures.

## Architectures

| Architecture | Stages |
|---|---:|
| 3-Stage VCO | 3 |
| 5-Stage VCO | 5 |
| 7-Stage VCO | 7 |

## Key Results

| Architecture | Maximum Measured Frequency | Vctrl |
|---|---:|---:|
| 3-Stage | 4.3996 GHz | 1.306 V |
| 5-Stage | 2.411 GHz | 1.800 V |
| 7-Stage | 1.646 GHz | 1.306 V |

The results show that increasing the number of stages increases the total propagation delay of the ring oscillator, resulting in a lower oscillation frequency.

## Repository Contents

```text
Current-Starved-VCO-Comparison-180nm/
│
├── 3-Stage/
├── 5-Stage/
├── 7-Stage/
├── Results/
├── Documentation/
└── README.md
