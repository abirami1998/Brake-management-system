# Brake-management-system
Model flow:
Subsystem1:
•	The difference between the desired relative slip and the actual relative slip is provided as input for calculation of wheel speed.
•	The actual relative slip is calculated by using the wheel speed and the vehicle speed and the following relation 1-(Wheel speed)/(vehicle speed)
•	The frictional force between the runway and the wheel is calculated as the product of the weight of the vehicle and the coefficient of friction of the obtained from the mu-slip curve.
•	A manual switch is used to toggle between the friction values of a wet runway and a dry runway.
•	The frictional force thus obtained is multiplied with the tyre radius to obtain the tyre torque.
•	This force is divided by the vehicle mass and integrated to obtain the vehicle speed
Sum of forces:
The following forces are added:
•	Sum of frictional forces experienced by both the wheels
•	Thrust of the aircraft
•	Drag / Air resistance
•	Friction of the brake pads which is obtained from a hydraulic subsystem*
The combined effect of these forces is provided to the 6 degrees of freedom block whose output is the body velocity which is then integrated to obtain the stopping distance.
*Hydraulic Subsystem:
•	This system takes the duty cycle as the input and gives hydraulic pressure as the output
•	The duty cycle provided is used to generate width modulated pulses.
•	A variable displacement pump is used to pump up fluid from the reservoir.
•	The shaft speed of the pump is controlled by a velocity source which takes in pump speed as an input
•	The PWM generated is used to control the flow of the fluid in the valve.
•	A pressure sensor reads the pressure generated from the pump and gives it as the output.






















Simulink Model:
![image](https://user-images.githubusercontent.com/59002417/110895225-53516480-831f-11eb-8d74-2fb6633a5af1.png)

 



Subsystem:
 ![image](https://user-images.githubusercontent.com/59002417/110895196-47fe3900-831f-11eb-8470-f8eb7dcae4eb.png)

Hydraulic Subsystem:
![image](https://user-images.githubusercontent.com/59002417/110895255-6106ea00-831f-11eb-8567-e3804f2522af.png)

 
Wheel Subsystem:
![image](https://user-images.githubusercontent.com/59002417/110895269-695f2500-831f-11eb-8bdd-07dcdf38869b.png)

 

Output plots:
mu-slip curve:
![image](https://user-images.githubusercontent.com/59002417/110895296-7845d780-831f-11eb-8e29-1699417743f7.png)

 







Wet Runway Characteristics:
![image](https://user-images.githubusercontent.com/59002417/110895310-8136a900-831f-11eb-8ad5-66603f23bc80.png)

 
Dry runway Characteristics:
 ![image](https://user-images.githubusercontent.com/59002417/110895324-885db700-831f-11eb-981f-7a953e270ce5.png)



Inference:  
From the above plots we infer that the stopping distance and the time taken for the aircraft to stop is majorly dependent on the physical condition of the runway.
Wet runway:
Relative slip=0.2
Stopping distance	390.5m
Stopping time	10.37s

Relative slip=0.6
Stopping distance	403.8m
Stopping time	10.7s



Dry runway:
Relative slip=0.2
Stopping distance	227m
Stopping time	6.64s

Relative slip=0.6
Stopping distance	237m
Stopping time	6.64s




Conclusion: 
From this it is concluded that for an aircraft to operate effectively, an efficient braking system is of utmost vitality. The combined effect of hydraulic brakes, spoilers and drag contribute to the effectiveness of the braking system.
It is observed that to obtain optimal stopping distance ( <700 m) the nature of the runway which the aircraft uses decides the amount friction acting on the wheels thereby directly affecting the stopping distance and the stopping time.
The above model can be deployed in ranges with short runways like in aircraft carriers.  The scope of this model can be further extended to accommodate  pneumatic brakes to avoid fluid losses prevalent in hydraulic models.
