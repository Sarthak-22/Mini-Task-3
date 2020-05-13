### Project 1 - THE LIGHTING RING

__Problem statement__ - To build an electronic lighting ring that glows when worn and stops glowing when the ring is removed.


 __Ideation__- 
    
   * __Ring Design__ - The ring should be much broader in width for the microcomponents and our circuit as a whole to fit inside it. It should be made of a non-insuating material such as plastic, wax pattern or epoxy resin mould etc. Such designs/bodies are readily available in local stores. Hence, we can choose the design as per our desire.
   
  ![image](https://cdn.instructables.com/FGH/E4X8/GYZNVLNT/FGHE4X8GYZNVLNT.LARGE.jpg?auto=webp&width=1024&height=1024&fit=bounds)
   
   * __Microcontroller__ - The most important constraint while choosing an appropriate microcontroller is its size. Along with size, power consumption is also equally important. Hence, we need a microcontroller which is small in size and has power-saving abilities (sleep mode). Two microcontrollers that satisfy the above constraints is [MPC5668x](https://www.nxp.com/docs/en/data-sheet/MPC5668x.pdf) and [ATtiny45](https://ww1.microchip.com/downloads/en/DeviceDoc/Atmel-2586-AVR-8-bit-Microcontroller-ATtiny25-ATtiny45-ATtiny85_Datasheet.pdf). ATtiny microcontrollers has an operating voltage of 3V and is optimal with the current power supply availability.
   
   * __Resistive Pressure Sensor__ - A Resistive pressure sensors utilise the change in electrical resistance of a strain gauge bonded to the diaphragm that’s exposed to the pressure medium. This FSR will vary its resistance depending on how much pressure is being applied to the sensing area. The harder the force, the lower the resistance. When no pressure is being applied to the FSR its resistance will be larger than 1MΩ. This FSR can sense applied force anywhere in the range of 100g-10kg. This sensor is incredibly tiny with a diameter of 0.5". Hence it can be easily fit in the inner body of the ring where pressure varies as and when the ring is worn. Its even quite robust, cost-effective and easily customizable to a wide range of sizes as small as 0.45 mm.
   
   ![image](https://robu.in/wp-content/uploads/2016/03/Force-Sensor-Resistor-2.jpg)
   
   [Resistive Pressure Sensor](https://robu.in/product/force-sensor-resistor-0-5-14-7mm-pressure-sensor/?gclid=CjwKCAjwte71BRBCEiwAU_V9h5SKFv9LzttXfopvdy0LTAGSVNXXxhpdUok4hmWbfyltbIdZquBoCRoCmUMQAvD_BwE)
 
   * __Power Supply Source__ - Since the operating voltage of our microcontroller is around 3V, we can use 2 coin cell battery each of 1.5V rating in series. Also, most of the LED ratings are between 1.2-3.6V making a 3V supply more advatageous. Coin cell batteries are the smallest source of power and hence can easily fit inside a ring.
   
   * __Circuit assembly and programming__ - All the components of the circuit i.e sensors, resistors,capacitors(if any), LED and MCU pins should be directly soldered to avoid unnecesary usage of wires. The MCU pin connections can be made by referring to datasheet. ATtiny 45 can be easily pre-programmed with an Arduino using the __ATtiny core files__ in "Arduino ISP" sketch. The MCU can be programmed in such a way that when the ring is worn i.e when the pressure is high hence resitance low, the LED glows and when the ring is removed, the LED stops glowing. 
  
  * In order to further decrease the size of our circuit, instead of a normal LED, a 20mA microchip LED can be used as a source of light. A microchip LED is very bright for its small size and is available at subsidised rates.
