Nowadays it is difficult to know the capacity retained in 18650 batteries and when we are buying , it is really difficult to distinguish between a real and fake battery .The whole schematic is divided into to followings sections:
1. Constant Current Load Circuit
2. Battery Voltage Measurement Circuit
3. User Interface Circuit
4. Buzzer Circuit
The battery voltage is measured by the Arduino analog input pin A0. Two capacitors C1 and C2 are used to filter out the noises coming from the constant current load circuit which can degrade the ADC conversion performance.
The theory is based on the voltage comparison of the inverting (pin-2) and the non-inverting (pin-3) inputs of the OpAmp, configured as a unity amplifier. When we set the voltage applied to the non-inverting input by adjusting the PWM signal, the output of the opamp opens the gate of MOSFET. As the MOSFET turn-on, the current runs through R5, it creates a voltage drop, which provides negative feedback to OpAmp. It controls the MOSFET in such a way that the voltages at its inverting and non-inverting inputs are equal. So, the current through the load resistor is proportional to the voltage at the non-inverting input of the OpAmp.
