# 📘 CONTROL OF ROBOTIC SYSTEMS – DETAILED NOTES (EXAM ORIENTED)

---

## 🔹 **Module 1: Basics of Control**

1️⃣ **Differential Equation & Transfer Function (IMP)**

* Differential equations describe system behavior in time domain. They show how output depends on input and its derivatives.
* Transfer function represents system in Laplace domain, simplifying analysis. It relates **input** (U(s)) to **output** (Y(s)):
  [
  G(s) = \frac{Y(s)}{U(s)}
  ]

**Key Points:**

* Useful for linear time-invariant (LTI) systems.
* Simplifies computation of stability and response.
* Poles and zeros of (G(s)) determine stability and behavior.

**Example:** RC Circuit:
[
\tau \frac{dy(t)}{dt} + y(t) = K u(t), \quad G(s) = \frac{K}{\tau s + 1}
]

**Box Diagram:**
Input (u(t)) → System (G(s)) → Output (y(t))

---

2️⃣ **Frequency Response (IMP)**

* Describes system response to sinusoidal inputs of varying frequency.
* Key for analyzing resonance, bandwidth, and stability.

**Plots Used:**

* **Bode Plot:** Gain (dB) & Phase vs Frequency
* **Nyquist Plot:** Encirclements of -1 → Stability
* **Polar Plot:** Complex plane representation of frequency response

**Example:** Low-pass filter attenuates high-frequency input.

**Box Diagram:**
Input Sine → System → Output Sine (Amplitude & Phase Shift)

---

3️⃣ **Routh-Hurwitz Test & Relative Stability**

* Determines stability without solving characteristic equation.
* **Criterion:** All first-column elements of Routh array > 0 → stable.
* **Relative Stability:** Measures how far poles are from imaginary axis (faster decay = more stable).

**Example:** Characteristic equation (s^3 + 5s^2 + 8s + 4 = 0) → Routh array used to check stability.

**Box Diagram:**
Characteristic Equation → Routh Array → Stability Decision

---

4️⃣ **Root Locus & Design**

* Shows movement of closed-loop poles as system gain varies.
* **Construction Rules:** Start at open-loop poles, move towards zeros; asymptotes guide at infinity.
* **Design Goal:** Place poles for desired damping, overshoot, and settling time.

**Example:** Adding lead compensator shifts poles left → improves transient response.

**Box Diagram:**
System → Root Locus → Pole Locations → Response

---

5️⃣ **Phase Lead, Lag & Lag-Lead Design**

* **Phase Lead:** Improves transient response; reduces overshoot & rise time.
* **Phase Lag:** Improves steady-state accuracy; increases low-frequency gain.
* **Lag-Lead:** Combines advantages for both transient and steady-state improvement.

**Example:** Lead-lag compensator in servo motor improves both speed and accuracy.

**Box Diagram:**
Reference → Compensator → System → Output

---

6️⃣ **Bode, Polar & Nyquist Plots (IMP)**

* **Bode Plot:** Helps determine gain margin and phase margin.
* **Polar Plot:** Visual representation of magnitude & phase at all frequencies.
* **Nyquist Plot:** Ensures stability using encirclement of -1 in s-plane.

**Example:** Bode plot used to design gain margin = 6 dB.

**Box Diagram:**
Input → System → Frequency Response → Stability Analysis

---

## 🔹 **Module 2: Linear Control**

1️⃣ **State Variables & State Space Model (IMP)**

* State: Set of variables describing system at a given instant.
* State-space equations:
  [
  \dot{x} = Ax + Bu, \quad y = Cx + Du
  ]
* **Forms:** Controllable, Observable, Diagonal, Jordan.

**Example:** Mass-Spring-Damper:
[
x_1 = position, \quad x_2 = velocity
]

**Box Diagram:**
Input (u(t)) → System → State Variables (x(t)) → Output (y(t))

---

2️⃣ **Controllability & Observability**

