# overvoltageprotection
Simple power supply overvoltage protection schematic<br>

Простая схема защиты от перенапряжения на выходе источника питания<br>

Use it to protect your devices from possible overvoltage due to power supply breakdown etc, or just improve reliability.<br>

<image src="https://github.com/dkorobkov/overvoltageprotection/blob/master/vold_prot.png" width="50%"><br>
 
Voltage sensor here is TL431 (use Zener diode if TL431 is not available but performance will be poor). Its trip voltage can be adjusted by 4.7k + 1k voltage divider (TL431 opens when "R" voltage is above 2.5V). Opening TL431 will open p-n-p transistor (any small signal transistor will do, e.g. BC856)  that will force closing MOSFET (normally open with 1k resistor in gate circuit). 15V zener diode prevents gate overvoltage.

When overvoltage disappears output is connected back

<font size="-1">This schematic is not ideal at voltages very (+-0.05V) close to TL431 trip voltage, as MOSFET will run in active mode with high power dissipation.</font>
