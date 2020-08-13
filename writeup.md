# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program

---

## Project reflection
#### Describe the effect each of the P, I, D components had in your implementation.

The proportional (P) controller is to instantly generate a control signal that corrects the feedback error signal. There is no delay between input and output. The output signal is proportional to the magnitude of the input signal. 

The integral (I) part is used to correct the residual error. Due to the nature of P controller, it needs the existence of small error to generate the control output. By having I controller that sums the previous errors, the small residual error can be eliminated.

The derivative (D) controller is used to improve the response speed and reduce overshoot. It is proportional to the difference between the previous two error values. 

#### Describe how the final hyperparameters were chosen.

The PID coefficients were selected by manual tuning in this project. I started with Kp by gradually increasing it until the car started to oscillate around the lane center. After doing this step, the car has some ability to follow the lane. 

I then added a small Ki to remove the residual error. It actually did not impact much in this project since the car is always in a dynamic balance state. So I ended up with a small Ki value, just to remove the error if it persists.

The Kd parameter is important to improve the controller's response speed and also reduce overshoot. I found it very helpful in making the car drive through the turns. Without Kd, the car constantly ran out of the road when there was an abrupt turning. With Kd, the car was able to make very smooth turns.

The final PID values I selected are listed below:

Kp = 0.15

Ki = 0.00001

Kd = 3.0

