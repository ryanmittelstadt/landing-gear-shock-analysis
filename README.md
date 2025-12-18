<h2>Description</h2>
This project presents a parametric and sensitivity analysis of aircraft landing gear and structural vibration dynamics using MATLAB simulations. Landing impact dynamics are modeled to investigate the influence of stiffness and damping on settling time and maximum displacement. Wing vibration amplification due to engine imbalance is also analyzed over varying operating conditions. The work demonstrates design-oriented approaches to aerospace vibration and dynamics problems.
<br />


<h2>Languages and Utilities Used</h2>

- <b>MATLAB</b> 
- <b>Diskpart</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)

<h2>Program walk-through:</h2>

<p align="center">
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

<img src="https://i.imgur.com/LDYVjzP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The governing second-order equation of motion is converted into a first-order system and solved numerically using MATLAB’s ode45 solver. The system is initialized with a vertical landing velocity representative of touchdown conditions. Each simulation produces time histories of displacement, velocity, and force transmitted through the landing gear. <br/>
<img src="https://i.imgur.com/QYUx3bz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
 A comprehensive sensitivity analysis is performed by sweeping spring stiffness and damping ratio values across a broad design space. For each parameter combination, the system response is simulated and evaluated using automated post-processing. Settling time is calculated using a ±5% displacement criterion relative to peak response. The results are visualized as a surface plot, allowing rapid identification of trends and regions of improved performance.
<br />
 <br />
<img src="https://i.imgur.com/wIqZxB7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
 <br />
 While increasing spring stiffness generally reduces settling time, excessively stiff systems result in unrealistic displacement behavior and unacceptably high impact forces. To avoid non-physical designs, maximum displacement constraints are introduced based on typical small-aircraft landing gear behavior. These constraints limit the parameter space to physically reasonable solutions.
<br/>
<br />
<img src="https://i.imgur.com/vGQH8XZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
To further understand system behavior, displacement responses are generated for a range of damping ratios while holding spring stiffness constant. This analysis highlights the trade-off between underdamped oscillations and overdamped slow response, showing that moderate damping provides the fastest practical settling.  <br/>
 <br />
<img src="https://i.imgur.com/XV0QQAV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
