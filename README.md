# homebridge-weather-station

This is a weather station plugin for Nfarina's [Homebridge project](https://github.com/nfarina/homebridge),and is a fork of [homebridge-wunderground](https://www.npmjs.com/package/homebridge-wunderground). This fork combines all characterstics into a single service, exposes the current weather conditons, and automatically updates every few minutes.

You can use these values as conditions for triggers or just look at them via HomeKit enabled Apps on your iOS device or even ask Siri for them.

## Weather Conditions

Currently, the current weather conditions are exposed in two properties, `WeatherCondition` and `WeatherConditionValue`. `WeatherCondition` is a read-only string representation of the current weather conditions, and can be one of the Forecast Description Phrases listed on this [page](https://www.wunderground.com/weather/api/d/docs?d=resources/phrase-glossary).

`WeatherConditionValue` is an enum value that currently represents one of three values:

| Condition              | Enum Value			                                                      |
| -------------------    | -------- |
| Other   		         | 0 |
| Rain  			     | 1 |
| Snow			    	 | 2 |

You can combine this with the [homebridge-suncalc](https://github.com/kcharwood/homebridge-suncalc) to create rules that turn on and off the lights when its raining during the day.

# Installation

1. Install homebridge using: npm install -g homebridge
2. Install this plugin using: npm install -g homebridge-weather-station
3. Update your configuration file. See the sample below.

All you need now is a developer key for Weather Underground which can be easily created [here](http://www.wunderground.com/weather/api/).

# Configuration

Configuration sample:


Add the following information to your config file.
Make sure to add your API key and provice your city or postal code.

```json
"accessories": [
	    {
	      "accessory": "WUWeatherStation",
	      "name": "Weather Station",
	      "key": "XXXXXXXXXXXXXXX",
	      "location": "78613"
	    }
    ]
```

Location can be any value that wunderground is able to associate with a known location (city, state, zip, etc) 
