## Introduction

The Dars Recorder is an Application that integrates with OBS [https://obsproject.com](https://obsproject.com)

The goal is to setup a Schedule for the Lessons done by the Imam or other members of the community. At the Masjid Khaled Ben Walid we have lessons after Fajr prayer, Dhuhur Prayer and Isha prayer for about 20-30 minutes.

What this automation does is it starts recording at specified schedules based on the Iqama API that we use, so:

- Starts Recording at one of the Prayers above
- Stops Recording 1 hour later

The scheduling can be setup for the day of the week for special cases like the Jumuaa prayer which only occurs on Fridays and records for 2 hours instead (for the 2 Khutbahs)

## Setup

### Download Release

To setup the Dars Recorder (the cli is called `darsrec`), go to the release page and install the latest based on your operating system: [https://github.com/ccil-kbw/robot/releases](https://github.com/ccil-kbw/robot/releases)

Unpackage and move the file to an appropriate location (e.g `/usr/local/bin/darsrec`)

### OBS WebSockets

Enable WebSockets on the OBS application and note down the password to log in there.

### Run darsrec

- Open a Terminal and `export OBS_WEBSOCKET_PASSWORD=YOUR_WEBSOCKET_SECRET`
- Run `darsrec`

_NOTE: We strongly recommend keeping the software in the same network as your OBS application, either a server aside or on the same machine._
_NOTE2: You can either use [nohup](https://en.wikipedia.org/wiki/Nohup) or create a service similar to the one in the Discord Bot documentation_

## Roadmap

At the moment we are in the Alpha and stabilization phase, everything is currently hardcoded in the software itself, so:

- Use a configuration file to setup the Schedule (Delta of Iqamas or Specific week days/times)
- Add an API for admins to see what's going on (READONLY), this is simply for visibility
