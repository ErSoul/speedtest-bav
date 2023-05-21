# Speedtest Bandwidth Averager

## Description

This script will average the download/upload speeds for the different times of the day, from all the output (as CSV) of the [speedtest-cli](https://github.com/sivel/speedtest-cli) utility.

You can generate another CSV with the desired data so it'll be easier to use for another use cases. And you can see a chart to understand at which time of the day you're getting the best bandwidth.

## Setup env

Install the needed dependencies with:

`python -m pip install -r requirements.txt`

Then you have to generate the required CSV file that we'll use as input. For that, you have to download the _speedtest-cli_ utility, and add an entry to your _crontab_. You can use whatever interval suits you, but in general you'll want to execute the test every 30 minutes:

`*/30 * * * * /usr/bin/speedtest --csv >> /home/pi/speedtest-runs.csv`

## Usage

After you have enough data, you can visualize in a chart the average bandwidth for a given time of the day with:

`./speedtest-bav.py -d /path/to/csv`

Or you can generate a new CSV file with the averages for each time of the day:

`./speedtest-bav.py /path/to/csv -o /path/to/output/file`
