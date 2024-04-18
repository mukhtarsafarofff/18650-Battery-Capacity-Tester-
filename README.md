Nowadays it is difficult to know the capacity retained in 18650 batteries and when we are buying , it is really difficult to distinguish between a real and fake battery .The whole schematic is divided into to followings sections:
1. Constant Current Load Circuit
2. Battery Voltage Measurement Circuit
3. User Interface Circuit
4. Buzzer Circuit

The power supply circuit consists of a DC Jack ( 7-9V) and two filter capacitors C1 and C2. The power output (Vin) is connected to the Arduino pin Vin. Here I am using the Arduino on-board voltage regulator to step down the voltage to 5V.
The main component of constant current load circuit is LM358 IC.LM358 is a dual amplifier in a single package.
This op-amp, R3, and the MOSFET build a constant current load circuit. When we set the voltage on the non-inverting input pin, the op-amp turns on the MOSFET and tries to get the same voltage across the R3. The Voltage appears due to the ohms law, as current flows through the resistor a voltage drop must appear. So I can control the current through the load resistor (R4) by changing the PWM signal pulse width.
The battery voltage is measured by the Arduino analog input pin A0. Two capacitors C1 and C2 are used to filter out the noises coming from the constant current load circuit which can degrade the ADC conversion performance.
The theory is based on the voltage comparison of the inverting (pin-2) and the non-inverting (pin-3) inputs of the OpAmp, configured as a unity amplifier. When I set the voltage applied to the non-inverting input by adjusting the PWM signal, the output of the opamp opens the gate of MOSFET. As the MOSFET turn-on, the current runs through R5, it creates a voltage drop, which provides negative feedback to OpAmp. It controls the MOSFET in such a way that the voltages at its inverting and non-inverting inputs are equal. So, the current through the load resistor is proportional to the voltage at the non-inverting input of the OpAmp. To calculate Battery Capacity, I use this equation: Battery Capacity (mAh) = Current ( I ) in mA x Time (T ) in Hours. The discharge current can be adjusted by pressing the Up and Down Button. The time duration is measured by using a timer in the Arduino code.
To test the circuit, i use  18650 battery and i have connected the battery to the battery terminal. Now set the current to according to your requirement and long-pressed the “UP” button. Then you should hear a beep and the test procedure starts. During the test, you will monitor all the parameters on the OLED display. The battery will discharge until its voltage reaches its low-level threshold (3.2V). The test process will be finished by two long beeps.

Heutzutage ist es schwierig zu wissen, welche Kapazität in 18650-Batterien erhalten geblieben ist, und beim Kauf ist es wirklich schwierig, zwischen echten und gefälschten Batterien zu unterscheiden. Das gesamte Schema ist in folgende Abschnitte unterteilt:
1)Konstanter Stromlastkreis
2)Batteriespannungsmesskreis
3)Benutzerschnittstellenkreis
4)Summerkreis

Die Batteriespannung wird über den Arduino-Analogeingangspin A0 gemessen. Zwei Kondensatoren C1 und C2 werden verwendet, um die von der konstanten Stromlastschaltung kommenden Störungen zu filtern, die die ADC-Konversionsleistung beeinträchtigen können.Die Theorie basiert auf dem Spannungsvergleich der invertierenden (Pin-2) und nicht-invertierenden (Pin-3) Eingänge des OpAmps, der als Einheitsverstärker konfiguriert ist. Wenn ich die Spannung am nicht-invertierenden Eingang durch Anpassen des PWM-Signals einstelle, öffnet der Ausgang des Operationsverstärkers das Tor des MOSFET.Wenn der MOSFET eingeschaltet wird, fließt der Strom durch R5, was eine Spannungsabnahme erzeugt, die dem Operationsverstärker eine negative Rückkopplung bietet.Es steuert den MOSFET so, dass die Spannungen an seinen invertierenden und nicht-invertierenden Eingängen gleich sind.
