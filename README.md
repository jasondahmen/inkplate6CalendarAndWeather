# inkplate6CalendarAndWeather
Calendar and Weather for my inkplate6

<img alt="Inkplate6" src="https://github.com/jasondahmen/inkplate6CalendarAndWeather/raw/main/README_pics/eInkCalendar.jpg" width="600">

# Assumptions
  - I believe that the ESPHome yaml coding can do some calculations but does not have the heavy lifting power that Home Assistant has for this reason much of the data being passed to the ESPHome Inkplate is just raw text. Because of this you must have sensors that are based from a "template" within home assistant. To get the sensors to update in "realtime" (more like a schedule) you must add a trigger of every X number of minutes or hours to recalculate the values.
# Prerequisites
  - ESPHome
    - Is installed on Home Assistant and you can push code.
    - USB Driver
      - I downloaded this:(https://dl.espressif.com/dl/idf-installer/esp-idf-tools-setup-online-2.24.exe) to push my first esphome via USB, after that all code was pushed wirelessly.
    - I have a cert on my Home Assistant box so setup was easy, unfortunately I do not know the work around method for http. Please do this on your own.
  - Integrations
    - ***CHANGE THE TEMPLATES YAML*** if you are using a different integration.
    - TEST with "Developer tools" -> "Services" -> weather.get_forecasts
    - TEST with "Developer tools" -> "Services" -> calendar.get_events
      
    - OpenWeatherMap
      - I have the "OpenWeatherMap" integration setup for "onecall_hourly"
    - Meteorologisk institutt (Met.no) DOUBLE CHECK name could be different
      - weather.home OR weather.forecast_home
    - Google Calendar
      - calendar.CALENDAR_ENTITY
  - Fonts
    - You will need download "Helvetica.ttf" and "materialdesignicons-webfont.tff" (case sensitivity matters for the code) and store them on with your ESPHome folder within Home Assistant.
  - Knowledge
    - Understand the basics of template values for arrays and attributes.
# Hardware
  - I purchased a Inkplate 6 (https://soldered.com/product/soldered-inkplate-6-6-e-paper-board/) but with enough tweaking of code and display you should be able to mirror something similar.
# Notes
  - If you are using attributes in your template ALL "attribute_templates" must return values if not the calculation for them will not work.  Because of this all calendar entries needed to be individually added.
# To Do
  - Look into wake button on for GPIO and setting up a script
  - Set display to partial update by default

# Support Me
 - If I saved you some time consider supporting me: https://www.buymeacoffee.com/jasondahmen

# Citation and Inspiration
  - @jkmaxwell (https://github.com/jkmaxwell/Inkplate-ESPHome-Family-Calendar) For the Calendar code
  - @techdregs (https://github.com/techdregs/E-Paper-DashBoard) For the coding of action and response vaules
