# Discord Bot

## Setup
First to Setup a Bot in your Server please follow the official documentation here: [https://discord.com/developers/docs/getting-started#step-1-creating-an-app](https://discord.com/developers/docs/getting-started#step-1-creating-an-app)

From there you will be able to get your Server's ID, we will name it `GUILD_ID` in the Installation phase. You'll also need your Bot's Token that we're calling `BOT_TOKEN`

## Installation

_Bismillah_

### Download Release

To download our Discord Bot, go to our releases page and download the latest `iqamabot` with the distribution of choice.

We currently build for MacOs (darwin) and Linux, if interested in other distributions please let us know.

[https://github.com/ccil-kbw/robot/releases](https://github.com/ccil-kbw/robot/releases)

Download the tool and put it in `/usr/sbin/iqamabot`

To have the service running in the background you can follow these steps: 


### [Daemon Mode](https://en.wikipedia.org/wiki/Daemon_(computing))

#### Service File

Copy this and put it in `/etc/systemd/system/iqamabot.service`:

```
[Unit]
Description=iqamabot

[Service]
EnvironmentFile=/etc/iqama.d/conf.env
ExecStart=/usr/sbin/iqamabot -guild $GUILD_ID -token $BOT_TOKEN

[Install]
WantedBy=multi-user.target
```

#### Environment

Create the environment configuration and put the information about your Discord Bot in it `/etc/iqama.d/conf.env`:
```
GUILD_ID=YOUR_GUILD_ID
BOT_TOKEN=YOUR_BOT_TOKEN
```

#### Start and Enable

Start and Enable the Service:

```
sudo systemctl start iqamabot
sudo systemctl enable iqamabot
```

