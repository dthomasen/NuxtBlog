---
title: 'Detect stale sensors in Home Assistant'
image: 'stale.jpg' 
---

I have an automation that turns the office light on and off depending on the state of my Macbook. In some scenarios however, the state isn't updated (forced turned off, empty battery etc.) 
<!--more-->

To fix this I've written a template to trigger an automation after 2 hours of silence (no state published) from the sensor.

## Time date sensor
It uses the time_date sensor - So make sure that it's enabled (Add it in the Home Assistant config).
```yaml
platform: time_date
display_options:
  - 'date'
  - 'date_time_iso'
  - 'time'
  - 'date'

```

### Last changed
We use the last_changed property that all sensors have:

```jinja2
{% if as_timestamp(states.sensor.{{CURRENT_DATE_TIME_SENSOR}}.last_updated) - as_timestamp(states.binary_sensor.{{SENSOR_NAME}}.last_changed) > {{MINUTES_TO_WAIT}}*60 %}
true
{% else %}
false
{% endif %}
```

## Example
```jinja2
{% if as_timestamp(states.sensor.date_time_iso.last_updated) - as_timestamp(states.binary_sensor.macbook_pro_tilhorende_dennis_active.last_changed) > 120*60 %}
true
{% else %}
false
{% endif %}
```