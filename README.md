# Sigrok-USB-PD-CC-line-captures
Several captures of USB PD protocol captures of the CC line during sync

I designed an enclosure for an DPS3005 mini PSU to mount it directly on top of a Bosch 18V battery. 
You can find this enclosure in my repo. Having already done this work, i wanted also to charge a Laptop. 
For that, a bigger battery was needed. I have an ebike with a 36V (up to 40V fully charged). I found this nice project
https://www.pedelecforum.de/forum/index.php?threads/use-bosch-e-bike-battery-as-power-bank.111511/ and tested it with a DPS5005 mini PSU.
Worked great. The problem was an additional UCB-C port for charging a Laptop. The DC-DC converter from the project mentioned above did not trigger 
my Microsoft Surface Laptop Studio 2 Laptop (SLS2). 
I bought an USB USB PD 3.1 trigger board and tried an additional DC-DC converter connected to the USB-PD 3.1 trigger board. It initially worked, 
but after some seconds, the power breaks down and it reconnected. 

To find out the problem, i dived into the USB communication. It uses the USB PD protocoll. 
I hooked up my Hantek 4032L logic analyzer to the D+, D-, CC1 and CC2 lines and used sigrok with pulseview to inspect the data.
All the communication was on the CC1 line (Pin A5). I did some tests with some devices.

Power-Source was:
* Bosch ebike battery from my small project
* Pine-Power charger
* INIU-B63 Powerbank

My DUT were:
* Microsoft Surface Laptop Studio 2
* Fujitsu-Lifebook Laptop
* Sony Xperia 10 III Smartphone (with SailfishOS) 
* Flipper Zero
* LiteVNA
* ES15 electric screw driver

Maybe someone find this files helpfull.


## View
<p align="center">
<img src="ViewCapture20250112_113516.png" width="250"> 
<img src="IMG_20241114_202705.jpg" width="220"> 
<img src="IMG_20241114_202520.jpg" width="220">
</p>
<p align="center">
<img src="PD_sync.png" width="220">
<img src="PD_sync3_startsequence.png" width="220">
<img src="pulseview_KvjTKqyQQ7.png" width="220">
</p>  

