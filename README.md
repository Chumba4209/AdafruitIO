# **BMP180 Sensor to Adafruit IO via MQTT**
This project allows you to collect temperature and pressure data from a BMP180 sensor using an ESP8266 (D1 Mini) microcontroller, transmit it via MQTT to Adafruit IO, and view the data either on your Adafruit IO Feeds or Dashboards.
Configuration is made simple via a Wi-Fi Manager portal, eliminating the need to access or modify the code directly.

**Hardware Requirements**

•	ESP8266 D1 Mini (or compatible ESP8266 microcontroller)

•	BMP180 Temperature and Pressure Sensor

•	0.96" OLED Display (I2C)

•	Micro USB cable (for flashing and powering the ESP8266)

**Software Requirements**

•	Adafruit IO Account (https://io.adafruit.com/)

•	Two Adafruit IO Feeds:
o	BMP_Temperature
o	BMP_Pressure

•	Optional: Adafruit IO Dashboard (for visualization)

**Setup Instructions**

**Step 1: Create Adafruit IO Feeds**

Log into your Adafruit IO account and create two new feeds:
•	BMP_Temperature

•	BMP_Pressure
These will receive the live data from your device.


**Step 2: Flash Binary Firmware**

Flash your ESP8266 using the provided binary file available through the Solution Builder platform under “BMP180+AdafruitIO” on the link: https://solutions.carenuity.com/solutions/CvNzl2HewiJ08jA2p7mN?ecosystem=mxPH5kGodhJBicKPFXwx

No Arduino IDE or code editing is required.

**Step 3: Wi-Fi and Adafruit IO Configuration via Config Portal**

When the ESP8266 boots up for the first time, it will:

1.	Display on the OLED:
* Booting...
2.	 Open BMP180Config on WiFi
3.	Edit WiFi and Adafruit IO credentials
4.	 Save
5.	Open a Wi-Fi Access Point named BMP180ConfigAP.
6.	Connect to this Wi-Fi from your phone or laptop.
7.	A captive portal will open automatically (or visit 192.168.4.1).
8.	Enter:
* Your Wi-Fi SSID and Password.
* Your Adafruit IO Username.
* Your Adafruit IO Key.
9.	Click Save 

**Step 4: Device Behavior after Reset**

If configured correctly, OLED shows:
* Booting...
* WiFi Connected
* MQTT Connected
* Temp: 25.3 °C
* Pres: 1013.2 hPa
> Live sensor readings update continuously on the OLED display.
> Data is sent automatically to your Adafruit IO feeds.

If MQTT fails to connect, OLED shows:
* MQTT Failed. Retrying...

**Step 5: View Data on Adafruit IO Dashboard (Optional)**

To visualize your sensor data:
1.	Go to the Dashboards section in Adafruit IO.
2.	Create a new Dashboard.
3.	Add two widgets:
> Gauge, Line Chart for BMP_Temperature.
> Gauge, Line Chart for BMP_Pressure.
4.	Link each widget to the respective feed you created earlier.

Now you can monitor your temperature and pressure values in real-time!
