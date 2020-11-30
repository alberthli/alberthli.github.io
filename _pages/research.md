---
layout: archive
title: "Research"
permalink: /research/
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

This page lists my accepted/in-review publications with more detail, links to the papers, and supplemental material like media, code, and citations. I also provide short descriptions of my current research, but withhold some of the important technical details since the work is ongoing. Click on project titles to see more detail. For more information on my current research, please email me directly. For a more condensed overview of my research, look at my CV.

## Current Research
<details>
<summary><b>One-Shot Learning Physics Models with the Meta-Extended Kalman Filter</b></summary>
<div class="boxed">

Collaborators: [Philipp Wu](https://wuphilipp.github.io/), [Monroe Kennedy III](https://monroekennedy3.com/)

[Meta-learning](https://arxiv.org/pdf/2004.05439.pdf), or learning-to-learn, is a relatively new sub-field in deep learning that involves training machines that are adaptable to a variety of tasks rather than specializing in any particular one. This paradigm is useful when considering cases where data are sparse or when training a model from scratch is simply impractical. Meta-learning is in fact the _default_ mode of learning for humans and other biological organisms: during childhood, we develop very strong priors for how the world roughly operate and tune our expectations when we observe task-specific information. For example, we have strong priors for how projectile motion should look (e.g. tossing a ball in the air), but we can adjust our spatiotemporal predictions of a ball-shaped balloon being thrown after we see it being tossed once.

It's this adaptability that we are targeting in this project. We would like to investigate the _one-shot_ setting, where the agent gets to observe on one trajectory of some task to adjust its task-specific physics-based prior. Then, we would like the agent to predict the rest of any query trajectories we give it. For example, it gets to see some arbitrary object being pushed on a table. Then, given one second of new pushing data, we may ask it to predict the following 9 seconds.

The key tool we are using is the extended Kalman filter, which we have used in a learning-based prediction setting with great success for single-task prediction (see my paper on Replay Overshooting). Our preliminary results suggest that on the [MIT Push](https://mcube.mit.edu/push-dataset/index.html) dataset, we have reasonable prediction quality, though we still need to implement more baseline models from the literature for fair comparisons.
</div>
</details>

<details>
<summary><b>Safe Multi-Agent Collaborative Transport Without Communication</b></summary>
<div class="boxed">

Collaborators: [Monroe Kennedy III](https://monroekennedy3.com/)

Consider a situation where you are a leader in a group of heterogeneous robotic assistants and you want to carry some heavy object from one location to another through a busy environment. In this scenario, each agent has a distinct field of view, but ultimately would like to enforce some notion of safely carrying the object while still following the leader. Since humans don't have a WiFi or Bluetooth module in their brains, we additionally enforce that the cooperation is done without explicit communication except through sensed forces on the load.

This project studies a heuristically-motivated decentralized dynamical prediction strategy where each agent estimates the aggregate behavior of every other agent in the system and tries to apply an input it believes will keep the load safe using [_control barrier functions_](https://arxiv.org/pdf/1903.11199.pdf). We also develop a notion of _dynamic trust_, which is a way for robots to mediate the amount of faith they have in the group to maintain safety. Our preliminary results in simulation show that this strategy is effective for following a nominal trajectory even when obstacles directly block the motion of the system.
</div>
</details>

<details>
<summary><b>Human-Robot Cooperative Transport</b></summary>
<div class="boxed">

Collaborators: [Eley Ng](https://www.linkedin.com/in/eleyng/), [J.D. Kelly](https://www.linkedin.com/in/jd-kelly/), [Dylan Losey](https://dylanlosey.com/), [Dorsa Sadigh](https://dorsa.fyi/), [Monroe Kennedy III](https://monroekennedy3.com/)

Consider an episodic setting where a robotic assistant and a human would like to carry an object through an environment. After some period of time, the robotic agent may develop some idea of the strategy employed by the human when carrying the object, and could use this to condition its own control strategy to best achieve consensus during the carrying process.

This project studies the reinforcement learning setting where the robot may learn a conditional policy and an encoder for the human strategy, updating its models after each episode. Our goal is to replicate human-human behavior during the cooperative carrying process, so there may be a pre-training period to initialize the robot policy, followed by episodic adapatation. We are currently setting up a virtual simulation environment for human-human games for initial training data and will move to a physical platform for both data collection and model training later in 2021.
</div>
</details>

## Journal Publications
<details>
<summary><b>[J1] Inverse Statics Optimization for Compound Tensegrity Robots (2020)</b></summary>

<div class="boxed">

[[Paper]](http://alberthli.github.io/files/journal/invstatopt.pdf) [[Code]](https://github.com/apsabelhaus/tiso)

[_Tensegrities_](https://en.wikipedia.org/wiki/Tensegrity) are structures traditionally comprised of rigid bars held in equilibrium by a network of cables. Originally explored by architects and civil engineers, it was not until relatively recently that actuated tensegrities were studied in the field of robotics. As robots, tensegrities enjoy benefits such as lightweight construction and adjustable compliance, exhibiting features of both fully rigid and fully soft robots.

This project studied what we term _compound tensegrities_, whose rigid elements are not just purely compressive bars, but can take on any arbitrary geometry (and therefore also admit net moments about each rigid body). This allows more faithful bio-inspired designs at the expense of complicating traditional tensegrity modeling techniques. In our work, we reformulate the classic _force density method_ used for computing equilibrium forces in network structures to allow for analysis of compound tensegrities and derive a fast optimization-based shape controller that can also be used for quasi-static position control. Finally, the method is validated both in simulation and on a simple hardware test case.

<details>
<summary><b>Full Citation</b></summary>

Andrew Preston Sabelhaus, **Albert Hao Li**, Kimberley Sover, Jacob Madden, Andrew Barkan, Adrian Agogino, and Alice Agogino, "Inverse Statics Optimization for Compound Tensegrity Robots," _IEEE Robotics and Automation Letters_, vol. 5, no. 3, pp. 3982-3989, 2020.
</details>

<details>
<summary><b>Bibtex Citation</b></summary>

```
@article{  
  Sabelhaus2020_invstatopt,  
  title={Inverse Statics Optimization for Compound Tensegrity Robots},  
  author={Sabelhaus, Andrew Preston and Li, Albert Hao and Sover, Kimberley and Madden, Jacob and Barkan, Andrew and Agogino, Adrian and Agogino, Alice},  
  journal={IEEE Robotics and Automation Letters},  
  volume={5},  
  number={3},  
  year={2020},  
  pages={3982-3989},  
}
```
</details>

</div>
</details>

## Conference Publications
<details>
<summary><b>[C2] Ball Juggling on the Bipedal Robot Cassie (2020)</b></summary>
<div class="boxed">

[[Paper]](http://alberthli.github.io/files/conference/cassie.pdf) [[Video]](https://www.youtube.com/watch?v=tLrz_R_T6kg) [[Media]](https://spectrum.ieee.org/automaton/robotics/robotics-hardware/uc-berkeley-cassie-cal-robot-juggle)

To facilitate human-robot interactions and robotic multi-tasking in dynamical environments, we expect them to be able to reason accurately about contact. One of the simplest benchmarks for controlling via contact is the _robotic juggling_ task, which has been replicated before on quadrotors, robotic manipulators, and large humanoid robots.

This project studied _bounce juggling_ on the bipedal robot _Cassie_, developed by Agility Robotics. The distinguishing factor of this work is the difficulty of maintaining an active juggle while also balancing the robot, which is already a nontrivial task depending on the robot's environment. We derived two different juggling controllers, both inspired by _mirror law algorithms_: one based on a simple PID scheme on the ball position and another based on contact force optimization at the robot's feet to maintain balance while driving the juggling with sufficient force and precision.

We found that in simulation, both controllers were locally exponentially stable with Poincaré analysis. We implemented the simpler of the two on Cassie and found that we were able to maintain stable juggles for long periods (with the longest period being over 40 juggles long). Unfortunately, I left Berkeley to start my MS near the end of this project, and we did not have time to implement the second controller online.

<details>
<summary><b>Full Citation</b></summary>

Katherine Lin Poggensee\*, **Albert Hao Li\***, Daniel Sotsaikich\*, Bike Zhang, Prasanth Kotaru, Mark Mueller, and Koushil Sreenath, "Ball Juggling on the Bipedal Robot Cassie," _2020 European Control Conference (ECC)_, Saint Petersburg, Russia, 2020, pp. 875-880. \*Equal Contribution.
</details>

<details>
<summary><b>Bibtex Citation</b></summary>

```
@inproceedings{  
  Poggensee2020_jugglingcassie,  
  title={Ball Juggling on the Bipedal Robot Cassie},  
  author={Poggensee, Katherine Lin and Li, Albert Hao and Sotsaikich, Daniel and Zhang, Bike and Kotaru, Prasanth, and Mueller, Mark and Sreenath, Koushil},  
  journal={2020 IEEE European Control Conference (ECC)},  
  year={2020},  
  address={Saint Petersburg, Russia},  
  pages={875-880},  
}
```
</details>

</div>
</details>

<details>
<summary><b>[C1] Dex-Net 3.0: Computing Robust Vacuum Suction Grasp Targets in Point Clouds Using a New Analytic Model and Deep Learning (2018)</b></summary>
<div class="boxed">

[[Paper]](http://alberthli.github.io/files/conference/dexnet.pdf) [[Video]](https://www.youtube.com/watch?v=dZIHmcaTJ_c&feature=emb_title) [[Code]](https://github.com/BerkeleyAutomation/dex-net)

Vacuum-based grasping and manipulation is a popular alternative to traditional parallel-jaw methods, since we only need to compute a single point of contact and we may be able to lift objects that are difficult to grasp otherwise. The goal of this project was deriving an analytical physics-based suction model, training a grasping planner to find good suction points on various objects from point cloud data, and implementing the system on a real robot.

My role on the project was designing new grippers that could interface with the ABB YuMi and replace its default grippers with lightweight and cost-effective alternatives. I was also responsible for hardware maintenance, including part replacements, fixing electronic parts and circuitry-related failures, and implementing new design features. Ultimately, Dex-Net 3.0 was able to achieve success rates of 98%, 82%, and 58% on the "basic," "typical," and "adversarial" object categories, with adversarial performance improving to 81% when trained specifically on adversarial objects.

<details>
<summary><b>Full Citation</b></summary>

Jeffrey Mahler, Matthew Matl, Xinyi Liu, **Albert Li**, David Gealy, Ken Goldberg, "Dex-Net 3.0: Computing Robust Vacuum Suction Grasp Targets in Point Clouds Using a New Analytic Model and Deep Learning," _2018 IEEE International Conference on Robotics and Automation (ICRA)_, Brisbane, QLD, 2018, pp. 5620-5627.
</details>

<details>
<summary><b>Bibtex Citation</b></summary>

```
@inproceedings{  
  Mahler2018_dexnet3,  
  title={Dex-Net 3.0: Computing Robust Vacuum Suction Grasp Targets in Point Clouds Using a New Analytic Model and Deep Learning},  
  author={Mahler, Jeffrey and Matl, Matthew and Liu, Xinyu and Li, Albert and Gealy, David and Goldberg, Ken},  
  journal={2018 IEEE International Conference on Robotics and Automation (ICRA)},  
  year={2018},  
  address={Brisbane, QLD},  
  pages={5620-5627},  
}
```
</details>

</div>
</details>

## Publications In Review
<details>
<summary><b>[R1] Replay Overshooting: Learning Stochastic Latent Dynamics with the Extended Kalman Filter (2021)</b></summary>
<div class="boxed">

[[Paper]](http://alberthli.github.io/files/in_review/ro_submitted.pdf) [[Video]](https://www.youtube.com/watch?v=eA32XTNRSuY) [[Code]](https://github.com/wuphilipp/replay-overshooting)

Humans are very skilled at spatiotemporal prediction, being able to predict the motion of objects or other agents with fairly minimal observations. This project sought to learn _latent dynamics models_ for the purpose of long-horizon spatiotemporal prediction on robots. As a prerequisite, we must be able to extract _latent states_ from sequences of _observations_. For example, we may be interested in predicting positions of objects (the states) from video frames (the observations). This process is called _posterior inference_.

Many conventional methods in the learning literature conduct posterior inference using an inference network like a bi-RNN, which consumes the data and returns an estimate over some latent state. As it turns out, this is unnecessary, as classical state estimation theory allows approximate inference using methods like the extended Kalman filter, which requires only a dynamics network and an observation model, eliminating the need for a third inference network.

We present results for such a model and also a new learning algorithm called _replay overshooting_ that prioritizes training the dynamics model over the observation model. We show that our method is effective on multiple types of data, such as stripped position data or image sequences, while remaining very parameter-efficient compared to existing methods in the literature. As an added bonus, our method allows seamlessly changing the learned model between discrete and continuous-time, the first such method that natively incorporates both perspectives for dynamics learning.

<details>
<summary><b>Full Citation</b></summary>

**Albert Hao Li\***, Philipp Wu\*, Monroe Kennedy III, "Replay Overshooting: Learning Stochastic Latent Dynamics with the Extended Kalman Filter," _2021 IEEE International Conference on Robotics and Automation (ICRA)_, Xi'an, China, 2021. \*Equal Contribution.
</details>

</div>
</details>
