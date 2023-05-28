# Polybar: Weather Module

![Weather Module](/other/images/weather-module.png)

A small and simple weather module for Polybar, written in Python and using the [OpenWeatherMap API](https://openweathermap.org/api) to fetch weather data.

## Dependencies

The module uses the following Python modules:
- [requests](https://pypi.org/project/requests/)

The module also uses the following fonts:
- [Feather Font](https://github.com/AT-UI/feather-font)

## Installation

Clone the repository to your polybar configuation directory, which is usually located at `~/.config/polybar/`.
After that, you should add a new module to your Polybar configuration file, which is usually located at `~/.config/polybar/config`. The module should look like this:

```
[module/weather]
type = custom/script
exec = python ~/.config/polybar/polybar-weather/weather.py $HOME/.config/polybar/polybar-weather
interval = 900 
format = <label>
label = %output%
format-padding = 2
format-foreground = ${color.foreground}
format-background = ${color.primary}

```

You can also find the module [here](/module.ini). Here a short explanation of the module options:
- `exec`: The path to the Python script. If you choose to clone this repository to a different directory, you should change this paths accordingly.
- `interval`: The interval in seconds in which the module should update the weather data. Currently, I recommend to set this to 900 seconds (15 minutes), to not overload the OpenWeatherMap API.
- Other options are basic formatting options and can be changed to your liking, so that it fits your Polybar configuration.


## Configuration

The module can be configured by editing the `config.ini` file. The file contains the following options:

- `APPID`: Your OpenWeatherMap API key. You can get one [here](https://openweathermap.org/).
- `LAT` and `LON`: The latitude and longitude of the location you want to get the weather data for.
- `UNITS`: The units in which the weather data should be displayed. You can choose between `METRIC` and `IMPERIAL`.

## License

This project is licensed under the MIT License - see the [LICENSE.md](/LICENSE.md) file for details. Note that this only applies to my code. The modules I use are licensed under their respective licenses.
