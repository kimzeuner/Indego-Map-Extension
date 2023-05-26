# Indego-Map-Extension
Add Indego Map to your Indego Integration

# Indego-Map-Extension

## General information

Firt of all, i have no ides how python scrpts are made, i was able to make this extension work using the Bosch Integration by jm73 and code snippets from SmarthomeAddicted (Just Copy and Paste and Trial and Error). 
This means in most cases i will not be able to fix any issues, i just hope this extensions works for you out of the box.

These Files are making it possible to use some more features in the Indego Integration for HA- by jm-73.
New Functions, Features:
	1. Map of your Mower/Garden
	2. Some advanced Alert functions
	3. Some new services regarding Map and Alerts

## Installation

1. Install Indego Integration by jm-73 from HACS (i used Version 5.1) and add your Mower (using Bosch Single Key) as described.
2. Download Files from indego-map-extension.
3. Copy the files "__init__.py", "const.py", "manifest.json" and "services.yaml" into your indego folder (/custom_components/indego) and replace the existing files. 
4. Restart HA.
5. Maybe it is needed to install svgutils and sh (you will see a Log Entry after restart with errorcode (ModuleNotFoundError: No module named 'sh' or ModuleNotFoundError: No module named 'svgutils')
	1. i have done this by using "Advanced SSH & Web Terminal" from Add-On Store
	2. command pip install svgutils will install svgutils
	3. command pip install sh will install should
	4. Restart HA.

## Usage

After replacing the files and restarting HA you should find several new Entities in your Integration.
New Entities:
Alert count
Alert date
Alert description
Alert errorcode
Alert flag
Alert headline
Alert id
Alert message
Alert push
Alert read status
Has map
Map svg cache ts
Map update availabel
Position svg x
Position svg y
Position x
Position y

Also some new services will be available (just type "indego" in your services tab and you will find them)
download map
read alert
read alert all
delete alert
delete alert all


On firts use you have to download the Map from your Mower. 
This can be done by using the service "Bosch Indego Mower: download_map". 
In the datafield add "filename: mapWithoutIndego" (without quotation).
This will download the map and save it in your www folder (mapWithoutIndego.svg)
Afterwards also a map with your Mower Position will be added (mapWithIndego.svg)
Unfortunately i am not sure when the mapWithIndego is created but it should be done after an status update of your mower.

## Additional information
Save the existing Files (mentioned above) from your Indego Integration before replacing them so you can re-upload them when my files are not working.
Once it works, save the files before making an update of the Indego Integration. I think the files will be replaced during the update.

## Credits

Thanks to jm-73 & SmarthomeAddicted

This Extension uses the Bosch Indego Integration by jm-73  https://github.com/jm-73/Indego
and some code snippets by SmarthomeAddicted https://github.com/SmarthomeAddicted/Indego-Integration who was able to make the Map work in the old Version (before start of Single Key)


