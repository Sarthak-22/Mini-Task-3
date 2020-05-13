### MicroMouse Maze

 * __Problem Statement__ :- An autonomous, self contained robot(__Micromouse__) is to be built which can get to the centre of the maze in shortest possible time.
 
 * __Ideation__ :- 
 
      __Hardware overview__ - ESP32 is used as the micocontroller. Three sensors i.e 1 ultrasonic distance sensor, 2 TOF sensors at two sides are attached for getting wall data. Motors with rotary encoder, a power supply, chassis, jumper wires are some other required components.
      
      __Software overview__ - Arduino IDE, maze solving algorithm i.e floodfill algorithm and PID algorithm.
      
      Upload the code => Provide power supply => get data from sensors => feed it into the algorithm => provide output data to the encoded motors => get data from sensors => .....
      
      Hardware/Software components | Feasibilty | Advantages | Disadvantages 
      -----------------------------|------------|------------|--------------
      ESP 32 | Beginner friendly as the code Arduino IDE | In-built WiFi, bluetooth module. Powerful 32 bits CPU to store memory | Relatively costlier(almost two times the cost of module)
      Sensors | Cheap and easily available | Simple and compact. No moving parts and built-in illumination adjacent to the lens. Small amount of processing power is used. | It needs to be optimised continously for electronic devices |
      Arduino IDE code | Open source and easy to code for beginners | Contains many in-built libraries. ESP32 can be installed as an add-on in Arduino IDE | |
      
      * __Programming software__ - Although Arduino IDE is an easy-to-program language, coding the same in python is quite beneficial and powerful to implement complex algorithms. Python has quite an easy syntax thus making it easy for beginners. Many microcontrollers(including ESP32) extensively support Python as a programming tool. A middleware named __Zenith__ provides developers with an ecosystem of software tools for programming microcontrollers using Python and then connect them to the Cloud. A deatiled information on setting up Python programming with microcontroller ESP32 can be found [here](https://www.open-electronics.org/python-on-esp32-easy-for-beginners-powerful-for-professionals/).
      
      * __Sensors__ -  Instead of using 1 distance sensor and 2 TOF sensor, we can use __3 distance sensors__(front,left,right) alltogether. A distance sensor can calculate the distance of the nearest obstacle. Hence, we can program our microcontroller in such a way that if the distance of any obstacle is less than a certain threshold distance, update the __wall data__ in the algorithm. Although Tof sensor is much faster, has a greater accuracy and good range but when it comes to a maze-solving robot, ultrasonic sensor and TOF sensor perform almost the same operation with almost the same precision. The main advantage is that an ultrasonic sensor costs less than half the price of TOF sensor. This will help optimize our budget for other remaining equipments.
      
      * __Design__ -  While making the model of micromouse, the mechanical design should be consider as a major concern. In any model of micromouse, the main purpose of the chassis of the micromouse is to move smoothly and clearly between the paths of maze without collapse. Hence, according to me, the base frame of the robot can be constructed out of a circular disk. The circular base only needs to turn in place. A circular base occupies a relatively smaller amount of space as compared to many other design shapes.
      
      * The components will be mounted in a layered support system. This will provide a way for subsystems to be mounted and removed easily without interfering with the other systems. A layered mounting system provides a way to easily add and remove subsystems independently. The structure of the robot can be built with plastic sheets in order to decrease the overall weight of the robot. 
      
      * __Motors/Encoders__ -  A DC motor with encoders(preferably __N20 6V 100RPM Micro Metal Gear Motor With Encoder__). This motors are small and quite light as compared to stepper motors. The electronics is fairly simple provides with optimal power supply. The motor is also provided with inbuilt encoder which is quite useful to provide encoded data about the rotation of wheels to our program. Though stepper motors are good for speed, they are quite heavy, power hungry and need relatively heavy duty driving electronics. 
      
      * __Power Supply__ - A 520mAh 7.4V Li-po battery can be used as a source of power for the motors and control system. It offers high capacity and hence can be used to hold more power. It is rechargeable and safe from explosion unlike other Li-ion battery. 
      
      
     
Some __research papers__ based on Micromouse assembly and implementation of Flood-fill algorithm can be found here - 

[Research Paper1](https://www.researchgate.net/publication/319943074_Optimization_Maze_Robot_Using_A_and_Flood_Fill_Algorithm)

[Research paper2](https://pdfs.semanticscholar.org/7a3b/a96296fe54e2fc82030e2c5375299cfbe9c9.pdf?_ga=2.14211703.1111116604.1589368847-600967904.1589368847)
      
      
      




