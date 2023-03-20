# Collaborative adaptive cruise control and energy management strategy for extended-range electric logistics van platoon

This paper improves the economy of the extended-range electric logistics van (ERELV) platoon from two aspects of cooperative adaptive cruise control (CACC) and energy management strategy (EMS).
Based on the DMPC algorithm, an Eco-CACC controller with the optimization goals of stability, comfort and energy-saving is designed.
The multi-agent deep reinforcement learning (MADRL) algorithm is used to solve the EMS of the ERELV platoon.
DQN, DDPG and MADDPG were used to solve the energy management strategy of extended range electric logistics platoon.

## Eco-CACC and MADRL EMS overall control framework
![论文图片](https://user-images.githubusercontent.com/69177652/225628593-3d345c6e-bc35-4cf5-81fa-339341a6799a.png)
 
## Eco-CACC based on DMPC 
A single-point optimization problem is defined on each vehicle node in the platoon, and the model prediction optimization problem of all nodes needs to be solved at each optimization moment.  Using the domain node information obtained by the PLF communication topology, each sub-problem is optimized to obtain the control input of the vehicle.
###
![image](https://user-images.githubusercontent.com/69177652/226297689-92c32791-68aa-42fa-b71d-669640bc879e.png)

## EMS for ERELV platoon
The state transition of ERELV has the Markov property and generates a corresponding energy consumption at each time step. Since each agent cannot know the complete environment state, the EMS of the ERELV platoon can be modeled as a partially observable POMDP. The task types applied by MADRL algorithm are divided into fully cooperative, fully competitive and hybrid types. For the EMS of the ERELV platoon, each vehicle node needs to jointly explore the optimal control behavior under different vehicle states, so it is a fully cooperative MADRL problem.
###
![image](https://user-images.githubusercontent.com/69177652/226298289-82a1e4d8-87c2-4ea5-8b55-9f2d9d0f8c90.png)
