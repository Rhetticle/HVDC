# HVDC
High voltage DC arc lighter.

<p align="center">
  <img src="https://github.com/user-attachments/assets/4d2319c3-6aa8-4cce-ae9e-dd437b6fd366" />
  <img src="https://github.com/user-attachments/assets/eb917cba-2236-466e-8909-7de6da60f22f" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/e6325b4b-46be-4e89-8dd3-874a035f4fce" width=480>
</p>

# Topology
HVDC uses a spark-gap style method of arc generation. The two 1uF 1.3kV capacitors are charged until around 600V at which point the 600V gas discharge tube breaks down and the capacitor energy is dumped into the final output transformer primary to generate a high voltage arc on the secondary. 

The first transformer is used to step up the 7.4V supply voltage to 1kV to charge the capacitors. This transformer is driven by a full H-bridge at a 50% duty cycle. Two sqaure wave gate signals are generated by an STM32 microcontroller and two half-bridge gate drivers are used to provide fast switching speeds on the MOSFETs.

HVDC also features a completely embedded battery charging/management system to charge the 2S Lipo battery directly from a micro USB cable.

# Hardware Details
* Microcontroller - STM32C011J6M6 (SOIC8)
* Gate Drivers (Half Bridge) - ADP3110AKRZ-RL (SOIC8)
* Battery Charger - BQ25306RTER (16-WQFN)
