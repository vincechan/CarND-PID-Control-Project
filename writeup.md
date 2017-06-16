# Project PID Controller
Implement a PID controller in C++ to maneuver the vehicle around the track.

[Link to my video result](https://www.youtube.com/watch?v=nHmbRRNDAdE)

## Describe the effect each of the P, I, D components had in your implementation.
In a PID controller, 
The P stands for Propotional. In this project, the P term ensures the vechicle will steer in propotion and opposite direction of the CTE.
The D stands for Derivative. It's the derivative of the current cte and previous cte over time. In this project, the D term smooth out the steering angle. Without the D term, the vehicle will oscillate around the center line, makes for a very uncomfortable car ride.
The I stands for Integration. The I term compensate for any bias from the measurements.


## Describe how the final hyperparameters were chosen.
The hyperparameters were chosen manually. I would update the parameters in code, observe the effects the simulator, and updates the parameters again until I found a good combination. 

First I kept D term and I term at zero. I did this to try to find a P gain that's sufficiently large to make the turns on the track.
I gradually increased the P term from 0.1. Once it saw that it could pass the first turn. I started turning D. I gradually increased it from 1.0 until I saw that the car can drive around the track without too much oscillation. 
Finally I updated I term to 0.0001.

The final gains are Kp=0.15, Kd=1.5, Ki=0.0001
