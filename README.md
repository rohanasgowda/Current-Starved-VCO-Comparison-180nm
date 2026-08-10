Yes — **full detailed README, but organized with collapsible dropdown sections** so the GitHub page stays clean.

Copy **everything inside this code block** directly into your `README.md` editor:

````markdown
# Comparative Analysis of Current-Starved Ring VCOs

### 3-Stage, 5-Stage and 7-Stage VCOs Using GPDK 180nm CMOS Technology

---

## Overview

This project presents a comparative analysis of **3-stage, 5-stage, and 7-stage Current-Starved Ring Voltage Controlled Oscillators (VCOs)** designed and simulated using **Cadence Virtuoso** with **GPDK 180nm CMOS technology**.

The primary objective is to investigate how the **number of inverter stages affects oscillation frequency and tuning characteristics** of a Current-Starved Ring VCO.

### Project Specifications

| Parameter | Specification |
|---|---|
| Technology | GPDK 180nm CMOS |
| Supply Voltage | 1.8 V |
| VCO Type | Current-Starved Ring VCO |
| Architectures | 3-stage, 5-stage, 7-stage |
| Design Tool | Cadence Virtuoso |
| Simulator | Spectre |

---

## Objectives

- Design 3-stage, 5-stage, and 7-stage Current-Starved Ring VCOs.
- Simulate the architectures using GPDK 180nm CMOS technology.
- Study the effect of stage count on oscillation frequency.
- Analyze frequency variation with respect to control voltage.
- Perform DC and transient analyses.
- Compare the frequency characteristics of the three architectures.

---

<details>
<summary><strong>1. Current-Starved Ring VCO</strong></summary>

### Principle of Operation

A Current-Starved Ring VCO is based on a ring oscillator in which additional MOS transistors are used to control the current available to each inverter stage.

The control voltage (`Vctrl`) controls the current flowing through the current-starving transistors. This changes the charging and discharging rate of the inverter stages and consequently changes the propagation delay and oscillation frequency.

The basic relationship for a ring oscillator is:

```text
fosc ≈ 1 / (2 × N × td)
````

where:

* `fosc` = oscillation frequency
* `N` = number of inverter stages
* `td` = propagation delay of each stage

Increasing the number of stages increases the total propagation delay and generally reduces the oscillation frequency.

</details>

---

<details>
<summary><strong>2. VCO Architectures</strong></summary>

### 3-Stage VCO

The 3-stage VCO contains three inverter stages connected in a feedback loop.

It has the smallest number of stages among the three architectures and therefore exhibits the smallest total propagation delay and the highest measured oscillation frequency.

### 5-Stage VCO

The 5-stage VCO contains five inverter stages.

It provides an intermediate propagation delay and frequency range between the 3-stage and 7-stage architectures.

### 7-Stage VCO

The 7-stage VCO contains seven inverter stages.

The increased number of stages results in a larger total propagation delay and consequently a lower oscillation frequency compared with the 3-stage and 5-stage designs.

### Architecture Comparison

| Architecture | Number of Stages |
| ------------ | ---------------: |
| 3-Stage VCO  |                3 |
| 5-Stage VCO  |                5 |
| 7-Stage VCO  |                7 |

</details>

---

<details>
<summary><strong>3. Simulation Methodology</strong></summary>

All three architectures were designed and simulated using **Cadence Virtuoso** with **GPDK 180nm CMOS technology**.

The supply voltage was maintained at:

```text
VDD = 1.8 V
```

### DC Analysis

The control voltage was swept while keeping the supply voltage fixed at 1.8 V.

The current through the VDD supply source was observed as a function of `Vctrl`.

### Transient Analysis

Transient analysis was performed to:

* Observe the output waveform.
* Verify sustained oscillation.
* Determine the oscillation period.
* Calculate the oscillation frequency.

### Parametric Analysis

A control-voltage sweep was performed to investigate the variation of oscillation frequency with `Vctrl`.

The same control-voltage points were used for comparison between the three architectures.

</details>

---

<details>
<summary><strong>4. Frequency Comparison</strong></summary>

The measured oscillation frequencies are summarized below.

|   Vctrl |                  3-Stage |   5-Stage |   7-Stage |
| ------: | -----------------------: | --------: | --------: |
| 0.500 V | No sustained oscillation | 80.87 MHz |  57.9 MHz |
| 0.688 V |                2.144 GHz | 1.003 GHz | 624.9 MHz |
| 0.947 V |                3.996 GHz | 2.073 GHz | 1.456 GHz |
| 1.306 V |               4.3996 GHz | 2.406 GHz | 1.646 GHz |
| 1.800 V |                4.334 GHz | 2.411 GHz | 1.534 GHz |

> **Note:** The 3-stage VCO does not exhibit sustained oscillation at 0.5 V under the simulated conditions.

### Maximum Measured Frequency

| Architecture | Maximum Frequency |   Vctrl |
| ------------ | ----------------: | ------: |
| 3-Stage      |        4.3996 GHz | 1.306 V |
| 5-Stage      |         2.411 GHz | 1.800 V |
| 7-Stage      |         1.646 GHz | 1.306 V |

</details>

---

<details>
<summary><strong>5. 3-Stage VCO Results</strong></summary>

| Vctrl (V) | gm₁ (mS) | gm₂ (mS) | Δgm (mS) |                Frequency |
| --------: | -------: | -------: | -------: | -----------------------: |
|     0.500 |        — |        — |        — | No sustained oscillation |
|     0.688 |   3.2886 |   3.7506 |   0.4620 |                2.144 GHz |
|     0.947 |   3.5426 |  3.79319 |  0.25059 |                3.996 GHz |
|     1.306 |  3.64226 |  3.86956 |  0.22730 |               4.3996 GHz |
|     1.800 |  3.51944 |   3.7501 |  0.23070 |                4.334 GHz |

### Observation

The 3-stage VCO achieves the highest measured frequency among the three architectures.

At 0.5 V control voltage, sustained oscillation was not observed under the simulated conditions.

</details>

---

<details>
<summary><strong>6. 5-Stage VCO Results</strong></summary>

| Vctrl (V) | Frequency |
| --------: | --------: |
|     0.500 | 80.87 MHz |
|     0.688 | 1.003 GHz |
|     0.947 | 2.073 GHz |
|     1.306 | 2.406 GHz |
|     1.800 | 2.411 GHz |

### Observation

The 5-stage VCO provides an intermediate frequency range compared with the 3-stage and 7-stage architectures.

The maximum measured frequency is **2.411 GHz at Vctrl = 1.8 V**.

</details>

---

<details>
<summary><strong>7. 7-Stage VCO Results</strong></summary>

| Vctrl (V) | gm₁ (mS) | gm₂ (mS) | Δgm (mS) | Frequency |
| --------: | -------: | -------: | -------: | --------: |
|     0.500 |  12.7156 |  29.9742 |  17.2586 |  57.9 MHz |
|     0.688 |   9.3935 |  10.9937 |   1.6002 | 624.9 MHz |
|     0.947 |  14.3353 |  15.0243 |   0.6890 | 1.456 GHz |
|     1.306 |  13.9764 |  14.5830 |   0.6066 | 1.646 GHz |
|     1.800 |  14.0855 |  14.7371 |   0.6516 | 1.534 GHz |

### Observation

The 7-stage VCO exhibits the lowest maximum measured frequency among the three architectures.

The maximum measured frequency is **1.646 GHz at Vctrl = 1.306 V**.

</details>

---

<details>
<summary><strong>8. Comparative Analysis</strong></summary>

### Effect of Stage Count

The simulation results demonstrate a clear relationship between the number of stages and oscillation frequency.

| Architecture | Maximum Measured Frequency |
| ------------ | -------------------------: |
| 3-Stage      |                 4.3996 GHz |
| 5-Stage      |                  2.411 GHz |
| 7-Stage      |                  1.646 GHz |

The 3-stage VCO provides the highest measured frequency, while the 7-stage VCO provides the lowest.

This is primarily due to the increase in total propagation delay as the number of stages increases.

### Frequency Trend

```text
Number of Stages ↑
        ↓
