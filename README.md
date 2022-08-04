# HumidF

Objective
I have dipped my toes into making small arduino weather stations before, but they have generally ended up either too bulky or having the sensor and microcontroller part completely reliant on a computer host. Having spent a bit of time at a local hobby electronics lab, I realized it would be possible to make them much smaller, cheaper and independent if you use a smaller, cheaper development board with built in WiFi instead of an arduino uno. 

The purpose of this project is in part to make a very cheap and portable weather station, and in part to create a proof of concept using a very small chip with on board wifi directly connected to some form of sensor that can send the sensor readings directly to a REST API over the internet. This first prototype will be used to monitor temperature and humidity indoors on my computer desk. 

Material
Having looked around at the offering of wifi-enabled development boards at my makerspace, I found the esp8622 boards to be the best fit for this project. A d1 mini costs maybe 20-50 SEK depending on the store (about 30 at my makerspace) and is roughly the size of your thumb. I opted for a more capable (and thus more expensive, but still significantly less than the arduino uno with a wifi extension) board, the NodeMCU. The NodeMCU carries an ESP8622 (ESP-12) wifi microcontroller, allowing for wifi communication without any extensions, and has 9 general purpose IO pins, as well as 2 3,3V pins, a 5V pin and a whole bunch of extra features that we will not be using today. All of this goes for 50 SEK at my makerspace, or 59 at Lawicel. You might have to pay a lot more at other, more popular retailers, but still a lot less than a lopy4, a raspberry pi 3 or 4, and even a lot less than the budget option of an arduino uno with a wifi shield. 

Connected to the NodeMCU will be a DHT-11 temperature and humidity sensor. It's not the most accurate or precise sensor, and it can't be polled very often, but it fits our rather basic needs well, and has libraries that support it on multiple architectures (including the ESP8622). 

Computer setup

A nice thing about the ESP8622 series boards is that the open source community has provided a large number of libraries as well as Arduino IDE support for all popular boards using the architecture, as well as the generic processor itself. What we're going to have to do first is download the arduino IDE and then add ESP8622 support to it. 
