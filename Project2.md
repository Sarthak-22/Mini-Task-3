###  Control Systems for Reinforcement Learning - Hexapod 

#### What is RL algorithm?

 * Reinforcement learning approach enables a computer to make a series of decisions to maximize the cumulative reward for the task without human intervention and without being explicitly programmed to achieve the task. The following diagram shows a general representation of a reinforcement learning scenario.
 
 ![image](https://in.mathworks.com/help/reinforcement-learning/ug/reinforcement_learning_diagram.png)
   
### How to get the data from IMU sensor?

 * An IMU, in general, consists of three sensors - accelerometer(measuring acceleration along 3 axis), gyrometer(angular velocity), magnetometer. Most of the IMU's(MPU6050,LSM9DS1) support both I2C and SPI hence it is possible to read the data from almost any microcontroller. The hardware assembly of an IMU to a microcontroller can be easily practised by referring to the corresponding datasheet of the IMU. After all the connections and assembly, the most significant part is programming the microcontroller to extract data from the IMU.
 
 * Many microntroller programming software(such as Arduino IDE) have an inbuilt library/software that can directly output the acceleration and angular velocity on the screen without any additional math by the user. However, the way in which accelerometers deliver information depends upon whether it is a digital or an analog accelerometer.
 
 * Digital accelerometers will give you information using a serial protocol like I2C , SPI or USART, while analog accelerometers will output a voltage level within a predefined range that you have to convert to a digital value using an ADC (analog to digital converter) module. The formula to convert the voltage values into corresponding acceleration and angular velocity values can be found [here](https://engineering.stackexchange.com/questions/3348/calculating-pitch-yaw-and-roll-from-mag-acc-and-gyro-data). For detailed explanation of the math, visit [here](http://www.starlino.com/imu_guide.html).
 
 ### Analyzing the pipeline:
 
  * Our Hexapod consists of 18 Degrees of freedoms(DOF) i.e 3 DOF's for each of the six legs. In this project only three states are considered for each leg, hence total 729(3^6) states for the robot.  In every step, from every state of the agent, each action is rewarded and the rewards of speciﬁc state action is stored.
  
  * __Microcontroller selection__ - 
   Each serial connection (USB or RS232) can send and receive one signal over TX and RX of serial connection protocol. Therefore, to control our Hexapod, 18 serial connection would be required. However, this is not possible with regular Personal Computers or Laptops. 
   There are some boards which are compatible for controlling real-time like National Instruments products, but they are expensive to be  bought. One of the reasonable answers for connection challenge is to use a low level control architecture for tasks such as managing   transmitting and receiving signals.
   A board, which is an __AVR microcontroller ATmega2560__ base board ahould be used for low level control. It can control servo motors directly and also connect to a PC.
   
  * 
  
  
 
 
