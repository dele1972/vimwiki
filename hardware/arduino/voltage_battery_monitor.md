ADC_MODE(ADC_VCC);
int Batt;

void setup(){
...
}

void loop(){
Batt = ESP.getVcc();
}



This is where things become interesting. By the way most ESP8266 boards are designed, one cannot read the battery voltage Vin without external components. But there is a method to detect a discharged battery indirectly, by measuring the input voltage of ESP8266 — that would be V3.3.

In the code example above, the ESP8266 is configured to read the V3.3 voltage by placing ADC_MODE(ADC_VCC); on top of the sketch.

Then, the battery voltage in mV is read as in uint32_t getVcc = ESP.getVcc();

In my experiments, I found the following relation between Vin, V3.3 and the Vmeasured by ESP.getVcc(); This applies to the ESP8266 Thing Dev, which uses AP2112K-3.3V LDO regulator. Some other boards might behave differently so you will have to redo my experiment.

First of all, we see there’s an offset of about 0.18V between the Vmeasured and the actual V3.3. One can leave it like this or can compensate in the software.

Then we notice that, when the input voltage Vin = 3.3V, we have V3.3 = 3.2575 (it becomes to drop). The ESP8266 senses this small voltage drop, and it measures 3.44V.

Further, when the battery voltage drops to 3V (which is the safe margin to discharge LiPo batteries), the readout of the ESP.getVcc() is 3.106V. We can use this value to trigger a deep sleep to keep the battery from discharging


https://www.electronza.com/2019/05/esp8266-running-on-battery-power.html

https://www.reddit.com/r/esp8266/comments/7ywmeg/powering_wemos_d1_mini_with_lifepo4_33v/

https://www.engineersgarage.com/electronic-projects/nodemcu-battery-voltage-monitor/
https://www.electroniclinic.com/esp8266-iot-battery-monitor-battery-voltage-monitoring-using-nodemcu-esp8266-wifi-module/


