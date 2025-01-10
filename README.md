# HASS_HPInstantInk
## Overview
HP Instant Ink counter for Home Assistant

This is an implementation for Home Assistant, of a printer-based page counter for tracking usage of an HP Instant Ink plan.

It tracks the number of pages used from the XML page of the printer and, based on that and user-entered details of their plan, monitors the monthly usage of the plan and the overall cost.

## Usage
### Prerequisites
#### Printer Type
- The code is written for an HP Envy 5540 printer. It assumes the XML file of the printer is the same for all HP Instant Ink printers. This is likely not to be the case. There is a guide below of what to look for, and what to do, in that case.
#### Configuration
The configuration.yaml file must have these two items:

`default_config:`  
  
`homeassistant:`  
`  packages: !include_dir_named packages`

Explanation:
- [default_config](https://www.home-assistant.io/integrations/default_config/) configures a default set of integrations for Home Assistant to load.
- [Packages](https://www.home-assistant.io/docs/configuration/packages/) allow the yaml configuration to be combined into a single folder.

## Method

### Files & Folders
- Place the `custom_components/hp_instant_ink_local` folder and contents within the `custom_components` folder, itself within the `configuration` folder of your Home Assistant.
- Download the `packages/hp_envy_5540_instant_ink.yaml` file, and place it in the `packages` folder, itself within the `configuration` folder of your Home Assistant.

The outcome should look like this:  
`config/custom_components`  
`config/custom_components/hp_instant_ink_local`  
`config/custom_components/hp_instant_ink_local/__init__.py`    
`config/custom_components/hp_instant_ink_local/manifest.json`  
`config/custom_components/hp_instant_ink_local/sensor.py`  
`config/packages`  
`config/packages/hp_envy_5540_instant_ink.yaml`

### Update the URL to the printer
- In your favourite text editor, open config/custom_components/sensor.py
- Find the line beginning:  
  _RESOURCE = '`http://hp-envy.lan/DevMgmt/ProductUsageDyn.xml`'
- Replace the URL within the single quotes with the URL of the XML page of your printer.

### Add Sensors
- Edit your `config/sensors.py` to add the following:

`- platform: hp_instant_ink_local`  
`  resources:`  
`    - sp`  
`    - tp`  
`    - cr`  
`    - br`  

### Lovelace Cards
- Download the files in the 'cards' folder.  
- For each file, in the HASS front end, create a new card in yaml mode, paste in the code, then commit the card.

## Possible Issues
If the sensor does not work, check the following  
+ The URL and/or name of the XML page of the printer is correct.
+ Note the XML tag names in which the counters are found.

Once the tags have been identified, check in the sensor.py file for these and amend accordingly for the XML path to the correct tags:
- Subscription Pages:  
  xml_data = doc["pudyn:ProductUsageDyn"]["pudyn:PrinterSubunit"]["pudyn:SubscriptionImpressions"]
- Total Pages:  
  xml_data = doc["pudyn:ProductUsageDyn"]["pudyn:PrinterSubunit"]["dd:TotalImpressions"]["#text"]
- Colour Ink Percentage Remaining:  
  xml_data = doc["pudyn:ProductUsageDyn"]["pudyn:ConsumableSubunit"]["pudyn:Consumable"][0]["ConsumableRawPercentageLevelRemaining"]
- Black Ink Percentage Remaining:  
  xml_data = doc["pudyn:ProductUsageDyn"]["pudyn:ConsumableSubunit"]["pudyn:Consumable"][1]["ConsumableRawPercentageLevelRemaining"]
  
