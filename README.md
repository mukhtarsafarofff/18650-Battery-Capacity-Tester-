Nowadays it is difficult to know the capacity retained in 18650 batteries and when we are buying , it is really difficult to distinguish between a real and fake battery .The whole schematic is divided into to followings sections:
1. Constant Current Load Circuit
2. Battery Voltage Measurement Circuit
3. User Interface Circuit
4. Buzzer Circuit
The battery voltage is measured by the Arduino analog input pin A0. Two capacitors C1 and C2 are used to filter out the noises coming from the constant current load circuit which can degrade the ADC conversion performance.
The theory is based on the voltage comparison of the inverting (pin-2) and the non-inverting (pin-3) inputs of the OpAmp, configured as a unity amplifier. When I set the voltage applied to the non-inverting input by adjusting the PWM signal, the output of the opamp opens the gate of MOSFET. As the MOSFET turn-on, the current runs through R5, it creates a voltage drop, which provides negative feedback to OpAmp. It controls the MOSFET in such a way that the voltages at its inverting and non-inverting inputs are equal. So, the current through the load resistor is proportional to the voltage at the non-inverting input of the OpAmp. To calculate Battery Capacity, I use this equation: Battery Capacity (mAh) = Current ( I ) in mA x Time (T ) in Hours. The discharge current can be adjusted by pressing the Up and Down Button. The time duration is measured by using a timer in the Arduino code.
To test the circuit, i use  18650 battery and i have connected the battery to the battery terminal. Now set the current to according to your requirement and long-pressed the “UP” button. Then you should hear a beep and the test procedure starts. During the test, you will monitor all the parameters on the OLED display. The battery will discharge until its voltage reaches its low-level threshold (3.2V). The test process will be finished by two long beeps.

Heutzutage ist es schwierig, die Kapazität von 18650-Batterien zu ermitteln, und beim Kauf ist es wirklich schwierig, zwischen einer echten und einer gefälschten Batterie zu unterscheiden. Der gesamte Schaltplan ist in die folgenden Abschnitte unterteilt:
1.Konstantstrom-Lastkreis
2.Stromkreis zur Messung der Batteriespannung
3.Benutzerschnittstellenschaltung
4.Buzzerschaltung

Die Batteriespannung wird vom Arduino-Analogeingangspin A0 gemessen. Zwei Kondensatoren C1 und C2 werden verwendet, um die vom Konstantstrom-Lastkreis kommenden Störungen herauszufiltern, die die ADC-Umwandlungsleistung beeinträchtigen können. Die Theorie basiert auf dem Spannungsvergleich der invertierenden (Pin-2) und der nichtinvertierenden (Pin-3) Eingänge des OpAmp, konfiguriert als Einheitsverstärker. Wenn ich die an den nichtinvertierenden Eingang angelegte Spannung durch Anpassen des PWM-Signals einstelle, öffnet der Ausgang des Operationsverstärkers das Gate des MOSFET. Beim Einschalten des MOSFET fließt der Strom durch R5 und erzeugt einen Spannungsabfall, der für eine negative Rückkopplung zum Operationsverstärker sorgt. Er steuert den MOSFET so, dass die Spannungen an seinen invertierenden und nichtinvertierenden Eingängen gleich sind. Der Strom durch den Lastwiderstand ist also proportional zur Spannung am nichtinvertierenden Eingang des Operationsverstärkers. Um die Batteriekapazität zu berechnen, verwende ich diese Gleichung: Batteriekapazität (mAh) = Strom (I) in mA x Zeit (T) in Stunden. Der Entladestrom kann durch Drücken der Auf- und Ab-Taste eingestellt werden. Die Zeitdauer wird mithilfe eines Timers im Arduino-Code gemessen. Um die Schaltung zu testen, verwende ich eine 18650-Batterie und habe die Batterie an den Batteriepol angeschlossen. Stellen Sie nun den Strom entsprechend Ihren Anforderungen ein und drücken Sie lange auf die „UP“-Taste. Dann sollten Sie einen Piepton hören und der Testvorgang beginnt. Während des Tests überwachen Sie alle Parameter auf dem OLED-Display. Die Batterie wird entladen, bis ihre Spannung ihren niedrigen Schwellenwert (3,2 V) erreicht. Der Testvorgang wird durch zwei lange Pieptöne beendet.
