---
title: "Fish Hut, Dual Temps, Log-n-Plot"
date: 2019-06-28T10:50:51-02:00
draft: true
tags: []
topics: []
description: ""
---

## What and Why

A quick exercise to familiarize with the Feather M4 Express, Circuitpython, and some of the challenges in getting useful data as a product.

## Where and When

During flight period three I was berthed in "Purple #2", one of the double-ended huts. Quickly I discovered that a water bottle left on the bottom shelf would freeze over night, but left on the top shelf would not. Time for an experiment. With me I have two TMP36 temperature sensors, so naturally the thing to do was measure the temp on the top and bottom shelves through the night and examine the difference.

## How

#### Temp Probe Build

Twisted triplet wires.

#### Feather M4 Programming

Circuitpython functions
RTC on adalogger

#### Probe Placement and Data Capture

Photo of shelves, "open space" probe offset

#### Data Formatting and Presentation

Pandas, Matplotlib
Pandas, Bokeh
Pandas, io.adafruit.com

## Results

#### Quick Look

What was that upper probe spike around 0615 local time?!

## Future Fiddling

Enclosure
Terminals for probes
Trinket instead of Feather M4 Express
