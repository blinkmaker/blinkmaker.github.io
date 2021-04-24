---
layout: post
title: Improved MPU-6050 calibration
subtitle: Arduino sketch to find offset values
bigimg: /img/path.jpg
tags: [mpu6050, arduino, calibration]
---

To get correct orientation data from the MPU-6050, it is essential to calibrate the device. The MPU-6050 is a MEMS device and due to its very nature – it’s manufactured using nanotechnology – so, it is extremely sensitive to how it’s positioned and any tiny discrepancies during manufacturing can cause different MPU-6050s to output different values. The measured values can vary to various extents and in some cases the data output can be completely wrong. is is due to very small manufacturing differences, such as the position of the chip when it’s soldered onto the breakout board. Therefore, each MPU-6050 should be calibrated individually to obtain their respective offsets before it can be used to obtain meaningful data.

I have made some improvements to the original sketch by Luis Ródenas:
1. A check has been added if the MPU-6050 is not detected, so the sketch does not proceed to find the offsets.
2. The calibration offsets are printed out in a practical format so the results can be directly copied and pasted into the Arduino sketch.
3. Some general minor fixes and visual improvements.

Download the code from my [GitHub repository](https://github.com/blinkmaker/Improved-MPU6050-calibration).
