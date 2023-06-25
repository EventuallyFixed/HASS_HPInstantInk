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

![01_Select_Scrape_Integration](https://github.com/EventuallyFixed/HASS_HPInstantInk/assets/39234149/fab2345e-0fc0-4bf9-876e-c74513e5f9d9)

![02_Wiz_Page_01a](https://github.com/EventuallyFixed/HASS_HPInstantInk/assets/39234149/db19ba15-9587-4bc8-aabf-bb961b3f87a3)

![03_Wiz_Page_01b](https://github.com/EventuallyFixed/HASS_HPInstantInk/assets/39234149/7cc58908-bb78-40a7-a518-0f01e48e6fd0)

![04_Wiz_Page_02a](https://github.com/EventuallyFixed/HASS_HPInstantInk/assets/39234149/bca3513f-3116-44ec-bbca-1d9932f1f8e9)

![05_Wiz_Page_02b](https://github.com/EventuallyFixed/HASS_HPInstantInk/assets/39234149/e6789131-9764-4073-82a7-afa355c90401)

![05_Wiz_Page_03_Success](https://github.com/EventuallyFixed/HASS_HPInstantInk/assets/39234149/2344c559-1e74-486c-a681-0bcd1eb92b6a)



















 
