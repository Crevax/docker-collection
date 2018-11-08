# Pi-Hole Scripts

Recently decided to purchase a [Raspberry Pi](https://www.raspberrypi.org/) and decided on setting up [Pi-Hole](https://pi-hole.net/) as my first project. They provide an [official image](https://hub.docker.com/r/pihole/pihole/), which makes the process a lot simpler.

I had issues trying to get `docker-compose` to run on my Pi (using Raspbian Stretch Lite), so a bash script was used instead. Thankfully the Pi-Hole team already had a [script](https://github.com/pi-hole/docker-pi-hole/blob/master/docker_run.sh) establish, which made my work easier.

There were just a couple tweaks I needed to make to satisfy my person preferences.

- Use `#!/usr/bin/env bash` instead of `#!/bin/bash` to make it more portable (not every system has `bash` set up in `/bin`)
- Remove the IPv6 configuration since that's not a concern of mine
- Use a Docker-controlled volume instead of binding to the host
- Reference a specific version of the image so updates don't catch me off guard
