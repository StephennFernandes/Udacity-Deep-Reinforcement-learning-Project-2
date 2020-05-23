# project 2 : Continious Control 

For this project we work with a 3D unity environemnt which has a double joined arm that moves in the targets location . A reward of +0.1 is given for each step the agent takes on the arm to move in the goals direction , it has to maintain its position at the target location for as many time steps possiable. 

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

There are 2 seprate versions of the unity environment one with single agent environment and the second one with 20 multiple agents in the same environment . 

The RL task here is an episodic task in order to solve the environment the agent must obtain an average of +30 over 100 consecutive episodes. 

# Algorithm used 
A Deep Deterministic Policy Gradient was proposed in Continious control with a deep RL learning algorithm called DDPG is an off policy algorithm which can be used only for policy based problems . An actor and critic seprate neural networks are used . the algorithm additionally also uses experience replay and target networks to stabilize the training. 

The Actor netowrk consists of three fully connected layers with batch normallization to the first layer . it maps the states and actions and used Relu activation functions until the last layer. 

The critic network also consists of three fully connected layer with batch normalization applied at the first layer. the netowkr maps pairs to Q-values. it uses ReLU as activation function in the first 2 layers and no activation function for the last layer. 

# Hyperparameters 

	
    fc1_units=400 # Number of nodes in the first hidden layer
    fc2_units=300 # Number of nodes in the second hidden layer
    BUFFER_SIZE = int(1e6) # replay buffer size
    BATCH_SIZE = 128 # minibatch size
    GAMMA = 0.99 # discount factor
    TAU = 1e-3 # for soft update of target parameters
    LR_ACTOR = 1e-3 # learning rate of the actor
    LR_CRITIC = 1e-3 # learning rate of the critic
    WEIGHT_DECAY = 0 # L2 weight decay
    LEARN_EVERY = 20 # learning timestep interval
    LEARN_NUM = 10 # number of learning passes
    GRAD_CLIPPING = 1.0 # gradient clipping
    OU_SIGMA = 0.2 # OU noise parameter
    OU_THETA = 0.15 # OU noise parameter
    EPSILON = 1.0 # for epsilon in the noise process (act step)
    EPSILON_DECAY = 1e-6 3 epsilon decay rate
    num_episodes=2500 # maximum number of training episodes
    max_t=1000 # maximum number of timesteps per episode