Total Propagation Delay ↑
        ↓
Oscillation Frequency ↓
```

### Control Voltage

The oscillation frequency generally increases with increasing `Vctrl`.

This occurs because increasing `Vctrl` increases the available current through the current-starving transistors, reducing the charging and discharging delay of the inverter stages.

At higher control voltages, the frequency increase becomes less pronounced and may show a slight reduction depending on the device operating characteristics.

</details>

---

<details>
<summary><strong>9. Key Results</strong></summary>

### Highest Frequency

The **3-stage VCO** achieves the highest measured frequency:

**4.3996 GHz at Vctrl = 1.306 V**

### Intermediate Architecture

The **5-stage VCO** achieves:

**2.411 GHz at Vctrl = 1.8 V**

### Lowest Maximum Frequency

The **7-stage VCO** achieves:

**1.646 GHz at Vctrl = 1.306 V**

### Important Observation

The results demonstrate that increasing the number of stages generally decreases the achievable oscillation frequency because of the increased propagation delay through the ring.

</details>

---

<details>
<summary><strong>10. Project Structure</strong></summary>

```text
Current-Starved-VCO-Comparison-180nm/
│
├── README.md
│
├── 3-Stage/
│   ├── Schematic/
│   ├── DC-Analysis/
│   ├── Transient-Analysis/
│   ├── Parametric-Analysis/
│   └── Results/
│
├── 5-Stage/
│   ├── Schematic/
│   ├── DC-Analysis/
│   ├── Transient-Analysis/
│   ├── Parametric-Analysis/
│   └── Results/
│
├── 7-Stage/
│   ├── Schematic/
│   ├── DC-Analysis/
│   ├── Transient-Analysis/
│   ├── Parametric-Analysis/
│   └── Results/
│
├── Results/
│   └── Current_Starved_VCO_3_5_7_Stage_Comparison.xlsx
│
└── Documentation/
    ├── Report.pdf
    └── Presentation.pdf
```

</details>

---

<details>
<summary><strong>11. Tools Used</strong></summary>

* Cadence Virtuoso
* Spectre Simulator
* GPDK 180nm CMOS Technology
* Microsoft Excel

</details>

---

<details>
<summary><strong>12. Future Work</strong></summary>

* Layout implementation
* Design Rule Check (DRC)
* Layout Versus Schematic (LVS)
* Parasitic extraction
* Post-layout simulation
* Technology-node comparison
* Phase-noise analysis
* Jitter analysis
* Further optimization of the current-starving circuit

</details>

---

## Authors

**Rohan A S Gowda**
Electronics and Communication Engineering
JSS Science and Technology University, Mysuru

**Dasari Navaneeth**
Electronics and Communication Engineering
JSS Science and Technology University, Mysuru

---

## Acknowledgement

This project was carried out as an academic VLSI design study using the Cadence Virtuoso design environment and GPDK 180nm CMOS technology.

```
```
