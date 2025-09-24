# OpenEPaperLink integration for H<img width="16"  alt="Home assistant" src="Images/Ha.png">me Assistant

[<img alt="Home Assistant" width="300" src="https://episensor.com/wp-content/uploads/2023/04/home-assistant.png" />](https://www.home-assistant.io/)<br>
Home Assistant Integration for the [![Static Badge](https://img.shields.io/badge/OpenEPaperLink-project-blue?logo=github)](https://github.com/jjwbruijn/OpenEPaperLink)<br>
Home Assistant guide from [![Static Badge](https://img.shields.io/badge/Jonas%20_Niesner-blue?logo=github)](https://github.com/jonasniesner/open_epaper_link_homeassistant)<br>
Wiki code examples [![Static Badge](https://img.shields.io/badge/Jonas_Niesner_Wiki-blue?logo=github)](https://github.com/jonasniesner/open_epaper_link_homeassistant.wiki.git)<br>
Home Assistant [![Static Badge](https://img.shields.io/badge/HA-Electronic%20_Price%20_Tag-blue?logo=homeassistant&logoColor=blue)](https://community.home-assistant.io/t/anyone-looked-into-using-electronic-price-tag-screens-with-ha/407649/1)<br>
E-paper display [![Static Badge](https://img.shields.io/badge/Share_your-Projects!-blue?logo=homeassistant)](https://community.home-assistant.io/t/e-paper-display/138625)

Here is a code that I made according to this template [![Static Badge](https://img.shields.io/badge/Electricity-price?logo=github)](https://github.com/jonasniesner/open_epaper_link_homeassistant/wiki/Electricity-price-and-usage-costs)<br>
It works perfectly fine to run in Home Assistant and that generates what I want to achieve via the sensors I added from tibber and tibber pulse.<br>
This after I implemented Homey Pro with Home Assistant to get values from Homey pro and be able to use them in Home Assistant.<br>
This was only possible after I followed this guide on how to connect Homey pro with Home assistant after a successful connection using MQTT.<br>
[![Static Badge](https://img.shields.io/badge/Homey%20pro%20%2B%20Home%20Assistant%20guide-blue?logo=github)](https://community.homey.app/t/tutorial-pro-how-to-integrate-home-assistant-with-homey/92641)<br>
The extra functions in this file is the arrow that turns red and face downwards if the current price is below 1Kr and turns upwards if the current price is over 1Kr and also then changes the arrow to black.<br>
Likewise, with the current price that changes color according to the price.<br>

Put in your Display ID in the code and add your own sensors to it and you are good to go. <br>
Here is an example of one of my displays running the below code with some modifications.<br>
I will post a new code when I am satisfied with the result.<br>

<img width="400"  alt="Display" src="Images/ha_display.png"><br>

```
    service: open_epaper_link.drawcustom
target:
  entity_id: open_epaper_link.Put in your own display ID here
data:
  background: white
  dry-run: false
  ttl: 60
  rotate: 0
  payload:
    - type: line
      fill: red
      width: 3
      x_start: 148
      y_start: 0
      x_end: 148
      y_end: 110
    - type: line
      fill: red
      width: 2
      x_start: 0
      y_start: 109
      x_end: 296
      y_end: 109
    - type: text
      value: Kostnad idag!
      font: ppb.ttf
      x: 74
      "y": 20
      size: 20
      color: black
      anchor: mm
    - type: text
      value: >-
        {{ states('sensor.tibber_pulse_accumulated_cost') |
        round(0) }} kr
      font: ppb.ttf
      x: 74
      "y": 58
      size: 38
      color: >-
        {{ 'black' if
        states('sensor.tibber_pulse_accumulated_cost') |
        round(0) | int <= 50 else 'red' }}
      anchor: mm
    - type: text
      value: >-
        {{
        states('sensor.tibber_pulse_accumulated_consumption')
        | round(0) }} kWh
      font: ppb.ttf
      x: 74
      "y": 90
      size: 20
      color: >-
        {{ 'black' if
        states('sensor.tibber_pulse_accumulated_consumption')
        | round(0) | int <= 100 else 'red' }}
      anchor: mm
    - type: text
      value: Elpris nu!
      font: ppb.ttf
      x: 225
      "y": 20
      size: 20
      color: black
      anchor: mm
    - type: text
      value: >
        {% set electricity_price_attr =
        state_attr('sensor.electricity_price', 'low_price') %}
        {% set electricity_price_state =
        states('sensor.electricity_price') | round(2) %} {% if
        electricity_price_attr is not none and electricity_price_attr | round(2)
        == true %}
          {{ electricity_price_state }}
        {% else %}
          {% if electricity_price_state < 1 %}
            {{ electricity_price_state }}
          {% else %}
            {{ electricity_price_state }}
          {% endif %}
        {% endif %}
      font: ppb.ttf
      x: 224
      "y": 60
      size: 36
      color: red
      anchor: mm
    - type: text
      value: >-
        {{ 'öre/kWh' if states('sensor.electricity_price') |
        round(2) < 1 else 'Kr/kWh' }}
      font: ppb.ttf
      x: 224
      "y": 90
      size: 18
      color: black
      anchor: mm
    - type: icon
      value: >-
        {{ 'arrow-up' if states('sensor.electricity_price') |
        round(2) >= 1 else 'arrow-down' }}
      x: 160
      "y": 95
      size: 20
      color: >-
        {{ 'black' if states('sensor.electricity_price') |
        round(2) >= 1 else 'red' }}
      anchor: mm
    - type: text
      value: >-
        Hittils denna månad: {{ states('sensor.monthly_cost')
        | round(0) }} kr
      font: ppb.ttf
      x: 3
      "y": 120
      size: 12
      color: black
      anchor: lm
    - type: text
      value: "Kl: {{ now() | as_timestamp() | timestamp_custom('%H:%M', true) }}"
      font: ppb.ttf
      x: 235
      "y": 120
      size: 12
      color: black
      anchor: lm

```
<img width="400"  alt="Display" src="Images/ha_display.jpeg"><br>

The layout for this display abow you need to add your own sensors.<br>
You also need to have the Swedish Post Delivery integration for Home Assistant installed and configured for your postal code.<br>
[Here is the code for the layout](https://github.com/wizz666/OpenEpaperLink-Homey-Pro/blob/main/Sample%20code%20Home%20Assistant)<br>

<img width="400"  alt="Display" src="Images/F1.jpg"><br>

The layout for this display abow you need to add the sensors in HA and use it like the example code below.<br>
[Here you find the F1 Sensor for Home Assistant](https://github.com/Nicxe/f1_sensor)<br>
[Here is the example code for the layout](https://github.com/wizz666/OpenEpaperLink-Homey-Pro/blob/main/Sample%20code%20F1)<br>
