---

# 📘 CONTROL OF ROBOTIC SYSTEMS – DETAILED NOTES (EXAM ORIENTED)

---

## 🔹 Module 1: Basics of Control

### 1️⃣ Differential Equation & Transfer Function (IMP)

* Differential equations describe system behavior in the **time domain**, showing how output depends on input and its derivatives.
* Transfer function represents the system in the **Laplace domain**, making analysis easier.

$$
G(s) = \frac{Y(s)}{U(s)}
$$

**Key Points:**

* Applicable only to **Linear Time-Invariant (LTI)** systems.
* **Poles** determine stability; **zeros** affect transient response.

**Example (RC Circuit):**

$$
\tau \frac{dy(t)}{dt} + y(t) = K u(t)
$$

$$
G(s) = \frac{K}{\tau s + 1}
$$

**Block Diagram:**

```
Input u(t) → System G(s) → Output y(t)
```

---

### 2️⃣ Frequency Response (IMP)
frequency response is a quantitative measure of how a system reacts to input signals across different frequencies. It typically consists of two components: magnitude (how the signal's volume or strength changes) and phase (how the signal's timing is shifted).

* Describes system response to **sinusoidal inputs** of different frequencies.
* Shows **amplitude ratio** and **phase shift**.
* Represented using **Bode, Polar, and Nyquist plots**.

**Uses:**

* Stability analysis
* Resonance detection
* Controller design

**Example:** Low-pass filter attenuates high-frequency signals.

**Block Diagram:**

```
Sine Input → System → Sine Output (Gain & Phase Shift)
```

---

### 3️⃣ Routh–Hurwitz Test & Relative Stability

The Routh–Hurwitz stability criterion is a mathematical test used in control systems to determine the stability of a linear time-invariant (LTI) system without solving for its poles. While primarily used for absolute stability, it can be adapted to analyze relative stability.

* Determines system stability **without solving roots**.
* Construct the **Routh array** from the characteristic equation.

**Stability Condition:**

* All elements in the **first column** of the Routh array must be **positive**.

**Relative Stability:**

* Indicates how far the poles are from the imaginary axis.

**Example:**

$$
s^3 + 5s^2 + 8s + 4 = 0
$$

**Block Diagram:**

```
Characteristic Equation → Routh Array → Stability Decision
```

---

### 4️⃣ Root Locus & Design

the Root Locus is a graphical technique used to analyze how the roots (poles) of a system's characteristic equation move in the complex s-plane as a system parameter, typically the gain $(K)$, varies from zero to infinity

* Graphical technique showing how **closed-loop poles** move as gain $K$ varies.
* Helps analyze stability and transient performance.

**Design Objectives:**

* Reduce overshoot
* Improve settling time
* Increase damping ratio

**Example:** Adding a lead compensator shifts poles to the left.

**Block Diagram:**

```
System → Root Locus → Pole Locations → Time Response
```

---

### 5️⃣ Phase Lead, Lag & Lag–Lead Design

* **Phase Lead Compensator**

  * Improves transient response
  * Increases phase margin

* **Phase Lag Compensator**

  * Improves steady-state accuracy
  * Increases low-frequency gain

* **Lag–Lead Compensator**

  * Combines advantages of both

**Example:** Servo motor speed control.

**Block Diagram:**

```
Reference → Compensator → Plant → Output
```

---

### 6️⃣ Bode, Polar & Nyquist Plots (IMP)

## Bode Plots:
Two separate semi-log plots (Magnitude in dB and Phase in degrees). Best for "loop shaping" and identifying Gain Margin (GM) and Phase Margin (PM) to ensure robustness.
## Polar Plots:
A single plot on a complex plane representing magnitude and phase as a vector. While visually simple, they are the foundation for the more comprehensive Nyquist plot. 
## Nyquist plot:
A Nyquist plot is a graphical tool in control engineering used to determine the absolute and relative stability of a system by plotting the complex transfer function \(G(j\omega )H(j\omega )\) on the complex plane. Unlike a polar plot, it covers the entire frequency range from \(-\infty \) to \(+\infty \). 

* **Bode Plot:** Gain (dB) and phase vs frequency
* **Polar Plot:** Frequency response in complex plane
* **Nyquist Plot:** Stability analysis using encirclement of $-1$

**Stability Margins:**

* Gain Margin (GM)
* Phase Margin (PM)

**Example:** Gain margin = 6 dB indicates stable system.

**Block Diagram:**

```
Input → System → Frequency Response → Stability Check
```

---

