---
weight: 1
title: "Quick start guide for SimulIDE as an Arduino simulator"
date: 2023-01-22T00:00:00+08:00
lastmod: 2024-09-11T00:00:00+08:00
draft: false
author: "Pascal"

tags: ["simulide","arduino","simulation"]
categories: ["tech-embedded"]

lightgallery: true

toc:
  auto: false
---

> The idea behind this tutorial is to show how to install SimulIDE to run codes for an Arduino Uno board. Screenshots below were taken from a Windows machine. It will be the same thing for Unix-based systems (tested on Ubuntu). Some comments for the Mac port at the end (but it works!)

## Downloading tools

- [SimulIDE](https://www.simulide.com/p/downloads.html) : **Last Stable Version (1.1.10)**. For Linux, please prefer the `Linux64` archive. 
- [Arduino](https://www.arduino.cc/en/Main/Software). **Legacy IDE (1.8.19)**. Download the `Windows ZIP file` or the `Linux 64 bits` archive.

Note : for Ubuntu/Debian derivatives, you should install a few libraries to make SimulIDE working:

```bash
sudo apt-get install libqt5core5a libqt5gui5 libqt5xml5 libqt5svg5 libqt5widgets5 libqt5concurrent5 libqt5multimedia5 libqt5multimedia5-plugins libqt5serialport5 libqt5script5 libelf1
```

Extract softwares in a directory. You should get something similar to this:

![image-20200422203821497](../img/simulide-img1.jpg)

## Example: blinking LEDs on an Arduino Uno

In order to execute SimulIDE, run the executable at: `<simulide_dir>/bin` (on Windows)

![image-20200422204251027](../img/simulide-img2.jpg)

Here is the main interface :

![image-20200422205142210](../img/simulide-img3.jpg)

### Schematic settings (red rectangle)

| 1                 | 2                                   | 3        | 4    | 5    | 6       | 7              | 8     |
| ----------------- | ----------------------------------- | -------- | ---- | ---- | ------- | -------------- | ----- |
| SimulIDE settings | Switch between already opened files | New file | Open | Save | Save as | Run simulation | Pause |

### Code editor settings (blue rectangle)

| 1             | 2                                   | 3        | 4    | 5    | 6       | 7       | 8                       |
| ------------- | ----------------------------------- | -------- | ---- | ---- | ------- | ------- | ----------------------- |
| Code settings | Switch between already opened files | New file | Open | Save | Save as | Compile | Download on the Arduino |

Open the LED fadding example (`<simulide_dir>/share/simulide/examples/Arduino/ledFadding`)

- `.simu` file for the schematic.
- `.ino` file for the code.

### Compiler configuration

![image-20200422210236017](../img/simulide-img4.jpg)

Right click on the `ledFadding.ino` and click `Set Compiler Path`. Select the directory where you have the Arduino executable (`./simul_ide/arduino-1.8.12` in the screenshot below).

![image-20200422210353987](../img/simulide-img5.jpg)

Now you should be able to compile and upload your code!

![image-20200422210752398](../img/simulide-img6.jpg)

Now, just click on the red button in the upper left toolbar:

![image-20200422210913913](../img/simulide-img7.jpg)

> Hint: if you need a serial monitor, right click on the Arduino and select **Open Serial Monitor**.

> Hint: if you need something like a real-time monitor, right click on the Arduino and select **Open MCU Monitor**. You'll be able to check register contents in real-time when the simulation is running !

![mcu](../img/simulide-img8.jpg)

## Alternative compiler configuration

Sometimes, compiler settings are a bit painful. It may be easier to compile the binary in the default Arduino IDE and export the HEX file to be loaded in the simulator.

- Compile the binary in the Arduino editor. Then click on `Sketch => Export compiled binary`.
- Then, right click on the Arduino in SimulIDE and select `Load firmware` and look for the `*.hex` file just compiled close to the Arduino project file.