# RT050-DC-Motor-System-Identification
MATLAB-based DC motor speed calibration, dynamic system identification and model validation using the Feedback Instruments RT050 Motor Control model.

## Overview

This project was developed as part of a Control Systems laboratory assignment using the Feedback Instruments RT050 Motor Control Trainer.

The objective was to experimentally characterize the DC motor, identify its dynamic behaviour, and validate a mathematical model through MATLAB-based data acquisition and analysis.

The complete experimental procedure was automated using MATLAB scripts, reducing manual intervention while improving repeatability and measurement accuracy.

---

## Objectives

- Determine the supply voltage required to achieve predefined operating speeds.
- Automatically calibrate the motor at 600 rpm and 1200 rpm.
- Acquire experimental motor data.
- Perform dynamic system identification.
- Validate the identified mathematical model against experimental measurements.
- Analyse the system response using MATLAB.

---

## Hardware

- Feedback Instruments RT050 Motor Control Trainer
- DC Motor
- Optical Speed Sensor
- MATLAB
- RT050 MATLAB API

---

## Experimental Procedure

### 1. Automatic Speed Calibration

The algorithm searches for the voltage required to reach two operating points:

- 600 rpm
- 1200 rpm

Instead of using a fixed voltage increment, the algorithm dynamically adjusts the voltage step according to the speed error.

Large errors:

- larger voltage increments

Small errors:

- finer voltage increments

For every voltage level:

1. Apply voltage
2. Wait for stabilization
3. Acquire multiple speed samples
4. Compute average speed
5. Update voltage
6. Repeat until the desired tolerance is achieved

Tolerance:

±5 rpm

---

### 2. Dynamic Identification

After calibration, the motor is stabilized around **900 rpm**.

A sinusoidal excitation signal is then applied to the motor voltage.

The corresponding speed response is measured continuously.

These experimental datasets are later used for system identification.

---

### 3. Mathematical Model

The motor dynamics were approximated by a third-order transfer function representing:

- electrical dynamics
- mechanical dynamics

The identified model was implemented in MATLAB and compared against the experimental measurements.

---

### 4. Model Validation

Two validation tests were performed.

### Sinusoidal Response

The identified model reproduces the experimental response with good accuracy under sinusoidal excitation.

### Step Response

A voltage step was applied to both the real system and the identified model.

The comparison confirms that the identified model captures the dominant dynamics of the motor.

---

## MATLAB Features

The MATLAB implementation includes:

- Automatic motor calibration
- Adaptive voltage adjustment
- Speed averaging
- Data acquisition
- Dynamic testing
- Automatic plotting
- Model validation

---

## Results

The experimental results demonstrate:

- Stable operating point detection
- Accurate speed regulation
- Successful system identification
- Good agreement between experimental and simulated responses

---

## Skills Demonstrated

- MATLAB Programming
- Control Systems
- DC Motor Characterization
- Experimental Data Acquisition
- System Identification
- Signal Processing
- Dynamic Modelling
- Automation of Laboratory Procedures
- Engineering Data Analysis

---

## Repository Structure

```

RT050-System-Identification/
│
├── README.md
├── LICENSE
├── .gitignore
│
├── matlab/
│ └── LAST19HR.m
│
├── docs/
│ └── Presentation.pdf
│
├── results/
│ └── RESULTADOS_FINAIS.txt
│
├── images/
│ ├── calibration.png
│ ├── sinusoidal_response.png
│ ├── validation.png
│ └── ...
│
└── figures/
```

---

## Future Improvements

Possible future developments include:

- Closed-loop PID control
- Automatic parameter estimation
- Frequency response analysis
- Real-time graphical interface
- Simulink implementation
- Robust controller design
