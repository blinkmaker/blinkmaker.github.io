---
layout: post
title: Automated pump relay
subtitle: Configurable timer-based controller
bigimg: /img/path.jpg
tags: [arduino, pump, rtc, relay]
---

The water pump on the Algarve Fab Farm takes water from the well on the property and fills up a tank for consumption around the farm at any time. But due to water shortages, the pump needs to be turned on for a short time regularly instead of waiting until the tank is almost empty and then doing full refills. Usually, to deal with this issue, the pump is turned on manually for about 30 to 40 seconds every hour. This can become quite cumbersome, so a better way is to automate the entire process. 

Components used: Arduino UNO R3, DS1302 RTC module, 10A 250VAC relay.

Project: an Arduino was programmed to turn a relay on and off for 40 seconds every hour. The relay is connected to the pump. However, to get a precise measure of time, a DS1302 RTC module was used. The whole process was then tested with some initial difficulties.

The pump relay was first not turning on if the time of operation was changed from 30 to 40 seconds. This issue was solved by fixing a bug in the datatype used. The int datatype has a limitation of holding a maximum value of 32767, which is equivalent to ms and therefore limited to 32.767 seconds. The int type was changed to long, which supports a maximum value of 2,147,483,647.

The second bug had to do with the RTC time data. The initial code took into account the hour to engage the relay but not the minutes and seconds where were not necessary and caused a problem. For example, if the Arduino starts at 11:50:12, then it will activate the pump a second time at 12:00:00 which is only about 10 minutes later. This issue was fixed by resetting both the minutes and seconds and therefore taking into account only the hours data.

The programming now allowed the pump to work fine. I checked every hour to oversee the pump activation for 40 seconds and then it would turn off automatically. However, the next day, i noticed that water was overflowing from the storage tank. The problem was fixed by enabling the water level sensor which was previously disabled by mistake (the red button).
