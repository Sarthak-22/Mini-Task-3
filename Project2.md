###  Control Systems for Reinforcement Learning - Hexapod 

#### What is RL algorithm?

 * Reinforcement learning approach enables a computer to make a series of decisions to maximize the cumulative reward for the task without human intervention and without being explicitly programmed to achieve the task. The following diagram shows a general representation of a reinforcement learning scenario.
 
 ![image](https://in.mathworks.com/help/reinforcement-learning/ug/reinforcement_learning_diagram.png)
 
  The goal of reinforcement learning is to train an agent to complete a task within an unknown environment. The agent receives observations and a reward from the environment and sends actions to the environment. In other words, reinforcement learning involves an agent learning the optimal behavior through repeated trial-and-error interactions with the environment without human involvement.
  
### How to get the data from IMU sensor?

 * An IMU, in general, consists of three sensors - accelerometer(measuring acceleration along 3 axis), gyrometer(angular velocity), magnetometer. Most of the IMU's(MPU6050,LSM9DS1) support both I2C and SPI hence it is possible to read the data from almost any microcontroller. The hardware assembly of an IMU to a microcontroller can be easily practised by referring to the corresponding datasheet of the IMU. After all the connections and assembly, the most significant part is programming the microcontroller to extract data from the IMU.
 
 * Many microntroller programming software(such as Arduino IDE) have an inbuilt library/software that can directly output the acceleration and angular velocity on the screen without any additional math by the user. However, the way in which accelerometers deliver information depends upon whether it is a digital or an analog accelerometer.
 
 * Digital accelerometers will give you information using a serial protocol like I2C , SPI or USART, while analog accelerometers will output a voltage level within a predefined range that you have to convert to a digital value using an ADC (analog to digital converter) module. The formula to convert the voltage values into corresponding acceleration and angular velocity values can be found [here](https://engineering.stackexchange.com/questions/3348/calculating-pitch-yaw-and-roll-from-mag-acc-and-gyro-data). For detailed explanation of the math, visit [here](http://www.starlino.com/imu_guide.html).
 
 
