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
This project applies dynamic modeling and numerical simulation to analyze and design aerospace mechanical systems using MATLAB. Two primary problems are addressed: optimizing the shock absorption performance of an aircraft landing gear system during touchdown, and evaluating vibration amplification in an aircraft wing caused by engine imbalance. Both analyses are approached as design problems with no single correct solution, emphasizing sensitivity analysis and engineering trade-offs. <br/>
 <br />
The aircraft landing gear is modeled as an equivalent single-degree-of-freedom mass–spring–damper system. While real landing gear assemblies are mechanically complex, parallel shock absorbers allow the system to be reduced to a single effective stiffness and damping coefficient for vertical dynamics. This simplified model captures the dominant behavior during landing while remaining computationally efficient.  <br/>
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

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
