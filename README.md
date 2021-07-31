# Boid Flock Simulator
Visual implementation of Craig Reynolds' "Flocks, Herds, and Schools: A Distributed Behavioral Model" <br>
Link to the original work: https://www.cs.toronto.edu/~dt/siggraph97-course/cwr87/

<h2>Index</h2>
<ul>
  <li><a href="#Overview">Overview</a></li>
  <li><a href="#Controls">Controls</a></li>
  <li><a href="#Rule 1">Rule 1: Collision Avoidance</a></li>
  <ul>
    <li><a href="#R1 Implementation">Implementation</a></li>
    <li><a href="#R1 Behavior">Behavior</a></li>
    <li><a href="#R1 Limitations">Limitations</a></li>
  </ul>
  <li><a href="#Rule 2">Rule 2: Direction Alignment</a></li>
  <ul>
    <li><a href="#R2 Implementation">Implementation</a></li>
    <li><a href="#R2 Behavior">Behavior</a></li>
    <li><a href="#R2 Limitations">Limitations</a></li>
  </ul>
  <li><a href="#Rule 3">Rule 3: Flock Centering</a></li>
  <ul>
    <li><a href="#R3 Implementation">Implementation</a></li>
    <li><a href="#R3 Behavior">Behavior</a></li>
    <li><a href="#R3 Limitations">Limitations</a></li>
  </ul>
  <li><a href="#Conclusion">Conclusioin</a></li>
</ul>

<h2 id="Overview">Overview</h2>

<p>
This program offers a real-time simulation of an algorithm modeled after Craig Reynolds' "Flocks, Herds, and Schools: A Distributed Behavioral Model". His paper explains that with three simple rules, we can make individual agents (referred to as 'boids') act as part of a logically coherent flock. The rules can best be summarized as follows:<br>
<ol>
  <li>Attempt to avoid other agents</li>
  <li>Steer to the average direction of nearby boids</li>
  <li>Head to the center of 'mass'</li>
</ol>
To make the implementation of said rules possible, each boid was given variables determining the degrees and length of sight. This way their awareness is not universal and therefore uniform. Furthermore, the strength of each rule can be tweaked to achieve different group behaviors more appropriate for different scenarios. While this algorithm isn't plug-and-play, the approach to the rule's implementation can easily be mimicked in a myriad of applications. If the program is correctly executed it should look as follows:<br><br>
[Insert Image]
</p>

<h2 id="Controls">Controls</h2>

<p>
The program has two sections. The simulation is to the left and the control panel to the right. The control panel has checkboxes and sliders that control different aspects of the simulation. Below is a breakdown of what each of those settings controls:<br>
<ul>
  <li><b>Avoid collision checkbox</b>: Determines if boids should follow the first rule. If this setting is off the collision avoidance speed slider will not do anything.</li>
  <li><b>Align directions checkbox</b>: Determines if boids should follow the second rule. If this setting is off the direction alignment speed slider will not do anything.</li>
  <li><b>Center flocks checkbox</b>: Determines if boids should follow the third rule. If this setting is off the flock centering speed slider will not do anything.</li>
  <li><b>Highlight main checkbox</b>: Determines if the first generated boid should be red with a visible cone of sight. This setting affects all other visual settings as they require the main boid's cone of sight to work.</li>
  <li><b>Display directions checkbox</b>: Determines if the direction of all boids within the main boid's cone of sight should be displayed as a straight line.</li>
  <li><b>Display proximity checkbox</b>: Determines if the distance to all boids within the main boid's cone of sight should be displayed as straight lines that diminish in visibility the further away the targets are.</li>
  <li><b>Sight degrees slider</b>: Degrees of sight all boids have. The max is 360 and the minimum 1.</li>
  <li><b>Sight diameter slider</b>: Distance of sight all boids have in pixels. The max is 500 and the minimum 1.</li>
  <li><b>Speed slider</b>: Speed at which boids move in pixels per frame. The max is 15 and the minimum 1.</li>
  <li><b>Collision avoidance speed slider</b>: Turn speed of the first rule in degrees per frame (results in more violent behavior to comply with rule the higher this value is). The max is 10 and the minimum 1.</li>
  <li><b>Direction alignment speed slider</b>: Turn speed of the second rule in degrees per frame (results in more violent behavior to comply with rule the higher this value is). The max is 10 and the minimum 1.</li>
  <li><b>Flock centering speed slider</b>: Turn speed of the first third in degrees per frame (results in more violent behavior to comply with rule the higher this value is). The max is 10 and the minimum 1.</li>
</ul>
</p>

<h2 id="Rule 1">Rule 1: Collision Avoidance</h2>

<p>

</p>

<h3 id="R1 Implementation">Implementation</h2>

<p>

</p>

<h3 id="R1 Behavior">Behavior</h2>

<p>

</p>

<h3 id="R1 Limitations">Limitations</h2>

<p>

</p>

<h2 id="Rule 2">Rule 2: Direction Alignment</h2>

<p>

</p>

<h3 id="R2 Implementation">Implementation</h2>

<p>

</p>

<h3 id="R2 Behavior">Behavior</h2>

<p>

</p>

<h3 id="R2 Limitations">Limitations</h2>

<p>

</p>

<h2 id="Rule 3">Rule 3: Flock Centering</h2>

<p>

</p>

<h3 id="R3 Implementation">Implementation</h2>

<p>

</p>

<h3 id="R3 Behavior">Behavior</h2>

<p>

</p>

<h3 id="R3 Limitations">Limitations</h2>

<p>

</p>

<h2 id="Conclusion">Conclusion</h2>

<p>
The specific implementation of the three rules can be applied in a multitude of applications, the most relevant of all being video games and movies. The creatures the algorithm controls can greatly vary in conjunction with the arguments used. A more packed behavior better describes a group of fish while a more separated grouping aligns better with the behavior of birds. Additionally, there is no reason why the algorithm should be bound to a 2D environment as opposed to a 3D one. Finally, it should be noted that very minor changes to the value of control arguments can vastly alter the group's behavior, make sure to tune them in a way that results in believable movement.
</p>
