# Home Assistant Dashboard Card for Samsung washer-dryer
![Card 02.PNG](https://github.com/Sup3rMario/Dashboard-card-Samsung-washer-dryer/blob/main/Card%2002.PNG)

## Overview
My first attempt at creating a washing machine card for my Home Assistant dashboard for our Samsung washer-dryer.

## Requirement:
You must have connected the Samsung washing machine via the "SmartThings" integration.

## Preparation
You need three entities (since my HA is installed in German, the entities are in German; please check the attached image)
  - a.) Stromversorgung =>  binary_sensor.waschmaschine_stromversorgung ... (this only displays the card when the washing machine is turned on)
  - b.) Vorgangsstatus  =>  sensor.waschmaschine_vorgangsstatus ... (this displays the respective icon for the washing machine's status)
  - c.) Fertigstellungszeit =>  sensor.waschmaschine_fertigstellungszeit ... (this is how the template calculates and formats the remaining time for display on the card)

## Installation
1.) Copy the "washer" folder to the /www/images/ directory.

2.) Depending on where you store your templates, copy the template "washer_remaining_time.yaml" there or enter it directly into the configuration.yaml. (For example, my template files are located in the /template/ folder (entry in the configuration.yaml "template: !include_dir_list template"), then copy the template "washer_remaining_time.yaml" into this folder.)

3.) In the template code, correct the entry: 
 - "sensor.waschmaschine_fertigstellungszeit" to your entity name from point c.) 
 - "sensor.waschmaschine_vorgangsstatus" to your entity name from point b.)

4.) Now it's time to restart Home Assistant so that the sensor "sensor.washer_remaining_time" is created from the template.

5.) Then create a manual card in a dashboard and copy the contents from the "dashboard_card_washer_dryer_samsung.yaml" file into it.

6.) Now you should adapt the entities to your needs:
 - the "binary_sensor.waschmaschine_stromversorgung" entity (point a.)
 - 2 times - the "sensor.waschmaschine_vorgangsstatus" entity (point b.)
	
7.) I'll then switch to the "Show Visual Editor" and change the layout from a column width of 12 to 6, save, and finish.

### Have fun with it.
