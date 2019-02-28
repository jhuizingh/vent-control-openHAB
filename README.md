# openHAB Room Based Smart Vent Control

This is a set of item definitions, rules, and sitemap entries to enable control of smart vents in multiple different rooms that have their own temperature sensors. It is made to work in the [openHAB](https://www.openhab.org/) home automation bus.

There are currently 3 main files in directories that correspond with openHAB configuration folder directories. They are:

 1. items/climate_control.items - This contains the item definitions needed for the rules to work properly. It contains the items for a single room. Multiple rooms can be incorporated by copy/pasting the room-specific items and then updating the names appropriately. Most of these items to do not have any binding information configured because either they are virtual items or they would be specific to your environment.
 2. rules/smart_vent_management.rules - This contains rules that form the heart of the vent management in this system. It uses a combination of the [Associated Items](https://community.openhab.org/t/design-pattern-associated-items/15790) and [Working with Groups in Rules](https://community.openhab.org/t/design-pattern-working-with-groups-in-rules/20512) Design Patterns.
 3. sitemaps/vent_control.sitemap - This is a subgroup of items that can be placed in an existing sitemap in the appropriate place to show the items needed to control the room. Note, it is not a full sitemap and will not work if you attempt to use it as one. It must be placed within a valid sitemap.
![Basic UI Sample](./screenshots/BasicUI%20Sample.png)

# Features

 - Control the temperature of different rooms using temperature sensors and smart vents in each room you want to control. This works with one central HVAC thermostat, and vents are opened or closed based on what the HVAC system is doing. The limitation here is that you can't cool one room while heating others.
 - Ability to globally enable or disable control of all vents by openHAB
 - Ability to enable or disable control of an individual room's vents
 - Ability to manually force certain vents closed with the flip of a switch (if the blowing air is too cold if people are in a certain room, even if the temperature is still above the desired cool, for example)
 - Ability to use the thermostat's heat setting as a room's heat target or to override it on a room-by-room basis.
 - Ability to use the thermostat's cool setting as a room's cool target or to override it on a room-by-room basis.
