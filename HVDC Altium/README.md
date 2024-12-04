# HVDC Altium

The PCB used in HVDC was created in Altium Designer and manufactured by JLCPCB. The PCB is a standard 2 layer board 1.6mm thick.

![Screenshot 2024-12-04 212654](https://github.com/user-attachments/assets/55a185a0-9e4b-49bb-ad43-8e8f97a08705)
![Screenshot 2024-12-04 212714](https://github.com/user-attachments/assets/f2bef82e-639f-4aed-b85c-73deb648c851)

# PCB
This PCB has a plane on top for the 7.4V rail and a ground plane on the bottom layer. Note that the power plane does not extend past the charging transformer in order to reduce switching noise being induced into the plane.

As this design mixes high voltage pulses and digital electronics, lots of decoupling was needed. Extra decoupling capacitors were added to the STM32, gate drivers, 3V3 LDO regulator and battery charger to ensure all voltage supply rails remain relatively stable while the device is in use. There is also an array of 8 1uF shunt capacitors to shunt the kickback from the charging transformer primary from putting too much noise onto the main 7.4V rail (During operation this rail was measured to have around 800mV peak ripple). Note this array is placed as close a possible to the transformer primary coil.

Two 1M ohm 1W bleed resistors are present in order to ensure the capacitors are always discharged when the device is not in operation and prevents capacitors from being partially charged from previous use.
