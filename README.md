# MouseJack
All the details and steps needed to perform mousejacking with or without Autojack.


Mousejacking is class vulnerabilies that was discovered in 2016 by researchers at Bastille. Mousejacking is an often over looked method of gaining a foothold in a network. All the specifics about the findings including a technical write up can be found at Bastilles website. 
https://www.bastille.net/research/vulnerabilities/mousejack/ 

In order to exploit these vulnerabilities you will need to acquire a Crazyradio PA dongle
https://store.bitcraze.io/products/crazyradio-pa 

Then you will need to re-flash the dongle firmware using the tools provided by Bastille and following the directions they provide here. 
https://github.com/BastilleResearch/mousejack 

Once the dongle has been flashed you can use the tool "Jackit" to begin scanning for vulnerable devices and injecting rogue keystrokes into your targets. 
https://github.com/insecurityofthings/jackit#how

Jackit injection is done using classic Ducky Script. Details on how to use Ducky Script can be found here
https://github.com/hak5darren/USB-Rubber-Ducky/wiki/Duckyscript 

Once everything is configured you can automate the scanning and injection process by running AutoJack, making sure the payload path and file match yours.

There seems to be an issue on ARM devices where the USB dongle gets hung, preventing successive scans. To fix this without having to physically remove the dongle I created the USBreset script. Autojack takes care of scanning, injecting the payload on all targets, and then resetting the USB, all without user interaction. 

NOTE: there are some drawbacks to this type of attack. Keystrokes can get lost, mistyped, or stuck causing payloads to incorrectly execute. The target will see keystrokes being typed on their device which could cause suspicion. 
