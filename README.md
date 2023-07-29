# ESP32-Temperature-Humidity-monitoring-system
An asynchronous ESP32 web server with the DHT11 that displays temperature and humidity using Arduino IDE
# Hardware Components
a) ESP32 development board

b) DHT11 Temperature and Humidity Sensor

c) 4.7k Ohm Resistor

d) Breadboard

e) Jumper wires

# Software Components
a) Arduino IDE

b) Required libraries: Wi-Fi, ESPAsyncWebServer, ESPAsyncTCP, Adafruit_Sensor and DHT

# ESP32
![image](https://github.com/KarthikT23/ESP32-Temperature-Humidity-monitoring-system/assets/119528503/c026872d-9985-4b06-a982-0cc67a0ab8a0)

# ESP32 Pinout
![image](https://github.com/KarthikT23/ESP32-Temperature-Humidity-monitoring-system/assets/119528503/2f566421-0116-48fc-9296-51627fb8fd5c)

# ESP Web Server
![image](https://github.com/KarthikT23/ESP32-Temperature-Humidity-monitoring-system/assets/119528503/cc9590ed-3e3e-491f-9b6a-9060749ab7f1)

# Arduino IDE
![image](https://github.com/KarthikT23/ESP32-Temperature-Humidity-monitoring-system/assets/119528503/7cd214b5-981c-48a2-9679-e3f96e476a5e)

# DHT11
![image](https://github.com/KarthikT23/ESP32-Temperature-Humidity-monitoring-system/assets/119528503/dc05c7d4-d01f-4eef-bdd8-ad792a0b4e0c)

# Circuitry
Connect the Vcc pin of the DHT11 to 3.3V pin of ESP32. Connect the GND pin of DHT11 to GND of ESP32. Connect the Data Pin to GPIO 27, but you can connect it to any other digital pin. Also connect a pull-up resistor of 4.7K ohm to the Data Pin.
![image](https://github.com/KarthikT23/ESP32-Temperature-Humidity-monitoring-system/assets/119528503/99f40083-70e2-409f-8c24-84ba8c0910d6)

# Code Algorithm
1) First, import the required libraries. The Wi-Fi, ESPAsyncWebServer and the ESPAsyncTCP are needed to build the web server. The Adafruit_Sensor and the DHT libraries are needed to read from the DHT11. Insert your network credentials in the ssid and password variables, so that the ESP32 can connect to your local network.

2) Define the GPIO that the DHT data pin is connected to. Instantiate a DHT object with the type and pin we’ve defined earlier. Create an AsyncWebServer object on port 80.

3) Getting sensor readings is as simple as using the readTemperature() and readHumidity() methods on the dht object. We also have a condition that returns two dashes (–) in case the sensor fails to get the readings. By default, we’re reading the temperature in Celsius degrees.

# Building the Webpage
1) All the HTML text with styles included is stored in the index_html variable. The <meta> tag makes your web page responsive in any browser. The <link> tag is needed to load the icons from the fontawesome website.

2) Between the <style></style> tags, we add some CSS to style the web page. Basically, we’re setting the HTML page to display the text with Arial font in block without margin, and aligned at the center.

3) We set the font size for the heading (h2), paragraph (p) and the units(.units) of the readings. All of the previous tags should go between the <head> and </head> tags. These tags are used to include content that is not directly visible to the user, like the <meta> , the <link> tags, and the styles.

4) Inside the (body)(/body) tags is where we add the web page content. The (h2)(/h2) tags add a heading to the web page. In this case, the 'ESP32 DHT server' text, but you can add any other text.

5) Then, there are two paragraphs; one to display the temperature and the other to display the humidity. The paragraphs are delimited by the (p) and (/p) tags.

# Automatic Updates
1) There’s some JavaScript code in our web page that updates the temperature and humidity automatically, every 10 seconds. Scripts in HTML text should go between the <script></script> tags. To update the temperature on the background, we have a setInterval() function that runs every 10 seconds.

2) Basically, it makes a request in the /temperature URL to get the latest temperature reading. When it receives that value, it updates the HTML element whose id is temperature.

3) The processor() function will replace the placeholders in our HTML text with the actual temperature and humidity values. In the setup(), initialize the Serial Monitor for debugging purposes. Initialize the DHT sensor. Connect to your local network and print the ESP32 IP address.

4) When we make a request on the root URL, we send the HTML text that is stored on the index_html variable. We also need to pass the processor function that will replace all the placeholders with the right values. We need to add two additional handlers to update the temperature and humidity readings.

5) When we receive a request on the /temperature URL, we simply need to send the updated temperature value. It is plain text, and it should be sent as a char, so, we use the c_str() method.

6) The same process is repeated for the humidity. Lastly, we can start the server.
Because this is an asynchronous web server, we don’t need to write anything in the loop().

# Results
![image](https://github.com/KarthikT23/ESP32-Temperature-Humidity-monitoring-system/assets/119528503/5ae7fbdf-77a1-466e-b1d6-c6800bd54627)
![image](https://github.com/KarthikT23/ESP32-Temperature-Humidity-monitoring-system/assets/119528503/90bc8b3e-11f2-4b43-b940-0a3f8f672668)
![image](https://github.com/KarthikT23/ESP32-Temperature-Humidity-monitoring-system/assets/119528503/def11dbf-50d3-438f-a5df-bfe37259e873)


# References
[1] https://randomnerdtutorials.com/esp32-dht11-dht22-temperature-humidity-web-server-arduino-ide/

[2] https://www.electronicshub.org/dht11-humidity-sensor-arduino/

[3] https://randomnerdtutorials.com/esp32-pinout-reference-gpios/

[4] https://randomnerdtutorials.com/esp32-dht11-dht22-temperature-humidity-sensor-arduino-ide/

[5] https://randomnerdtutorials.com/esp32-async-web-server-espasyncwebserver-library/

[6] https://www.elprocus.com/a-brief-on-dht11-sensor/

[7] Srivastava, Deeksha, Awanish Kesarwani, and Shivani Dubey. "Measurement of Temperature and Humidity by using Arduino Tool and DHT11." International Research Journal of Engineering and Technology (IRJET) 5.12 (2018): 876-878.

[8] Gay, W. (2018). DHT11 sensor. In Advanced Raspberry Pi (pp. 399-418). Apress, Berkeley, CA.

[9] https://www.researchdive.com/blog/the-working-of-humidity-sensor-and-its-applications-in-various-industries

[10] https://thesai.org/Downloads/Volume10No9/Paper_66-IoT_based_Temperature_and_Humidity_Controlling.pdf

[11] https://circuitdigest.com/microcontroller-projects/interfacing-dht11-sensor-with-arduino

[12] https://hackaday.io/projects?tag=dht11

[13] https://www.elithecomputerguy.com/2020/05/arduino-projects-garden-sensor-suite-dht11-ds3231-light-moisture-i2c-lcd/






