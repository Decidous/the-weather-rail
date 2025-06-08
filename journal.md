## May 30: Brainstorming
Log-01: 3.5 hours

Members: Decidous, Evan

The overall idea was to build a weather station. At first, we thought mini hot-air balloons would work. It's possible, but we'd have to create the envelope (gores & panels) of the balloon from scratch. The second complication is that hot air balloons would interefere with no-fly-zones near airports. We'd have to drive to a remote area to conduct flying tests.

Enter: Phase II of planning. While we may not be able to get the same type of data as a weather balloon, we can definitely calculate some interesting stuff at a shorter height. Our idea is to construct a tower out of five 1 inch 6ft PVC pipes. Then, we'd secure it with guylines and stakes at two levels, each having 3 guylines. 

## May 31: Research
Log-02: 1 hour

Member: Evan

Some extra research has been put into how we will source and get materials for the tower. While the original idea was to use pvc pipes, those would be too flexible. I've decided the best approach is to use 3 pieces of slottable metal fence rails 6ft long sourcable from home depot. Here's a super useful resource I've been referencing for this info: https://www.youtube.com/watch?app=desktop&v=21Q0HFqWtpQ.

## June 7: Design Meeting

Log-03: 3 hours, 20 minutes
Members: Decidous, Evan

**Our goal**: Use a motor to move the ring up the rail with a pulley
THEN, have stationary & moving instruments

We want to have a couple of things that need to **move**.
* Camera: Capture light pollution & cloud coverage at an angled view
* (Optional) Directional Antenna Setup: Wi-Fi relay unit pointing towards source based on GPS coordinates + other antenna to current device
* Solar Panels: Automatically charge up onboard battery
* Anemometer: Accurately measure wind direction & speed (needs to change orientation if wind is blocked by the pole)

**Non-moving parts**:
* PCB: Main weather measuring tools
  * Humidity
  * Temperature
  * Air Quality
* Total Rain Sensor
* Soil Sampler
  * Moisture Level
* Battery

Design Roadmap:
* Sourcing parts
* The PCB
* Weather Ring
* Motor

We have decided to create a custom slip ring design that will use thin brass bendable sheets to line the inside and outside parts of the ring with +3.3v, GND, and (maybe) DATA. This will allow us to keep communications going even on a spinning contraption. The inside ring will not rotate, but the outside ring has gearing that will. A motor will spin the entire ring, while a secondary servo will orient the different components with an attachment arm.

![Screenshot from 2025-06-07 08-03-41](https://github.com/user-attachments/assets/e51ba312-24f4-4c4c-aef4-2787b678b83b)

![Screenshot from 2025-06-07 08-02-09](https://github.com/user-attachments/assets/60e50c07-3812-4a70-ba0f-7afceeda7bf0)

## June 7: Electronic Sourcing

Log-04: 2 hours
Member: Evan

There are many types of sensors in typical weather stations. The most basic being temperature and humidity. There are also some extra, which add greatly to weather estimation. This includes barometers, and anemometers. The first allowing storm prediction from drops in pressure, and the latter showing how chilly it is and the direction to take cover.

All of the sensors above I've found the equivalent for in chips on digikey. One of the points I had was to measure the pollution near roads to decide how safe it was to open building windows in certain city environments. This requires chemical sensors which degrade over time, and are quite expensive. The sensor for detecting carbon monoxide and NO2 costs $20, and the second sensor to detect CO2 costing another $20. These are quite expensive while not long lasting. The average life expectancy for one of the sensors I searched up was about 2 years.

In addition, I've sourced a electric heating pad which can be used inside of the enclosure to maintain temperature throughout the chilly nights. This should reduce humidity, and keep the sensors working optimally. I've decided to sectionalize the board into different areas including the heated area, direct opening (for the smoke & dust detector), & fully enclosed + heated area (microcontroller regulated environment).

Here's an overview of the features I can do with all of the sensors sourced so far
* Air Quality Sensors:
 * **CO2 sensor**: Dangerous levels of CO2 warning inside buildings. Can be used to diagnose road pollution as well.
 * **NO2 + Carbon Monoxide**: Can warn dangerous levels of carbon monoxide (poisoness) for example inside a closed garage with a car running. It can be used to diagnose road pollution
 * **Particulate Sensor**: Can monitor air quality from smoke and dust particulates either from the desert, storms, or wildfires.
* Weather Sensors
 * **Camera**: Can diagnose light pollution by comparing star brightness to the sky. Read cloud coverage & cloud darkness (how full of water they are) all using computer vision algorithms & external server processing.
 * **Barometer**: Detect altitude and perform storm prediction from decreasing air pressure
 * **Temperature & Humidity**: Detects how cold it is & how much water is in the air

I'm also still investigating soil sensors which I could put on a rod that goes into the earth when the instrument ring is at the bottom. This could help give readings on how muddy the terrain is, or if the soil has reached maximum water capacity and will flood.
