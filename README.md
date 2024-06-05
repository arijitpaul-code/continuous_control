# continuous_control

**Project Details**

The project is to train an agent to maintain the position of a double-jointed arm at the target location for as many time steps as possible, in Unity Reacher environment. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

The environment is considered solved when the agent get an average score of +30 over 100 consecutive episodes, for the single agent version of the environment. For the multi-agent (20) version of the environment, the agents must get an average score of +30 (over 100 consecutive episodes, and over all agents).

**Getting Started**

The dependencies for the progream are in requirements.txt file, following the instructions in https://github.com/udacity/Value-based-methods#dependencies, with the reacher unity environment sourced directly from (for Linux) https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip (single agent), https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip (multi agent) and extracted and placed in the p2_continuous-control/ folder. After that cuda support was installed using conda install cudatoolkit.

**Instructions**

The entire code is in Navigation.ipynb. To execute, run upto cell "In [2]" (under 2. Examine the State and Action Spaces) sequentially, to load and examine the environment. You can explore the environment to see random actions being taken by executing the next cell. Then execute cells "In [13]" for class definition (QNetowrk, DQN Agent, ReplayBuffer classes), and "In [14]" to build the agent. You can set the following for trying variants of the regular DQN (The setting below is for Dueling DDQN, which gives the best results).

DOUBLE_DQN = True; PRIORITIZED_EXPERIENCE_REPLAY = False; DUELING_DQN = True;

Then there are two options (1) To train - Execute the next cell "In [15]", which will train and output the status of training, ending with a plot of the score. This will save the best model in the 'checkpoint.pth' file (2) Alternatively, execute the model without training by loading the pretrained weights from the 'checkpoint.pth' file, by running the cell "In [16]"

Lastly, run the env.close() cell, when finished.
