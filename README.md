# Ultrasonic Sensor-Based Parking Assist System

**Course:** EE 615 Embedded Systems Lab 

**Instructor:** Prof. Abhijit Kshirsagar

**Group 02 Members:**  
1. Ganesh Panduranga Karamsetty - 210020009  
2. Rishabh Pomaje - 210020036  

---
### Project Plan

- Use the **TI TM4C123GH6PM microcontroller** to read and operate two ultrasonic sensors.
- Output the distance readings to the OLED SSD1306 (128 * 64) via I2C interface.
- Use on-board led and implement color signalling.
- The two sensors, corresponding to the front and rear sensors in a car will be operated depending on which switch is pressed. Analogous to whether the car is in forward gear or reverse gear. 
---

## Project Description

This system is based on the **Tiva C series TM4C123G LaunchPad** evaluation kit. Using ultrasonic sensors, we can measure distances to detect obstacles.

### Overview of Ultrasonic Sensor (US)

An ultrasonic sensor board, as shown in Figure 1a, consists of a **Transmitter** and a **Receiver**:

- **Transmitter:** Sends an ultrasonic pulse of short duration.
- **Pulse Reflection:** The pulse travels until it encounters an obstacle and reflects back.
- **Receiver:** Waits for the reflected pulse.

The board interfaces with the microcontroller using two signal pins, `Trig` and `Echo`.

### Distance Measurement

1. Send a signal and start the timer.
2. Wait for the reflected signal.
3. Once received, check the elapsed time.
4. Calculate the distance using the formula:

    $$\text{distance} (d) = \text{speed} (s) \times \text{time elapsed} (t)$$

   where  
   -  $d$ is the distance traversed by the pulse (i.e., twice the required distance).
   - $s$ is the speed of sound, approximately 343 m/s at $20^\degree$.

5. This yields the required distance.
![Distance calculation diagram](Images/exp01.svg)


## System Block Diagrams

### Hardware Block Diagram
![Hardware Block Diagram](Images/hardware_bl.svg)

### Software Block Diagram
![Software Block Diagram](Images/software.svg)

---
### NOTE: The OLED driver/ library has been designed by us from scratch with a bit of reverse engineering and referring to the datasheet. Hence, I strongly suggest you use the functions implemented in it with care as they are very much in developmental stage.
---

## Materials and Datasheets

| Material | Link to Datasheet |
|----------|-------------------| 
|Tiva C series TM4C123G LaunchPad | [TM4C123GH6PM Datasheet](https://www.ti.com/product/TM4C123GH6PM) |
| HC-SR04 | [HC-SR04 User Manual](https://robu.in/wp-content/uploads/2014/08/edited_HC-SR04-User-Manual-1.pdf) |
| 0.96in OLED with SSD1306 driver (128×64) | [SSD1306 Datasheet](https://cdn-shop.adafruit.com/datasheets/SSD1306.pdf) | 

---

## Timeline

| Date       | Milestone Reached |
|------------|--------------------------|
| 29/10/2024 | <font color='lime'>Initial plan formulation |
| 12/11/2024 | <font color='lime'>Able to detect and sense the distance using one US. |
| 14/11/2024 | <font color='lime'>Calibration of the distance |
| 15/11/2024 | <font color='lime'>Outputting the distance to PC monitor through UART serial|
| 17/11/2024 | <font color='lime'>Integrate another sensor for the front | 
| 28/11/2024 | <font color='lime'> Output distance to OLED

---

## Demo
Here is a demo picture of the system:

![Demo Picture](Images/demo_pic.jpg?raw=true)

And here is the demo video:

![Demo Video](Images/demo_movie.mp4?raw=true)
