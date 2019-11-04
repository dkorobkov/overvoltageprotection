# overvoltageprotection
Simple DC power supply overvoltage protection schematic<br>

Простая схема защиты от перенапряжения на выходе источника питания постоянного тока<br>

Use it to protect your devices from possible overvoltage due to power supply breakdown etc, or just improve reliability.<br>

<image src="https://github.com/dkorobkov/overvoltageprotection/blob/master/volt_prot.png" width="50%"><br>
 
Voltage sensor here is TL431 (use Zener diode if TL431 is not available but performance will be poor). Its trip voltage can be adjusted by 4.7k + 1k voltage divider (TL431 opens when "R" voltage is above 2.5V). Opening TL431 will open p-n-p transistor (any small signal transistor will do, e.g. BC856)  that will force closing MOSFET (normally open with 1k resistor in gate circuit). Base resistor (100 Ohm) increases switching slope and prevents MOSFET from going in active operation mode (i.e. become hot and burn out)

15V zener diode prevents gate overvoltage. It is not needed if protection trip voltage is set up below 15-17V because at higher input voltages transistor will open and tie gate to source.

Maximum allowed TL431 current is 100 mA, recommended is 10-20 mA. Adjust 510 Ohm accordingly and consider its power dissipation (0.125W SMD0805 can easily burn out)

Voltage drop on IRF9530 is approx. 0.4V so it can dissipate 1-3W and become hot with high current loads.

When overvoltage disappears output is connected back.

This schematic is not ideal at voltages very (+-0.05V) close to TL431 trip voltage, as MOSFET will run in active mode with high power dissipation.
