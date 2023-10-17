This is for a project to "fix" a $12 generic 3rd brake light I found on eBay.

This device has a control module that takes 12v + gnd and has 4 other 12v inputs to play animmations.

|  The animations are: |   
| --- |
| Running lights (has constantly blinking center for some reason) |
| Brake light (has 2s turn off animation that slowly goes to half brightness from the outside in, then to 0 brightness from the outside in) |
| sequential left turn | 
| sequential right turn | 
| Emergency lights, flows from center to either side (connect both turn signal wires to activate) | 

Most of them suck, especially the brake light one.

I tore down the strip to understand how it's communicating and found it's driven by CC16703 chips. These can be driven as WS2811 addressable led drivers but take 6-12v power input. The logic level is still 5v. 

The LED layout has each addressed "pixel" having 3 subpixels, though all LEDs are red. The subpixels are wired such that from the feed of the string, the first 3 leds are driven in series as the Blue subpixel, the next 3 LEDs are drives as Green, then the next 3 as Red. This repeats for 16 total "pixels", 48 addressable portions of the string, 144 total LEDs.


![pic](https://github.com/illiteratebeef/Generic-ebay-3rd-Brake-Arduinoization/blob/master/IMG_20190920_225231.jpg?raw=true)
![pic](https://github.com/illiteratebeef/Generic-ebay-3rd-Brake-Arduinoization/blob/master/IMG_20190920_231013.jpg?raw=true)
![pic](https://github.com/illiteratebeef/Generic-ebay-3rd-Brake-Arduinoization/blob/master/IMG_20191002_181819.jpg?raw=true)
