Nowadays it is difficult to know the capacity retained in 18650 batteries and when we are buying , it is really difficult to distinguish between a real and fake battery .The whole schematic is divided into to followings sections:
1. Constant Current Load Circuit
2. Battery Voltage Measurement Circuit
3. User Interface Circuit
4. Buzzer Circuit

The power supply circuit consists of a DC Jack ( 7-9V) and two filter capacitors C1 and C2. The power output (Vin) is connected to the Arduino pin Vin. Here I am using the Arduino on-board voltage regulator to step down the voltage to 5V.
The main component of constant current load circuit is LM358 IC.LM358 is a dual amplifier in a single package.
This op-amp, R3, and the MOSFET build a constant current load circuit. When we set the voltage on the non-inverting input pin, the op-amp turns on the MOSFET and tries to get the same voltage across the R3. The Voltage appears due to the ohms law, as current flows through the resistor a voltage drop must appear. So I can control the current through the load resistor (R4) by changing the PWM signal pulse width.
The battery voltage is measured by the Arduino analog input pin A0. Two capacitors C1 and C2 are used to filter out the noises coming from the constant current load circuit which can degrade the ADC conversion performance.The user interface circuit consists of two push buttons and a 0.96" I2C OLED display. The Up and Down push-button is to increase or decrease the PWM pulse width. R3 and R4 are pull-up resistors for the Up and Down push-buttons. C7 and C8 are used to debounce the push buttons. The third push-button (RST) is used for resetting the Arduino.The buzzer circuit is used to alert the starting and end of the test. A 5V buzzer is hooked to Arduino digital pin D9.The theory is based on the voltage comparison of the inverting (pin-2) and the non-inverting (pin-3) inputs of the OpAmp.When I set the voltage applied to the non-inverting input by adjusting the PWM signal, the output of the opamp opens the gate of MOSFET. As the MOSFET turn-on, the current runs through R1, it creates a voltage drop, which provides negative feedback to OpAmp. It controls the MOSFET in such a way that the voltages at its inverting and non-inverting inputs are equal.The PWM signal from the Arduino is filtered by using a low pass filter circuit ( R2 and C1).To calculate battery capacity i use this formule : Battery Capacity (mAh) = Current ( I ) in mA x Time (T ) in Hours
The discharge current can be adjusted by pressing the Up and Down Button. The time duration is measured by using a timer in the Arduino code.

Heutzutage ist es schwierig zu wissen, welche Kapazität in 18650-Batterien erhalten ist, und wenn wir kaufen, ist es wirklich schwer, zwischen einer echten und einer gefälschten Batterie zu unterscheiden. Das gesamte Schaltbild ist in folgende Abschnitte unterteilt:
1)Konstantstromlastschaltung
2)Batteriespannungsmesskreis
3)Benutzerschnittstellenkreis
4)Summer-Schaltung

Die Stromversorgungsschaltung besteht aus einer Gleichstrombuchse (7-9V) und zwei Filterkondensatoren C1 und C2. Die Leistungsausgabe (Vin) ist mit dem Arduino-Pin Vin verbunden. Hier verwende ich den eingebauten Spannungsregler des Arduino, um die Spannung auf 5V zu reduzieren. 
