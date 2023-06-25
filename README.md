# HASS_HPInstantInk
## Overview
HP Instant Ink counter for Home Assistant

This is an implementation for Home Assistant, of a page counter for tracking usage of an HP Instant Ink plan.

It tracks the number of pages used from the XML page of the printer and, based on that and user-entered details of their plan, automatically monitors the monthly usage of the plan and the overall cost.

## Usage
Download the 'packages/hp_envy_5540_instant_ink.yaml' file, and place it in the [packages](https://www.home-assistant.io/docs/configuration/packages/) folder of the configuration area of Home Assistant.

Download the files in the 'cards' folder.  For each file, in the HASS front end, create a new card in yaml mode, and paste in the code. Then commit the card.

## Scrape Sensor
The Scrape Sensor wizard in Integrations should be used as below. 
- It is critical that the Scrape Sensor Entity ID is named exactly as, 'sensor.hp_envy_5540_total_pages_printed_xml', and that the Value Template is, '{{ value|int(-1) }}'

### Wizard Page 1
![01_Select_Scrape_Integration](https://github.com/EventuallyFixed/HASS_HPInstantInk/assets/39234149/fab2345e-0fc0-4bf9-876e-c74513e5f9d9)

### Wizard Page 2
![02_Wiz_Page_01_all](https://github.com/EventuallyFixed/HASS_HPInstantInk/assets/39234149/665e936b-dbcd-489e-8448-cfbd14d4b02e)

### Wizard Page 3
![04_Wiz_Page_02_all](https://github.com/EventuallyFixed/HASS_HPInstantInk/assets/39234149/ed186eae-05cb-44cc-a5fe-03f0cf384e5e)

### Wizard Page 4
![05_Wiz_Page_03_Success](https://github.com/EventuallyFixed/HASS_HPInstantInk/assets/39234149/2344c559-1e74-486c-a681-0bcd1eb92b6a)



















 
