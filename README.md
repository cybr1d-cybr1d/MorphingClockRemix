# MorphingClockRemix
Modified from HariFun's great Morphing Digital Clock idea https://www.instructables.com/id/Morphing-Digital-Clock/ and lmirel's MorphingClockRemix https://github.com/lmirel/MorphingClockRemix.

I used HariFun's experimental 12E code for the clock and WiFi https://github.com/hwiguna/HariFun_166_Morphing_Clock/tree/Experimental12E

The exact board I used can be found here https://hackerboxes.com/collections/past-hackerboxes/products/hackerbox-0030-lightforms

I used both of these projects to make a working version for a WeMos NodeMCU  V3 with ESP8266 12E. When I tried to use the original version of MorphingClockRemix, the WiFi would not work if the refresh rate was too high and if I lowered the refresh rate then the WiFi would work but the display couldn't draw fast enough and it was very obviously flashing.

Major differences:
- This code does NOT use the NTPClient Lib https://github.com/2dom/NtpClient
- When getting the weather conditions it matches the icon code instead of the description
- Added animated weather for fog/haze in day and night, clear night sky with twinkling stars, partly cloudy day and night,         and overcast day and night

Issues:
- The weather is currently set to update every 30 minutes. When the weather updates it freezes the screen for 10 - 15 seconds 
  and then redraws. Using the original code I was unable to get the weather data to reliably pull.

![alt text](https://raw.githubusercontent.com/j3rmbob/MorphingClockRemix/master/main.gif?raw=true)

- 12/24h time format
- date format and display below the clock
- Morphing clock code/logic is kept almost as is from https://github.com/hwiguna/HariFun_166_Morphing_Clock
- WiFiManager code/logic is also from https://github.com/hwiguna/HariFun_166_Morphing_Clock - the password for connecting to ESP   AP is: MorphClk
- it uses TinyFont and TinyIcons as my own implementation
- it uses openweathermap.org so you'll need a free account for the weather data (sync every 5min or so)
  !! you'll need to update the apiKey and location variables (around line 300)
- metric or imperial units support for weather data display above the clock
- it uses animated icons for weather: sunny, clear night, partly cloudy day, partly cloudy night, overcast day, overcast night, 
  rain, thunder, snow, haze/fog day, haze/fog night
- temperature and humidity change color based on (my personal) comfortable values

Sunny clear sky

![alt text](https://raw.githubusercontent.com/j3rmbob/MorphingClockRemix/master/sunny.gif?raw=true)

Night clear sky

![alt text](https://raw.githubusercontent.com/j3rmbob/MorphingClockRemix/master/clear_night.gif?raw=true)

Partly cloudy day

![alt text](https://raw.githubusercontent.com/j3rmbob/MorphingClockRemix/master/partly_cloudy_day.gif?raw=true)

Partly cloudy night

![alt text](https://raw.githubusercontent.com/j3rmbob/MorphingClockRemix/master/partly_cloudy_night.gif?raw=true)

Overcast day

![alt text](https://raw.githubusercontent.com/j3rmbob/MorphingClockRemix/master/overcast_day.gif?raw=true)

Overcast night

![alt text](https://raw.githubusercontent.com/j3rmbob/MorphingClockRemix/master/overcast_night.gif?raw=true)

Rain

![alt text](https://raw.githubusercontent.com/j3rmbob/MorphingClockRemix/master/rain.gif?raw=true)

Thunder

![alt text](https://raw.githubusercontent.com/j3rmbob/MorphingClockRemix/master/thunder.gif?raw=true)

Snow

![alt text](https://raw.githubusercontent.com/j3rmbob/MorphingClockRemix/master/snow.gif?raw=true)

Fog/haze day

![alt text](https://raw.githubusercontent.com/j3rmbob/MorphingClockRemix/master/fog_haze_day.gif?raw=true)

Fog/haze night

![alt text](https://raw.githubusercontent.com/j3rmbob/MorphingClockRemix/master/fog_haze_night.gif?raw=true)

tested ONLY using the NodeMCU variant listed as NodeMCU V3 (ESP-12E Module) in Arduino Studio

provided 'AS IS', use at your own risk