## 🔹 Module 2: Linear Control

### 1️⃣ State Variables & State Space Model (IMP)

state-space modeling is the standard mathematical framework for representing complex, multi-axis robotic systems. It captures a system's internal dynamics through a set of first-order differential equations, allowing for more comprehensive control than traditional transfer functions.

* **State variables** fully describe the system at any time. State variables are the minimal set of variables—such as position, velocity, and orientation—required to fully describe a system's status at any given moment.
* Suitable for **MIMO systems**.

$$
\dot{x} = Ax + Bu
$$
$$
y = Cx + Du
$$

**Example (Mass–Spring–Damper):**

* $x_1 =$ position
* $x_2 =$ velocity

**Block Diagram:**

```
Input → State Equations → States x(t) → Output y(t)
```

---

### 2️⃣ Controllability & Observability

* **Controllability:** Ability to drive system from any initial state to any desired state.
* **Observability:** Ability to estimate all states from output.

**Test Condition:**

* Rank of controllability/observability matrix = number of states

**Example:** Single-mass system is completely controllable and observable.

**Block Diagram:**

```
Controller → Plant → Output → Observer → State Estimation
```

---

### 3️⃣ Pole Placement & Observer Design

## Pole Placement (State Feedback Control)
Pole placement is a design technique that allows engineers to move the eigenvalues (poles) of a system to specific locations in the complex plane to achieve desired performance. 

* **State Feedback Control:**

$$
u = -Kx + r
$$

* Used to place closed-loop poles at desired locations.
* **Observer** estimates unmeasured states.

## State Observer Design
In most real-world robotic systems, not all internal states (like motor acceleration or internal temperatures) can be measured directly due to sensor costs or noise. An Observer is a mathematical model that runs in parallel with the physical machine to estimate these hidden states.

**Example:** DC motor control using Luenberger observer.

**Block Diagram:**

```
Reference → Controller → Plant → Output → Observer → Feedback
```

---

### 4️⃣ P, PI & PID Controllers

Proportional (P), Proportional-Integral (PI), and Proportional-Integral-Derivative (PID) controllers remain the backbone of industrial automation, governing approximately 95% of closed-loop operations. These controllers utilize feedback to minimize the error between a desired setpoint and a measured process variable. 

* **P Controller:** Fast response, steady-state error remains
* **PI Controller:** Eliminates steady-state error
* **PID Controller:** Best overall performance

**PID Equation:**

$$
u(t) = K_p e(t) + K_i \int e(t)dt + K_d \frac{de(t)}{dt}
$$

**Example:** Temperature control system.

**Block Diagram:**

```
Error → PID → Actuator → Process → Output
```

---

### 5️⃣ Control Law Partitioning & Single-Joint Modelling

Control Law Partitioning remains a cornerstone of model-based robotic control, used to simplify complex, non-linear dynamics into a form manageable by linear control techniques. This method is particularly effective for Single-Joint Modelling, where individual joint dynamics are isolated for high-precision control.

* Control input divided into **feedforward** and **feedback** parts.
* Common in robotic joints.

**Example:** Torque control of robotic arm joint.

## Control Law Partitioning (Computed Torque Control)
Control Law Partitioning is a strategy that divides the control effort into two distinct parts: a Model-Based Portion and a Servo (Feedback) Portion. 
The Model-Based Portion: This part uses the mathematical model of the robot (its mass, inertia, and gravity effects) to cancel out non-linearities in the system. It essentially "linearizes" the robot's behavior so that it acts like a simple unit mass.
* The Servo Portion
* Core Benefit
  
## Single-Joint Modelling
single-joint modelling is the standard first step for designing these partitioned control laws. It treats each joint as an independent system to account for its specific physical properties. 

**Block Diagram:**

```
Reference → Feedforward + Feedback → Joint → Position Output
```

---

## 🔹 Module 3: Non-Linear Control Systems

### 1️⃣ Common Physical Non-Linear Systems (IMP)

physical non-linearities are classified as either incidental (inherent in the hardware) or intentional (deliberately added to the system). These non-linearities often degrade the performance of linear controllers, making control law partitioning and model-based compensation essential for high-precision motion.

* Pendulum
* Saturation
* Friction
* Van der Pol oscillator

**Characteristics:**

* Multiple equilibrium points
* Limit cycles
* Non-superposition

---

### 2️⃣ Phase Plane Method & Analysis

the Phase Plane Method remains a critical graphical tool for analyzing the stability and behavior of second-order nonlinear systems. It provides a visual representation of how system states—typically position (\(x\)) and velocity (\(\.{x}\))—evolve over time.

