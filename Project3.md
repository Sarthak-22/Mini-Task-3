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
      
      
      
      




