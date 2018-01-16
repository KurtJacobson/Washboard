# Weather Dashboard: Washboard

A skin for the [weewx](http://weewx.com/) weather system.  It utilizes [Bootstrap](https://getbootstrap.com/), and [chartist.js](https://gionkunz.github.io/chartist-js/) to render a mobile friendly weather webpage.

[Taking a look at a demo](https://jquagga.github.io/Washboard/) will likely give you a sense of what this skin does far better than what I could write here.  It was built around the concept that the primary user of this weather data is you, the weather station owner.  It replaces the weewx generated images with chartist graphs which are bigger and hopefully easier to read.  With bootstrap, the webpage works on a phone, tablet, or computer.

:warning: - So it should be noted this is very new and I haven't had the opportunity to test every aspect of the code.  For example, it's January so I don't know if the Heat Index code is going to work yet.  My weather station doesn't report UV or solar radiation so neither of those have been thoroughly tested.  If you MUST have accurate data, I'd run this skin along with the standard.  At least until this gets more testing.  Still, it's a lot of fun!

## Getting Started

Generally speaking, all you have to do is download a copy of this repository to your weewx/skins directory, change your skin in weewx.conf, and then restart weewx.

### Prerequisites

What things you need to install the software and how to install them

* A functional weewx installation
* Matthew Wall's [excellent forecast extension](https://github.com/weewx/weewx/wiki/forecasting) (optional) - required for the "current weather" icon.


### Installing

Assuming weewx is in /etc/weewx
```bash
cd /etc/weewx/skins
git clone https://github.com/jquagga/Washboard
```

Then edit /etc/weewx/weewx.conf to change the skin varible under:

```python
[[StandardReport]]
skin = Washboard
```

Finally restart Weewx

#### Configuring additional options
Now that you have the skin up and running, you may want to enable a few other things.  If you've installed the forecasting extension, you can configure the line

```python
forecast_source = NWS
```
It should support NWS, WU and other options supported by the forecast extension.  By default it is set to NWS.

The next two lines are if you want links the navbar for a NWS forecast or to the WU page for your weather station.  If you un-comment them, they should appear on the website.

## Built With

* [Bootstrap](https://getbootstrap.com/)- The web framework used
* [Chartist.js](https://gionkunz.github.io/chartist-js/) - Javascript library rendering the charts
* [weewx](http://weewx.com/) - Weather Station software making this possible
* [weewx-forecast](https://github.com/weewx/weewx/wiki/forecasting) - weewx extension fetching forecast data
* [weather-iconic icons](https://github.com/jackd248/weather-iconic) - I use these SVG for weather icons instead of the standard forecast icons which come with that extension.

## License

This project is licensed under the GPLv3 License - see the [LICENSE](LICENSE) file for details.  Generally I'm more of a MIT License guy at heart, but I built this on a lot of GPLv3 code so I just went with that.

It's a web template.  Take it and make it your own!
