# HASS_HPInstantInk
## Overview
HP Instant Ink counter for Home Assistant

This is an implementation for Home Assistant, of a page counter for tracking usage of an HP Instant Ink plan.

It tracks the number of pages used from the XML page of the printer and, based on that and user-entered details of their plan, automatically monitors the monthly usage of the plan and the overall cost.

## Usage
Download the 'packages/hp_envy_5540_instant_ink.yaml' file, and place it in the [packages](https://www.home-assistant.io/docs/configuration/packages/) folder of the configuration area of Home Assistant.

Download the files in the 'cards' folder.  For each file, in the HASS front end, create a new card in yaml mode, and paste in the code. Then commit the card.

