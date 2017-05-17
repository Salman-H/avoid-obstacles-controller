# avoid-obstacles-controller
A controller that steers the robot away from obstacles to avoid a collision. Implemented as part of a Georgia Tech Mobile Robotics course project.

Simiam is a MATLAB-based educational bridge between theory and practice in robotics created at Georgia Tech GRITS Lab.

<br />
<h4>1. Transformation of Coordinate Reference Systems</h4>
<p>A robot is <i>seen</i> from the world's perspective. To avoid obstacles, they need to be observed on this <i>world reference frame</i> on which
the robot is located. To achieve this, obstacle coordinates for each InfraRed sensor are transformed from their <i>local sensor frame</i> to the 
<i>robot reference frame</i>, and then from the robot frame to the world frame.</p>

<p>After successfully doing these transformations, the points detected by each of the five IR sensors can be located on the <i>world frame</i>:</p>
<img src="https://github.com/Salman-H/avoid-obstacles-controller/blob/master/figures/test_1_and_2_a.jpg" alt="" width="600">
<br />
<img src="https://github.com/Salman-H/avoid-obstacles-controller/blob/master/figures/data_1_and_2_a.jpg" alt="" width="750">
<br />
<img src="https://github.com/Salman-H/avoid-obstacles-controller/blob/master/figures/test_1_and_2_b.jpg" alt="" width="600">
<br />
<img src="https://github.com/Salman-H/avoid-obstacles-controller/blob/master/figures/data_1_and_2_b.jpg" alt="" width="750">


<h4>2. Obstacle Avoidance Heading</h4>
<p>Vectors are computed from the center of the robot to each of the transformed IR sensor points, then weighed and summed to produce a resultant vector, 
<b>u_ao</b>, that points in the direction of free space (away from the obstacle). A heading, <b>theta_ao</b>, is then computed using this
vector and the PID controller used to steer the robot to this heading to avoid a collision.</p>

<img src="https://github.com/Salman-H/avoid-obstacles-controller/blob/master/figures/sim_ao_3_a.jpg" alt="" width="600">
<br />
<img src="https://github.com/Salman-H/avoid-obstacles-controller/blob/master/figures/sim_ao_3_b.jpg" alt="" width="600">
<br />
<img src="https://github.com/Salman-H/avoid-obstacles-controller/blob/master/figures/plot_ao_3_a.jpg" alt="" width="600">
<br />
<img src="https://github.com/Salman-H/avoid-obstacles-controller/blob/master/figures/plot_ao_3_b.jpg" alt="" width="600">