* Plots state variables against each other ($x_1$ vs $x_2$).
* Shows trajectories and stability behavior.

**Example:** Simple pendulum motion.

**Block Diagram:**

```
States → Phase Plane → Trajectory Analysis
```

---

### 3️⃣ Stability Analysis
stability remains the single most critical characteristic of any control system, defined as the system's ability to produce a Bounded Output for any Bounded Input (BIBO stability). While classical linear methods provide the foundation, modern applications—especially in robotics and autonomous systems—increasingly rely on advanced nonlinear and stochastic analysis.

#### Lyapunov’s Stability Criterion
Lyapunov’s Stability Criterion remains the most powerful mathematical tool for determining the stability of nonlinear robotic and autonomous systems. Unlike the Phase Plane method, which is limited to second-order systems, Lyapunov's methods can analyze systems of any dimension by evaluating a "scalar energy function."

* Choose a positive definite function $V(x)$.
* If $\dot{V}(x) < 0$, system is stable.

**Example:**

$$
V = x^2 + y^2
$$

#### Describing Function Method

* Approximate frequency-domain analysis for nonlinear systems.

**Block Diagram:**

```
Nonlinear System → Lyapunov Function → Stability Result
```

---

### 4️⃣ Control Problems for Manipulators
control problems for robotic manipulators focus on managing complex physical dynamics and ensuring safe, autonomous interaction in unstructured environments.

**Issues:**

* Nonlinearity
* Coupling
* Parameter uncertainty

**Solutions:**

* Feedback linearization
* Computed torque control

**Example:** 2-DOF robotic arm control.

---

## 🔹 Module 4: Motion Control

### 1️⃣ Point-to-Point (PTP) Control

Point-to-Point (PTP) control, also known as a positioning system, is a fundamental motion control method where the primary objective is to move a tool or workpiece from one specific location to another. In 2026, it remains a standard approach in both CNC (Computer Numerical Control) machining and industrial robotics.

* Motion between two fixed points.
* Path is not important.

**Trajectories:**

* Trapezoidal
* Cubic
* S-curve

**Example:** Pick-and-place robot.

**Block Diagram:**

```
Start → Trajectory Planner → Controller → Actuator → End
```

---

### 2️⃣ Trajectory Generation & Continuous Path Control

Trajectory generation is the mathematical process of creating a time-parameterized motion profile that specifies a system's position, velocity, and acceleration at every instant. In Continuous Path (CP) Control, the system maintains strict control over the tool or end-effector's precise trajectory relative to the workpiece throughout the entire movement

* Generates smooth position, velocity, acceleration profiles.
* Continuous path control tracks the **entire path**.

**Example:** CNC machine tool path.

**Block Diagram:**

```
Reference Path → Trajectory Generator → Controller → Actuator
```

---

### 3️⃣ Joint-Based & Cartesian Control

In robotic motion control, systems operate in two primary coordinate spaces: Joint-Based (Configuration Space) and Cartesian (Task Space). Choosing between them depends on whether the priority is the efficiency of the robot's internal mechanisms or the precise path of its end-effector. 

* **Joint Control:** Individual joint control
* **Cartesian Control:** End-effector control using inverse kinematics

## 1. Joint-Based Control (Joint Space)
Joint-based control specifies a robot's configuration through the direct position of its individual actuators (e.g., J1 = 45°, J2 = 90°)

## 2. Cartesian Control (Task Space)
Cartesian control defines motion in terms of the tool's position and orientation in a 3D world (X, Y, Z coordinates and Roll, Pitch, Yaw).

**Example:** Welding robot uses Cartesian control.

**Block Diagram:**

```
Task Space → Inverse Kinematics → Joint Commands → Robot
```

---

### 4️⃣ Force Control & Hybrid Position/Force Control

the demand for robots to perform delicate tasks—such as robotic polishing, assembly, and human-robot collaboration—has shifted focus toward advanced force regulation. While traditional position control manages where a robot goes, Force Control manages how hard it interacts with its environment. 

* **Force Control:** Regulates interaction force. Pure force control focuses on maintaining a specific contact force rather than a trajectory.

* **Hybrid Control:** The most robust strategy for complex industrial tasks is Hybrid Control, which decouples the task space into two independent subspaces: Position Subspace and force Subspace

**Example:** Robotic assembly and insertion task.

**Block Diagram:**

```
Desired Position & Force → Controller → Robot → Sensor Feedback
```

---
