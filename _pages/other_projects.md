---
layout: archive
title: "Other Projects"
permalink: /other_projects/
author_profile: true
---

<style>
  .boxed {
    color: black;
    border: 3px solid black;
    margin: 0px auto;
    padding: 10px;
    border-radius: 10px;
  }
</style>

This page details non-research projects that I've undertaken personally or for coursework. Click on project titles to see more detail. Some minor projects have been omitted for brevity.

## 2020
<details>
<summary><b>Forecasting Object-Pushing with the Meta-Extended Kalman Filter</b></summary>
<div class="boxed">

Course Project: _Deep Multi-Task and Meta Learning (CS 330)_  
Stanford University

This project was my initial attempt at the one-shot learning using meta-EKFs project on my research page. For more detail, see my research blurb about the project. Like in continuous-time neural filters, we approach the problem of meta-learning using classic state estimation techniques. By nature, the Kalman filter is somewhat like an adaptive controller (but "adapting" to unknown states, not system parameters). The key idea here is seeing if we can use a scheme similar to the decades-old [dual estimation](https://papers.nips.cc/paper/1999/file/f50a6c02a3fc5a3a5d4d9391f05f3efc-Paper.pdf) filter schemes to perform task-specific adaptation like in [Model-Agnostic Meta-Learning](https://arxiv.org/pdf/1703.03400.pdf), but backpropagating through filter operations rather than through gradient steps. The report has been withheld since it contains information that will be in the final paper.
</div>
</details>

<details>
<summary><b>Safe Multi-Rate Quadcopter Trajectory-Tracking</b></summary>
<div class="boxed">

Course Project: _Optimal and Learning-Based Control (AA 203)_  
Stanford University  
Collaborators: [Daniel Sotsaikich](https://www.linkedin.com/in/dsotsaikich/), [Brent Yi](https://brentyi.com/)

[[Video]](https://www.youtube.com/watch?v=je6I42qc2Z8)

This project sought to implement the multi-rate safe control scheme from [[this paper]](https://arxiv.org/pdf/2004.01761.pdf) in simulation. In the paper, they consider the simple case of a segway, while we instead consider here the 3D motion of a quadcopter.

The key idea is that we can maintain two controllers: one which operates slowly and generates high-level goals using some computationally-intensive planning scheme like MPC. A second fast controller maintains immediate safety using control barrier functions, which prevents the system from colliding with obstacles in the environment. We show that there are control frequencies where the slow controller alone fails, but the combination of the slow and fast controllers succeed in stabilizing the quadcopter to a desired trajectory safely.
</div>
</details>

<details>
<summary><b>Continuous-Time Neural Filters</b></summary>
<div class="boxed">

Course Project: _State Estimation and Filtering for Aerospace Systems (AA 273)_  
Stanford University  
Collaborators: [Brent Yi](https://brentyi.com/)

[[Report]](http://alberthli.github.io/files/other_projects/ctnfs/ctnf_report.pdf)

While most filter-based dynamics learning algorithms (e.g. [Deep Markov Models](https://arxiv.org/pdf/1609.09869.pdf), [Deep Variational Bayes Filters](https://arxiv.org/pdf/1605.06432.pdf), [Kalman Variational Autoencoders](https://proceedings.neurips.cc/paper/2017/file/7b7a53e239400a13bd6be6c91c4f6c4e-Paper.pdf), etc.) operate in discrete-time, we wanted to study the use of continuous-time filters for the same effect. Inspired by the advent of [neural ODEs](https://arxiv.org/pdf/1806.07366.pdf), we explored the setting where we used the Kalman-Bucy filter to consume data and a differentiable ODE solver to try learning the underlying nonlinear dynamics governing the system evolution.

The key idea behind the filter is _posterior inference_, or computing a belief over some latent state from a sequence of observations. The classical Kalman filter provides a very fast, iterative way to conduct posterior inference, which makes it perfect for an optimization-based approach towards learning dynamical and observation models. 

In these preliminary results, we found that there were some benefits to the continuous-time formulation, though our results were a little raw (preceding our Replay Overshooting paper by several months). Ultimately, the project was fairly novel and it was fun finding rarely-explored perspectives connecting state estimation theory and deep learning. 
</div>
</details>

<details>
<summary><b>Safe Multi-Agent Collaborative Transport</b></summary>
<div class="boxed">

Course Project: _Multi-Robot Control, Communication, and Sensing (AA 277)_  
Stanford University  
Collaborators: [Bibit Bianchini](http://www.bianchini-love.com/), [Lauren Luo](https://www.linkedin.com/in/lauren-luo-989945b4/)

[[Slides]](https://docs.google.com/presentation/d/1x-2FnyPR2dk_yOQGTGBPL0lex5EPH7kUlvsOLxj1c68/edit?usp=sharing)

This project is my first go at the multi-agent collaborative transport project on my research page. For the research-level detail, see my blurb on the research page. Some of the interesting results from the project implementation are shown here. I've withheld the project report and code, since those will end up being part of the paper results.

---

<p align="center">
  <img src="http://alberthli.github.io/files/other_projects/safe_carry/load_path.png" />
</p>
<p style="text-align: center; font-size: 16px"><i>The full trajectory with obstacles and some close-ups of evasive action. Lasers that did not detect obstacles are not shown for improved clarity.</i></p>

</div>
</details>

## 2019
<details>
<summary><b>Autonomous "Delivery" Vehicle</b></summary>
<div class="boxed">

Course Project: _Intro to Robot Autonomy (AA 274A)_  
Stanford University  
Collaborators: [Daniel Sotsaikich](https://www.linkedin.com/in/dsotsaikich/), [Brent Yi](https://brentyi.com/)

[[Slides]](http://alberthli.github.io/files/other_projects/delivery_bot/delivery_slides.pdf)

In this project, we were tasked with creating a "delivery" robot that could navigate in a mock environment to do food pickup and delivery. The system was a simple differential drive robot (Turtlebot) with a Velodyne lidar sensor mounted on top. The robot operated in two phases: a manual exploration phase in which a SLAM algorithm would map out the environment, including key "pickup" and "delivery" locations, and an autonomous delivery phase, in which we could suggest any order of pickup and delivery locations and the robot would plan the trajectory (keeping in mind obstacles in the environment and replanning as necessary) while navigating from location to location.

All software was built on ROS. The delivery logic was encoded in a finite state machine and planning was done using A\*. We also implemented a web-based command center that allowed any web-connected device (like phone or laptop) to manually control the robot, display the vendors on the map, and allowed a quick switch between exploration and delivery modes. Unfortunately, there is no video of our presentation run, but it worked!
</div>
</details>

<details>
<summary><b>Stump Vinyl</b></summary>
<div class="boxed">

Course Project: _Mechatronics (ME 102B)_  
UC Berkeley  
Collaborators: [Miranda Maravilla-Louie](https://www.linkedin.com/in/mirandajml/), Matt Morrison, [Sepehr Rostamzadeh](https://www.linkedin.com/in/sepehr-rostamzadeh/), [Daniel Sotsaikich](https://www.linkedin.com/in/dsotsaikich/), [Kriya Wong](https://www.linkedin.com/in/kriya-wong-1431a5107/)

[[Video]](http://alberthli.github.io/files/other_projects/stump_vinyl/stump_vinyl_vid.mp4) [[Poster]](http://alberthli.github.io/files/other_projects/stump_vinyl/stump_vinyl_poster.pdf)

This was one of my favorite projects and the brainchild of group member Matt (who humorously narrates the linked video). We sought to design and fabricate from scratch a 2-speed vinyl record player embedded into a real redwood tree stump acquired from a felled tree after a storm on one of Matt's friend's property. The end product featured a beautiful wooden exterior with a simplistic, custom-designed interface. I was primarily involved in electronic integration, motor control, and hardware specification. I was secondarily involved in the mechanical design of the moving parts like the turntable and tone arm.

First, the stump's ends were flattened to use as datum surfaces for a wood router. Afterwards, the raw stump still had many cracks and holes in it in its natural condition that made it unsuitable for immediate processing. A few runs of overnight epoxy filling helped fill those areas and strengthen the interior material. Over the course of a few months, the interior was milled out to allow the electronics and other mechanical components to be mounted.

The turntable was manufactured from aluminum on a CNC mill and designed to be stiff and structurally sound while light. Record players have two common methods for actuating the turntable: direct and belt drive. For this project, we opted to use a belt drive system so we could abuse a high drive ratio in order to run the motor at a higher RPM, thus allowing the use of a lower resolution encoder.

With the belt drive system, we also had to design a method to consistently tension the belt. For this, the entire motor assembly was placed into a carriage-style sliding assembly that allowed the user to move its position until the belt was sufficiently tensioned.

The tone arm of a record player is a delicate piece: it acts as the part holding the needle and must apply a very precise force on the record. Too low, and the audio signal will not be very strong. Too high, and the record runs the risk of being damaged by the needle force. Further, the base of the tone arm must also exhibit very low friction so that as the record grooves push on the needle, the base rotates smoothly. The placement of the tone arm is also important. The greater the tangency of the tone arm direction to the grooves, the better the sound quality. We used the Lofgren B method to place the tone arm in an optimal position. We also implemented an auto-stop system to detect when the record ended, stopping the turntable.

The whole system featured a fairly interconnected set of electronic parts all powered at different voltage levels. Our goal was to fully integrate the power, speaker, motor control, and audio processing circuits together on a physically small module that was easy to design around and that minimized the weight of the player. Most of the electronic components were bought off-the-shelf, including a buck converter, the Teensy 3.6 as the microcontroller, the audio adapter board for signal processing, the motor driver board and motor, a logic level shifter, and and amp to go along with the speakers. I also wrote some low-level code to read the motor encoders and implemented a simple PID scheme to control the motor speed.

Stumpy is now retired and resides with Matt's parents in San Diego.

---

<p align="center">
  <img src="http://alberthli.github.io/files/other_projects/stump_vinyl/stump_innards.jpg" />
</p>
<p style="text-align: center; font-size: 16px"><i>The interior of the enclosure after the milling process.</i></p>

<p align="center">
  <img src="http://alberthli.github.io/files/other_projects/stump_vinyl/finished_stump.png" />
</p>
<p style="text-align: center; font-size: 16px"><i>The finished record player.</i></p>

</div>
</details>

<details>
<summary><b>Dynamic Robot Arm Trajectory-Tracking</b></summary>
<div class="boxed">

Course Project: _Nonlinear Systems (ME C237)_  
UC Berkeley  
Collaborators: [Daniel Sotsaikich](https://www.linkedin.com/in/dsotsaikich/), [Philipp Wu](https://wuphilipp.github.io/)

[[Slides]](https://docs.google.com/presentation/d/1SHs37LoZgW16Sz8T-8pkzUrenk6HyGlApq3xy3vODRo/edit?usp=sharing)

This project sought to control a 6-DOF robot arm along a pre-computed trajectory using input-output linearization. In particular, our goal was to judge the capacity of this nonlinear controller to perform complex tasks such as ball-catching by analyzing its performance in tracking a relatively quick-moving trajectory. In doing so, we abstracted the ability of the controller away from other aspects of task completion, such as perception, trajectory optimization, etc. We found the controller's performance to be passable for a relatively naive application of I/O linearization.

The arm, its model, and all control code are part of the [_Blue_](https://www.berkeleyopenarms.org/) project (now at Berkeley Open Arms), and are the product of research done from UC Berkeley's [Robot Learning Lab](http://rll.berkeley.edu). I have no affiliation with the RLL.

Since we had direct access to the arm's physical parameters, we could derive an analytical model for the robot dynamics from standard open-chain manipulator models. We let some symbolic computations run for a few days to compute all the necessary matrix functions, then compiled the results into fast C++ functions. We also generated smooth trajectories using target points and cubic spline interpolation. Our desired trajectory was just chosen as three random points that the robot cycled between. After some iteration, we found that some PD-style modifications to the I/O linearization controller were enough to achieve fairly good tracking. For more details, see the slides.

---

<p align="center">
  <img src="http://alberthli.github.io/files/other_projects/dyntrajtrack/cycle.gif" />
</p>
<p style="text-align: center; font-size: 16px"><i>Blue tracking a cyclic trajectory.</i></p>

</div>
</details>

## 2018
<details>
<summary><b>Attitude and Heading Reference System</b></summary>
<div class="boxed">

Personal Project  
Collaborators: [Philipp Wu](https://wuphilipp.github.io/)

[[Code]](https://github.com/alberthli/ahrs)

This was a fun personal project that helped introduce me a bit to more complex ideas in sensor fusion, communication protocols like I2C, and hardware calibration routines. The idea of an attitude and heading reference system is to provide _attitude_ information (roll, pitch, yaw or some equivalent rotational coordinates) while also estimating the heading relative to the global magnetic field. Typically, you can use a 9-axis IMU consisting of a magnetometer, accelerometer, and gyroscope and then use some attitude estimation algorithm to filter the signals.

The traditional method here is the Kalman filter, though there are newer and more computationally efficient (with looser accuracy guarantees) methods like Mahony's or Madgwick's filters for aerospace systems that work in quaternion space. We opted for an implementation of Madgwick's algorithm for this project. One of the most fun parts of the project was learning how to mess around with bit registers on these sensors to set things like sensitivity/precision, communication modes, and data rate selection. We ultimately ended up implementing a bunch of stuff in both C++ and Python, but the system wasn't really used for anything and by 2018 we were too busy to make too much more progress on it.
</div>
</details>

## 2017
<details>
<summary><b>Simulated Robot Arm MPC</b></summary>
<div class="boxed">

Course Project: _Model Predictive Control and Loop Shaping (ME C231A)_  
UC Berkeley  
Collaborators: [Rachel Thomasson](https://www.linkedin.com/in/rachelthomasson/), [Philipp Wu](https://wuphilipp.github.io/), [Allan Zhao](https://www.linkedin.com/in/allan-zhao-0410682b/)

This project sought to implement a model predictive controller in simulation for a 6-DOF arm to follow pre-computed trajectories. The arm not only successfully followed these trajectories, it demonstrated rejection of randomly generated Gaussian perturbations to the end-effector. Simulations were conducted in MATLAB using the nonlinear solver fmincon.

The arm, its model, and all control code are part of the [_Blue_](https://www.berkeleyopenarms.org/) project (now at Berkeley Open Arms), and are the product of research done from UC Berkeley's [Robot Learning Lab](http://rll.berkeley.edu). I have no affiliation with the RLL.

I chose two trajectory geometries for study: a square and a helical path. Curves describing these motions were plotted in Cartesian space and discretized into sets of target points used for the controller.

Model predictive control operates on the principle of solving constrained finite time optimal control (CFTOC) problems repeatedly until an end condition is satisfied (there may not be an end condition). The CFTOC problem can be defined by a cost function and the constraints on the state and input space. We defined our states as the joint positions and velocities and the inputs to be actuator torques. An equality constraint is also applied: the evolution of the system's dynamics defined in the previous section.

To reduce computation time, at each time step I linearized the dynamics around the current state of the system. Our controller divided the trajectory-tracking problem into several smaller ones whose end conditions were satisfied when the end-effector position was close to the next point in our discretized trajectory. The end-effector would attempt to travel in a straight line in Cartesian space between these points. We also showed that our controller is quite robust to random Gaussian force disturbances applied to the end-effector.

The approach taken here was quite naive, and it was a while before I learned more advanced optimal control techniques like iLQR or techniques in sequential convex programming.

---

<p align="center">
  <img src="http://alberthli.github.io/files/other_projects/simmpc/disturbances.gif" />
</p>
<p style="text-align: center; font-size: 16px"><i>The simulated controller rejecting disturbances while tracking a trajectory.</i></p>

</div>
</details>

<details>
<summary><b>Kinematic Ball-Catching</b></summary>
<div class="boxed">

Course Project: _Intro to Robotics (EE C106A)_  
UC Berkeley  
Collaborators: [Kireet Agrawal](https://www.linkedin.com/in/kireetagrawal/), [David Gealy](https://www.linkedin.com/in/david-gealy-726741b7/), [Rachel Thomasson](https://www.linkedin.com/in/rachelthomasson/), [Philipp Wu](https://wuphilipp.github.io/)

[[Video]](https://www.youtube.com/watch?v=r4Fji2e9nkE&feature=emb_title) [[Slides]](https://docs.google.com/presentation/d/1cxPvYGTbB8BG72-MSRxU9p83Ri8C__usBQ_gA2N2Oko/edit?usp=sharing)

This project sought to implement a real-time method for catching a ball with a 6-DOF robotic arm developed by the Robot Learning Lab. At the time, dynamic methods were deemed too slow to run online, so we used kinematic methods instead. A ball was identified by a Kinect as it was tossed and a Kalman filter estimated the position of the ball when in range of the arm. When a high enough confidence was established, the arm would move to the position it predicted would intercept the ball's trajectory. We were successful in catching almost all underhand throws.

The arm, its model, and all control code are part of the [_Blue_](https://www.berkeleyopenarms.org/) project (now at Berkeley Open Arms), and are the product of research done from UC Berkeley's [Robot Learning Lab](http://rll.berkeley.edu). I have no affiliation with the RLL.

The arm was mounted onto a static frame clamped onto a table. Additionally, ball-tracking was done using a Kinect, which was mounted snugly onto an auxiliary frame that I attached onto the main base. Rather than a traditional end-effector, a velcro ball and a corresponding pad was used to perform the catching. Note the Vive virtual reality trackers attached to the arm's links. These were not used for position feedback, but rather for initial calibration of the arm's position for use in rviz to visualize the arm on lab computers.

The Kinect computed the ball position using a pinhole model and the trajectory of the ball was estimated using projectile motion equations estimated using a Kalman filter. We fixed a desired distance of catching, which formed a sphere, and continuously recomputed the intersection between the ball trajectory and this sphere, which became the desired pad position.

---

<p align="center">
  <img src="http://alberthli.github.io/files/other_projects/ball_catch/catches.gif" />
</p>
<p style="text-align: center; font-size: 16px"><i>David tossing the ball and Blue catching it.</i></p>

</div>
</details>

<details>
<summary><b>Beacon-Following Car</b></summary>
<div class="boxed">

Course Project: _Microprocessor-Based Mechanical Systems (ME 135)_  
UC Berkeley  
Collaborators: [Denny Min](https://www.linkedin.com/in/syungdennymin/), [Vedang Patankar](https://www.linkedin.com/in/vedang-patankar-57180317a/), [Patrick Scholl](https://www.linkedin.com/in/patrick-scholl-0a5a1b10b/)

This project sought to hack a toy RC car and implement two main functions: following the pulse of a handheld ultrasonic beacon or navigating to a target GPS coordinate in real time. The hardware provided to us was the NI MyRIO, and we supplemented that with ultrasonic and infrared sensors, a magnetometer, an accelerometer, and a GPS module. We were successful in implementing both functions.

The system was an RC car with several layers. The inner layer housed the motors and H-bridges, the middle layer housed the MyRIO, and the upper layer held the battery and the sensor array. At the front of the car were three ultrasonic receivers to interface with the beacon.

The beacon was composed of a single ultrasonic transducer and an array of IR LEDs. The IR signal was used to synchronize the clocks between the ultrasonic transducer and the receiver array on the car so that accurate time of flight could be recorded both for distance and direction control. I designed the circuit for the beacon and implemented a state machine architecture to distinguish between waiting on IR signals, waiting on ultrasonic signals, and interpreting ultrasonic signals to actuate the motors.

The other mode of the vehicle was GPS coordinate-tracking. In this mode, the user simply input global coordinates to command the vehicle to and it would automatically move to that location. Unfortunately, the car was destroyed for parts after the project and there wasn't too much documentation during the process.

---

<p align="center">
  <img src="http://alberthli.github.io/files/other_projects/beacon_car/gui.png" />
</p>
<p style="text-align: center; font-size: 16px"><i>The GUI for the car's settings.</i></p>

<p align="center">
  <img src="http://alberthli.github.io/files/other_projects/beacon_car/car_move.gif" />
</p>
<p style="text-align: center; font-size: 16px"><i>The car responding to the beacon during a test session.</i></p>

</div>
</details>

<details>
<summary><b>Simply Statics</b></summary>
<div class="boxed">

Course Project: _Advanced Programming with MATLAB (E 177)_  
UC Berkeley

[[Code]](https://github.com/alberthli/simplystatics)

This project sought to implement a solver for statically determinate 2D beams with transverse loads applied as an educational tool for new engineering undergrads. In particular, my goal was for the solver to analytically calculate shear and moment diagrams for an arbitrarily high number of loads, including distributed loads represented by arbitrary real functions. Online beam calculators exist, but typically impose limits on how many loads can be applied and only consider uniform distributed loads. This project was part of a larger submission with three distinct parts. There were no collaborators for this portion of the project.

The calculator analyzed the system constraints defined by the user to verify that the constraints were valid. Then, the boundary conditions were applied and symbolic integration was performed to retrieve the shear and moment functions describing the beam's reaction to external loadings.

---

<p align="center">
  <img src="http://alberthli.github.io/files/other_projects/simply_statics/gui.png" />
</p>
<p style="text-align: center; font-size: 16px"><i>The GUI. Note the complex user-defined transverse load.</i></p>

</div>
</details>

<details>
<summary><b>Smart Exercise Band</b></summary>
<div class="boxed">

3D Printing Hack-a-thon: _3DMC_  
UC Berkeley  
Collaborators: [Kireet Agrawal](https://www.linkedin.com/in/kireetagrawal/), [Travis Brashears](http://www.travisbrashears.com/), [Sepehr Rostamzadeh](https://www.linkedin.com/in/sepehr-rostamzadeh/), [Philipp Wu](https://wuphilipp.github.io/)

This project sought to prototype a flexible workout band that could analyze the movements of an individual engaging in physical activity and give encouragement or advice in response. The allotted time for the hack-a-thon was 24 hours. We were successful in producing the band, collecting data, and returning basic feedback to the user. However, more complex analysis of the data was not possible given our time constraints. We placed 2nd at the competition.

The band itself was 3D-printed on a flexible filament called NinjaFlex. This material printed extremely slowly and was very prone to failure - we had about 3 failed prints over the duration of the hack-a-thon, but we were lucky to be able to print on multiple printers at once. The user wears the armband on the upper arm and performs exercises. Onboard is a 9-axis IMU that measures angular data during a motion. There is also an audio unit and speaker that can give live feedback to the user, though this feature was not fully implemented during the duration of the hack-a-thon.

---

<p align="center">
  <img src="http://alberthli.github.io/files/other_projects/exercise_band/armband.jpg" />
</p>
<p style="text-align: center; font-size: 16px"><i>Me volunteering my arm to test the band.</i></p>

</div>
</details>

## 2016
<details>
<summary><b>Whiteboard Bot</b></summary>
<div class="boxed">

Robotics Competition: _Dorm Ex Machina_  
UC Berkeley  
Collaborators: [Adam Castiel](https://www.linkedin.com/in/adam-castiel-15b61a123/), [Denny Min](https://www.linkedin.com/in/syungdennymin/)

[[Video]](https://www.youtube.com/watch?v=GfPKv-0IBVw)

This project was a part of a larger one whose goal was to prototype a whiteboard marker printer, a device that could analyze an image and reproduce it on a whiteboard. My portion of the project was the image analysis algorithm that took an image as an input and produced two outputs: a visual of the path a marker would take to draw the image, and a set of instructions passed to servos commanding the device. I was successful in implementing the algorithm, but the resolution of the servos permitted only simple images to be drawn.

The path generated for the marker was meant to replicate human tendencies in drawing features. For example, outlines would tend to be traversed first with the details of the interior being filled in after. This feature-based approach to drawing was designed to produce a more artistic rather than mechanistic device. The path generator was written in Java and the generated path was converted into servo commands for the physical drawing. Unfortunately, little documentation remains of the mechanical system, which was later destroyed after the competition to re-use parts.
</details>
