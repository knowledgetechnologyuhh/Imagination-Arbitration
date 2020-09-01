# Imagination-Arbitration
This repository contains Python implementation for the Intrinsically Motivated Meta-Controller (IM2C) algorithm and Integrated-Imagination Arbitration (I2A) learning framework [[1]](#1). The implementation considers the problem of learning vision-based robotic grasping on the NICO robot [[2]](#2), but can be easily tuned towards other control problems with different sensory inputs.

## Dependencies
* python 2.7
* numpy 1.14.3
* keras 2.2.2
* tensorflow 1.10.1
* cv2 3.4.3

## Instructions
* Make sure you load the scene NICO-seated.ttt into the CoppeliaSim (previously V-REP) simulator [[3]](#3).
* Use im2c.py as the main script for running IM2C or i2a.py for running I2A. Simply run 
```
python im2c.py
```
or
```
python i2a.py
```

## File description
* To enable the remote API functionality of CoppeliaSim from Python client, you will need following 3 files: vrep.py, vrepConst.py, and remoteApi.so
* NICO-seated.ttt is the simulation scene that includes the robot and its environment.
* env.py contains all functions related to the simulation environment, such as connecting to the simulator, controlling the joints, receiving the visual input, and computing the reward signal.
* node.py and itm.py implement the Instantaneous Topological Map (ITM) [[4]](#4), which is the growing self-organizing network used in our work, and compute the proposed local learning progress.
* networks.py contains the deep neural architectures for the actor, critic and local world models, as well as the implementation of the gradient-based model predictive control.
* parameters.py contains hyperparameter values.
* im2c.py is the main script for running the IM2C learning algorithm.
* i2a.py is the main script for running the I2A learning framework.
* goals.txt contains a list of random goal positions for the grasping object.

## References
<a id="1">[1]</a> 
M. B. Hafez, C. Weber, M. Kerzel, and S. Wermter. Improving Robot Dual-System Motor Learning with Intrinsically Motivated Meta-Control and Latent-Space Experience Imagination. Robotics and Autonomous Systems, 2020 (to appear)

<a id="2">[2]</a> 
M. Kerzel, E. Strahl, S. Magg, N. Navarro-Guerrero, S. Heinrich, and S. Wermter. NICO– Neuro-Inspired COmpanion: A developmental humanoid robot platform for multimodal interaction. In 2017 26th IEEE International Symposium on Robot and Human Interactive Communication (RO-MAN), pages 113–120, 2017.

<a id="3">[3]</a> 
E. Rohmer, S. P. Singh, and M. Freese. V-REP: A versatile and scalable robot simulation
framework. In 2013 IEEE/RSJ International Conference on Intelligent Robots and Systems,
pages 1321–1326, 2013.

<a id="4">[4]</a> 
J. Jockusch and H. Ritter. An instantaneous topological mapping model for correlated stimuli. In International Joint Conference on Neural Networks (IJCNN), volume 1, pages 529–534, 1999.

## Cite
If you use the code, please cite the following paper:

```
@article{hafez2020improving,
  title={Improving Robot Dual-System Motor Learning with Intrinsically Motivated Meta-Control and Latent-Space Experience Imagination},
  author={Hafez, Muhammad Burhan and Weber, Cornelius and Kerzel, Matthias and Wermter, Stefan},
  journal={arXiv preprint arXiv:2004.08830},
  year={2020}
}
```

## Contact
Burhan Hafez - hafez@informatik.uni-hamburg.de

