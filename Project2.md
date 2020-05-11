###  Control Systems for Reinforcement Learning - Hexapod 

#### What is RL algorithm?

 * Reinforcement learning approach enables a computer to make a series of decisions to maximize the cumulative reward for the task without human intervention and without being explicitly programmed to achieve the task. The following diagram shows a general representation of a reinforcement learning scenario.
 
 ![image](https://in.mathworks.com/help/reinforcement-learning/ug/reinforcement_learning_diagram.png)
   
### How to get the data from IMU sensor?

 * An IMU, in general, consists of three sensors - accelerometer(measuring acceleration along 3 axis), gyrometer(angular velocity), magnetometer. Most of the IMU's(MPU6050,LSM9DS1) support both I2C and SPI hence it is possible to read the data from almost any microcontroller. The hardware assembly of an IMU to a microcontroller can be easily practised by referring to the corresponding datasheet of the IMU. After all the connections and assembly, the most significant part is programming the microcontroller to extract data from the IMU.
 
 * Many microntroller programming software(such as Arduino IDE) have an inbuilt library/software(__Wire Library__) that can directly output the acceleration and angular velocity on the screen without any additional math by the user. However, the way in which accelerometers deliver information depends upon whether it is a digital or an analog accelerometer.
 
 * Digital accelerometers will give you information using a serial protocol like I2C , SPI or USART, while analog accelerometers will output a voltage level within a predefined range that you have to convert to a digital value using an ADC (analog to digital converter) module. The formula to convert the voltage values into corresponding acceleration and angular velocity values can be found [here](https://engineering.stackexchange.com/questions/3348/calculating-pitch-yaw-and-roll-from-mag-acc-and-gyro-data). For detailed explanation of the math, visit [here](http://www.starlino.com/imu_guide.html).
 
 * Each leg will have 3 IMU's. Hence, in total our microcontroller(Arduino) would accept data from 18(3*6)* IMU sensors. However, our Arduino can send data between two devices only (Master-Arduino, Slave-IMU) through I2C communication over SDA pin(A4) and SCL pin(A5) of Arduino.
 
 * Hence to overcome such an issue, we can use an IMU that has SPI interface. With SPI, we can connect multiple devices on the same bus. They share data out(shown as SDO), data in(SDI), and clock(SCLK). Each device has its own chip select (CS) pin. In fact there is even an [Arduino library](https://www.arduino.cc/en/Reference/SPI) that supports SPI.
 
 * However in SPI interfacing, one major concern in the propogation delays and sometimes loss of synchronity with the clock pulse. The most commonly applied method is to loop back the master clock via a separate data line, which resembles the receive clock to provide synchronicity for the receive data sent by the slave. In transmit direction, the data sent by the master stay in synch with the master clock and can be easily read by the slave. In the opposite or receive direction, data sent by the slave traverse synchronously with the looped-back clock as both experience the same prop-delay through the isolator. Because both data streams, in transmit and receive, now possess their own clock to which they run synchronously, the data link is independent of propagation delay and clock speed and allows for maximum speed utilization. For more info, visit [here](https://www.electronicdesign.com/technologies/microcontrollers/article/21795651/isolate-your-highspeed-spi-bus-despite-long-propagation-delays).
   
   
 
 ### Analyzing the pipeline:
 
  * Our Hexapod consists of 18 Degrees of freedoms(DOF) i.e 3 DOF's for each of the six legs. In this project only three states are considered for each leg, hence total 729(3^6) states for the robot.  In every step, from every state of the agent, each action is rewarded and the rewards of speciﬁc state action is stored.
  
  * __Microcontroller selection__ - 
   Each serial connection (USB or RS232) can send and receive one signal over TX and RX of serial connection protocol. Therefore, to control our Hexapod, 18 serial connection would be required. However, this is not possible with regular Personal Computers or Laptops. 
   There are some boards which are compatible for controlling real-time like National Instruments products, but they are expensive to be  bought. One of the reasonable answers for connection challenge is to use a low level control architecture for tasks such as managing   transmitting and receiving signals.
   A board, which is an __AVR microcontroller ATmega2560__ base board ahould be used for low level control. It can control servo motors directly and also connect to a PC.
   
  * In order to __manage the wires__, we can create compartments or small hollow tubes for the wires from each leg to pass through. These 6 tubes would then open near the microcontroller where the connections can be made. We can even introduce a __Wifi module__ in our robot so that the data from the microcontroller can be directly sent over internet to our software wih RL algorithm. The processed data can again be sent to the microcontroller over internet thus eradicating the need of a __USB__ connection.
  
  
 
 
