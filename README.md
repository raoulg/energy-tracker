# energy-tracker

A simple script (meant to be run via cron) that tracks your Mac laptop's energy usage in watt hours.

**NOTE**: This will only run on Mac.


## Installation

To start, copy the energy tracking script into the correct folder:

```bash
sudo cp log-power-usage.sh /usr/local/bin/log-power-usage.sh
```

Next, install the cron script which will run the energy tracker once per minute:

```bash
crontab -l > cron-new
cat cron >> cron-new
crontab cron-new
rm cron-new
```


## Viewing Usage Data

Once installed, the energy tracker will log all energy consumption to the file `~/.cache/energy-tracker/energy-log.txt`.

This file will look something like this:

```text
timestamp,wattage,wattHours,uuid
2024-04-13T12:02:35Z,8.46427726,.14107128766666666666,8D154220-45E6-5C0D-9753-3DAF9F757909
2024-04-13T12:18:01Z,10.1954079,.16992346500000000000,8D154220-45E6-5C0D-9753-3DAF9F757909
2024-04-13T12:19:01Z,9.24522876,.15408714600000000000,8D154220-45E6-5C0D-9753-3DAF9F757909
2024-04-13T12:20:00Z,9.16311264,.15271854400000000000,8D154220-45E6-5C0D-9753-3DAF9F757909
```

Each line contains a timestamp, the amount of wattage being used at the time of sampling, the amount of watt-hours being used, and the uuid of the Mac.
