---
title: Immersive radio
date: 2025-11-23
tags: ['chat']
link: 'https://github.com/bruck-dev/helix-plugins/tree/main/radio'
author: "bruck"
---

This plugin integrates radio and radio stations into Helix in a somewhat more immersive way. I also designed declaration of stations and radio items to be as easy as possible while still fitting within the architecture I personally would use.

## Features
- Classic radio system with support for multiple different radio items, each with their own frequency bands, interaction sounds, one-way only, etc.

- Support for /Radio, /RadioWhisper, /RadioYell, which change color and eavesdrop radius depending on the command used.

- Integrated support for languages, where /RadioLang and W/Y variants will be created and allow a language to be passed as a command argument to use to determine what language to radio in.

- Support for stationary radio entities that can send/receive messages. Configuration options can be viewed inside of the example entity files provided. Stationary radios can also turn to music/audio file radio stations, described in the following line.

- Radio stations. You can declare a frequency as a radio station, disabling it from being used as a radio comms frequency. Radio stations can be either a web radio stream or a playlist of local files. Since web streams are pulled live, you just need to specify that the station is a stream and the link to use, and it'll work out of the box. If a local file station, on server start a radio station instance will be created that will select a random starting track; it will then cycle through them all in a row, forever. Tuning into a local file station while a track is playing will jump to the current time of the track as if you've tuned in live!

- Integrated Extended Radio garbling.

As always, you are allowed to modify and redistribute this plugin however you wish, provided that it is not for commercial use and that I am properly credited for my work. I accept bug reports - please open an issue on the GitHub repo and I will get to it when I have a chance.

## License
This work is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License. To view a copy of this license, visit http://creativecommons.org/licenses/by-nc-sa/4.0/.