* **Controllability:** Ability to drive states from any initial to any final condition.
* **Observability:** Ability to reconstruct all states from output.
* **Tests:** Rank of controllability/observability matrices = number of states.

**Example:** Single-mass system is fully controllable and observable.

**Box Diagram:**
Controller → System → Output → Observer → State Estimation

---

3️⃣ **Pole Placement & Observer Design**

* **Pole Placement:** Use (u = -Kx + r) to place poles at desired locations for response shaping.
* **Observer Design:** Estimates unmeasured states using system output.

**Example:** DC motor speed control using Luenberger observer.

**Box Diagram:**
Reference → Controller → Plant → Output → Observer → State Feedback

---

4️⃣ **P, PI & PID Controllers**

* **P:** Reduces rise time, may leave steady-state error.
* **PI:** Eliminates steady-state error, may increase overshoot.
* **PID:** Reduces rise time, overshoot, and steady-state error.

**Example:** Temperature control in HVAC systems.

**Box Diagram:**
Error → PID Controller → Actuator → Process → Output

---

5️⃣ **Control Law Partitioning & Single Joint Modelling**

* **Partitioning:** Splits control input into feedforward & feedback.
* **Example:** Robotic arm joint: torque = feedforward torque + PID feedback.

**Box Diagram:**
Reference → Feedforward + Feedback → Joint → Position Output

---

## 🔹 **Module 3: Non-Linear Control System**

1️⃣ **Common Physical Non-linear Systems (IMP)**

* Pendulum, Van der Pol oscillator, saturation systems, friction systems.
* **Behavior:** Nonlinear response, limit cycles, multiple equilibrium points.

---

2️⃣ **Phase Plane Method & System Analysis**

* Plots states against each other (x_1 vs x_2).
* Determines trajectories, limit cycles, and stability qualitatively.

**Example:** Simple pendulum trajectories in phase plane.

**Box Diagram:**
System States → Phase Plane Plot → Trajectory Analysis

---

3️⃣ **Stability Analysis**

* **Lyapunov’s Method:** Define positive definite function (V(x)) → (\dot{V}(x) < 0) → stable.
* **Describing Function:** Approximate method for systems with nonlinearity.

**Example:** Lyapunov function (V = x^2 + y^2) ensures pendulum returns to equilibrium.

**Box Diagram:**
Nonlinear System → Lyapunov Function → Stability Assessment

---

4️⃣ **Control Problems for Manipulators**

* Challenges: Nonlinearity, Coupling, Parameter Uncertainty.
* Solutions: Feedback linearization, computed torque method.

**Example:** 2-DOF robotic arm torque control.

---

## 🔹 **Module 4: Motion Control**

1️⃣ **Point-to-Point (PTP) Control**

* Moves manipulator from start to goal position using trajectory planning.
* Trajectory types: Trapezoidal, Cubic polynomial, S-curve.

**Example:** Pick-and-place robot.

**Box Diagram:**
Start → Trajectory Planner → Controller → Actuator → End Position

---

2️⃣ **Trajectory Generation & Continuous Path Control**

* **Trajectory Generation:** Creates smooth position, velocity, acceleration profiles.
* **Continuous Path Control:** Follows desired path, not just discrete points.

**Example:** CNC milling machine path control.

**Box Diagram:**
Reference Path → Trajectory Generator → Controller → Actuator → Path Tracking

---

3️⃣ **Joint-Based & Cartesian Control**

* **Joint-Based Control:** Control each joint independently using joint coordinates.
* **Cartesian Control:** Control end-effector in task space using inverse kinematics.

**Example:** Welding robot uses Cartesian control to maintain straight line.

**Box Diagram:**
Desired Task → Inverse Kinematics → Joint Commands → Robot

---

4️⃣ **Force Control & Hybrid Position/Force Control**

* **Force Control:** Regulate contact force with environment.
* **Hybrid Control:** Position control in some directions + force control in others.

**Example:** Robotic assembly requiring precise insertion force.

**Box Diagram:**
Desired Position + Force → Controller → Actuator → Robot → Sensor Feedback
