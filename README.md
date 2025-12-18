<h2>Description</h2>
This project presents a parametric and sensitivity analysis of aircraft landing gear and structural vibration dynamics using MATLAB simulations. Landing impact dynamics are modeled to investigate the influence of stiffness and damping on settling time and maximum displacement. Wing vibration amplification due to engine imbalance is also analyzed over varying operating conditions. The work demonstrates design-oriented approaches to aerospace vibration and dynamics problems.
<br />


<h2>Languages and Utilities Used</h2>

- <b>MATLAB</b> 
- <b>Diskpart</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)

<h2>Program walk-through:</h2>

<p align="left">
I wanted to explore how engineers balance competing priorities—such as minimizing weight while maximizing structural stiffness—to solve real-world aerospace problems. The following analysis addresses two distinct dynamic systems critical to aircraft performance and safety:

* Problem 1: Landing Gear Design Optimization: The objective is to design a shock absorber for a home-built aircraft to minimize the settling time—the time it takes for oscillations to cease after the initial impact of landing. This is critical for preventing structural damage and ensuring pilot safety.
  
* Problem 2: Wing Vibration & Resonance Control: This problem focuses on a jet liner wing subject to mass imbalance from a turbofan engine. The goal is to determine the necessary wing stiffness to keep vibration amplification within strict safety limits ($A \le 0.05$) during various flight phases.

 <h3>Problem 1. Aircraft Landing Gear Design Optimization:</h3>

For a 1,200 kg aircraft landing at a vertical speed of $0.56\text{ m/s}$, the gear must dissipate energy as quickly as possible without exceeding structural force limits. <br/>
<p><strong>Mathematical Modeling</strong></p>
The system is modeled as a single degree-of-freedom (SDOF) mass-spring-damper system. The second-order equation of motion is derived from Newton's Second Law:

<div align="center">

$$\large m\ddot{x} + c\dot{x} + kx = 0$$

</div>
To perform numerical simulations, I converted the system into a first-order state-space representation for MATLAB’s ode45 solver:

* **State Variables:** $y_1 = x$ (Displacement) and $y_2 = \dot{x}$ (Velocity).
* **Derivatives:** $\dot{y}_1 = y_2$ and $\dot{y}_2 = -\frac{c}{m}y_2 - \frac{k}{m}y_1$.

<br />
</div>
<div align="center">
<img src="https://i.imgur.com/LDYVjzP.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
  </div>
<br />
<p><strong>Sensitivity Analysis & Parameter Sweeping</strong></p>

A comprehensive iterative sweep was performed using nested loops in MATLAB to identify the optimal spring stiffness ($k$) and damping ratio ($\zeta$).
<br />

* **Sweep Ranges:** $k \in [1000, 10000]\text{ N/m}$ and $\zeta \in [0.1, 1.0]$.
* **Settling Time Criteria:** Defined as the time required for the displacement to stay within a $\pm5\%$ tolerance band of the peak displacement.
<p align="center">
<img src="https://i.imgur.com/QYUx3bz.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
  </p>
<p><strong>Design Constraints and Selection</strong></p>
 While higher stiffness naturally reduces settling time (approaching a solid block at infinity), it drastically increases maximum force. A force analysis was conducted to ensure structural integrity.
<br />
 <br />
<p align="center">
<img src="https://i.imgur.com/wIqZxB7.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<br />
Research into small aircraft gear suggested a minimum displacement of 0.09 m to avoid a "crash-like" landing. Balancing these factors, the optimal design parameters were selected:

* **Optimal Stiffness ($k$):** $10,000\text{ N/m}$
* **Optimal Damping Ratio ($\zeta$):** $0.7061$
* **Final Settling Time:** $1.34\text{ seconds}$
<p align="center">
<img src="https://i.imgur.com/vGQH8XZ.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
   <br />
<img src="https://i.imgur.com/XV0QQAV.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Moj2C3n.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
  <h3>Problem 2. Jet Liner Wing Vibration Analysis:</h3>
This section analyzes the structural requirements for a passenger jet wing (empty mass 3,700 kg) subjected to a turbofan engine imbalance of 2.5 grams at a 75 cm.
<p><strong>Part A: Stiffness Requirement for Takeoff</strong></p>

The goal was to determine the wing's equivalent stiffness ($K_{eq}$) such that the amplification ratio ($A = X/\delta_{st}$) remains below $0.05$ as engine speed ramps from $0$ to $3,100\text{ RPM}$. With a full fuel load of $8,500\text{ kg}$, the total mass ($m$) is $12,200\text{ kg}$.
<br />
The amplification ratio was calculated using the formula:
$$A = \frac{m\omega^2 a}{\sqrt{(k - m\omega^2)^2 + (\omega c)^2}}$$

Through a MATLAB parameter sweep, it was found that the amplification ratio increases with $\omega$. The minimum compliant stiffness was determined to be $2.0606 \times 10^{10}\text{ N/m}$.
<p align="center">
<img src="https://i.imgur.com/RTBdreW.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/IXXG9W2.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
  </p>
<p><strong>Parts B & C: Landing Scenario and Worst-Case Analysis</strong></p>
The system was re-evaluated for a landing scenario where 90% of the fuel was consumed and the engine was at 2,200 RPM. 
<br />

Using the stiffness found in Part A, amplification ratios were calculated for damping ratios from 0 to 1:

* **Worst-case Amplification Ratio:** 0.00054977
* **Occurring at Damping Ratio ($\zeta$):** 0
<p align="center">
<img src="https://i.imgur.com/gDZ5yYV.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
</p>
