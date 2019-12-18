---
layout: post
title: Algarve Fab Farm
subtitle: Automated water pump relay
---

The water pump takes water from the well on the property and fills up a tank. But due to water shortages, the pump needs to be turned on for a short time regularly. The state of dealing with this issue, is to manually turn on the pump for about 30 to 40 seconds every hour. This can become quite cumbersome, so a better way is to automate the entire process. 

Project: an Arduino was programmed to turn a relay on and off for 40 seconds every hour. The relay is connected to the pump. However, to get a precise measure of time, a DS1302 RTC module was used. The whole process was then tested with some initial difficulties.

The pump relay was first not turning on if the time of operation was changed from 30 to 40 seconds. This issue was solved by fixing a bug in the datatype used. The int datatype has a limitation of holding a maximum value of 32767, which is equivalent to ms and therefore limited to 32.767 seconds. The int type was changed to long, which supports a maximum value of 2,147,483,647.


