---
title: "Automate The Snake Plant"
date: 2021-06-19T11:47:41-07:00
draft: false
tags: ["electronics", "sensors", "adafruit", "clue", "automation", "plants"]
topics: []
description: "Plant Scrubs the Air, Clue Automates the Care"
---

## Scrub The Air
Back in the '80s NASA conducted studies on plants suitable for ["Indoor Air Pollution Abatement"][1]. The Sansevieria family of plants were excellent performers and have the added benefit of being hardy succulents, requiring little water and indirect sunlight. A living plant is calming in my work space and the added air quality benefit makes this an easy choice for the amount of space it takes.

#### The Plant
The sansevieria fernwood variety happens to be [$7 at Ikea][2]. Transfer it into a [BOYSENBÄR concrete pot][3] and I have a tangible quality of life improvement.

#### The Plant Care
According to [Plantophiles.net][4] the number one risk in caring for a snake plant is over-watering. So, always on the lookout for electronics or microcontroller projects, automating and tracking the soil moisture seems like a perfect fit.  

#### Automate The Plant Care
Once again Adafruit has anticipated this application with their penchant for urbanite microcontroller projects. The [Bonsai Buckaroo Plant Care Kit][5] takes the stage. Together with a [Clue microcontroller][6] you can sense, log, and control the soil moisture in a package that comes with a tidy display and a host of other sensors. Granted, the Clue is expensive and overpowered for this application, but for development its a perfect choice.

## What, Where, When, How
According to Plantophiles.net, the happiest snake plant likes dry soil: "Soil that is still moist to the touch should be left another few days and then checked again". So, the target parameter we are controlling is soil moisture and the target value is "dry".

#### The What
The Bonsai Buckaroo is measuring resistance between two stainless steel nails and driving a water pump. The initial assumption will be that dry soil will have "very high" resistance. We can start with an initial target value and then iterate to a value that makes sense for the system.

For water delivery we will have to control a couple of parameters:
1. What volume of water will switch the soil from "dry" to "not dry"?
2. What location should this volume of water be applied to?

The pump will have to be characterized for how to accurately deliver the volume we want. How much is "a little", how much is "a lot"? The pump will be pulsed on and off and may have a minimum time or volume required to move any water at all.

#### The Where
Where should the resistance measurement electrodes be located to best represent "dry" and "not dry" soil? Also, from an aesthetic perspective, I would prefer the nails and terminals to be invisible to the casual observer.

For the pump, same scenario with the style of it, I want the pump and water hidden. Fortunately the 6" concrete pot is larger than the plastic pot Ikea sells the plant in, so there is a buffer space below for the pump, water, electrodes, and leads.

For the water delivery, where should the tubing terminate to most effectively move soil from "dry" to "not dry"? Should the tubing terminate within the soil? On top?

#### The When
Once the microcontroller decides it is time to "un-dry" the soil, and we know how much water to deliver, how long does the water take to "un-dry" it? Should we average moisture readings for 2 minutes? 10 minutes? An hour? Should there be a minimum "dead time" between water deliveries, to ensure that over-watering cannot occur?

#### The How
In an ideal world we would have a control pot with all of the same dimensions, soil, etc and only the plant missing. The control pot would be the test bed for determining all of the above parameters. As it is, I will work the existing pot primarily. Maybe a separate cup of soil for wetting experiments, but essentially the whole project ad hoc and residing on the desk where it will finally live.




[1]: https://ntrs.nasa.gov/citations/19930073077
[2]: https://www.ikea.com/us/en/p/sansevieria-plant-with-pot-snake-plant-assorted-colors-60445796/
[3]: https://www.ikea.com/us/en/p/boysenbaer-plant-pot-indoor-outdoor-light-gray-40459256/
[4]: https://plantophiles.com/plant-care/sansevieria-fernwood/
[5]: https://www.adafruit.com/product/4746
[6]: https://www.adafruit.com/product/4500
