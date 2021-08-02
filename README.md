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
<h3 id="R1 Implementation">Implementation</h2>

<p>
Attempts to avoid other agents by minimizing the total distance between all visible boids. This is done by making three virtual copies that move differently. One is updated after a left turn, the second after a right turn and the last without turning. Whichever has the lowest total distance becomes the real boid. A consequence of this approach is that sometimes the boid will not care to avoid crashing given that the overall distance decreases. To prevent this, I added a minimum distance between boids that the agent will try to maintain as much as possible.
</p>

<h3 id="R1 Behavior">Behavior</h2>

<p>
Boids attempt to avoid collisions at all cost except when limited by speed, turns, or information. As a result, agents don't crash when separated from most of the flock but fail to do so when the rule's speed is suppressed or combined with rules number 2 and or 3. Removing it, however, results in unnatural behavior even when 2 and 3 are active.
</p>

<h3 id="R1 Limitations">Limitations</h2>

<p>
Due to static speed and rotation degrees, collisions that should be easily avoided aren't at times. This should be fixed by adding a speed modifier and variable rotation speed. Additionally, due to screen wrapping, boids are sometimes stuck being pushed in and out of bounds due to the boid's vision teleportation. This was somewhat fixed by warping boids a few pixels away from the margins. An additional solution could be to make boids automatically steer away from walls.<br><br>
[Insert Image]
</p>

<h2 id="Rule 2">Rule 2: Direction Alignment</h2>
<h3 id="R2 Implementation">Implementation</h2>

<p>
Moves agents in the direction visible boids are heading. This is done by computing the average direction of all boids and steering the agent in that direction. If left will more effectively get us to the average, then we steer left. If a right does it instead, we steer right. Finally, if we happen to be heading in the average direction (or there are no nearby boids) we continue straight.
</p>

<h3 id="R2 Behavior">Behavior</h2>

<p>
Agents attempt to move in the same direction as nearby boids dampening the other rule's behavior. We can see its effect by activating rules 1 and 2 simultaneously, which results in the boids spreading out and moving in the same direction (a much less chaotic behavior than when we only had rule 1 activated).<br><br>
[Insert Image]
</p>

<h3 id="R2 Limitations">Limitations</h2>

<p>
If the speed is too high the turn might overshoot resulting in a wiggle motion. This effect is not seen when the other two rules are active.
</p>

<h2 id="Rule 3">Rule 3: Flock Centering</h2>
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
