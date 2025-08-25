
2025-08-18 17:44

Status:

Tags: [[LLMs(Large language models)]] [[SonyAI]] [[autonomous car]] 




# Gran Turismo Sophy(GT Sophy)

- Sophy is an autonomous racing vehicle bot made for the gran turismo game
- It was built using reinforced learning to be able to learn and beat world champions(It ended up coming in like third place)
- SonyAI used federated learning to efficiently train this AI
- Their goal was to build an AI bot capable of driving as good as the world champions while being limited to only sensory information available to any player(Such as the field of vision from the player perspective, current vehicle position and direction, etc..)
- “We are not building AI to beat humans. We are pursuing AI to ultimately better understand humans. That's what is driving our curiosity” - Kazunori Yamauchi (Producer of Gran Turismo and CEO of polyphony digital)
- It used asymmetric reinforcement learning which is the learning of robotic systems in a simulations which are later transferrable to real-world setups
- Actor-critic training method inside simulations
- course point information as global features. Course points are built using the shape of the track, including track limits of the left and right, and a center line of the track. At each time step, the range of the course points is a function of the current velocity of the vehicle: we consider the 3D relative coordinates of the course points ahead of the agent from 0.1 sec up to 6 sec ahead (maintaining the current velocity), equally spaced on 0.1 sec intervals. This results in 59 course points for each course line (left, center and right). 

- ##### ***Difficulties during planning the creation of sophy:***
	- Process high-dimensional sensor data to estimate the state of autonomous vehicles
	- Continuously plan optimal driving lines while avoiding obstacles and other vehicles
	- Control the vehicle while accounting for its nonlinear behavior and the conditions of the road

## There's alot more that i skipped taking notes on here. Refer the link below if later required




# References
[A Super-human Vision-based Reinforcement Learning Agent for Autonomous Racing in Gran Turismo](https://arxiv.org/pdf/2406.12563) 