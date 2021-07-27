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

</p>
