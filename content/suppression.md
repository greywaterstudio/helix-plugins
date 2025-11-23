---
title: Suppression
date: 2025-11-23
tags: ['combat']
link: 'https://github.com/bruck-dev/helix-plugins/tree/main/suppression'
author: "bruck"
---

This plugins adds a simple suppression system, where the player's screen will become progressively more blurred as more fire is received. Supports a number of configuration settings, including if a heartbeat effect should play and the required minimum radius for a bullet to suppress a player.

## Features as of now
- Suppression system with a basic ix.util blur effect and vignette that becomes progressively stronger as more suppression is accrued via bullets or explosions. The amount is tied to the damage that was/would be done, so players will probably suppress you considerably more than NPCs will. I tried to do some math to balance this, but it may be pretty high still.

- Automatic suppression fade when the player has gone a few seconds without taking any fire.

- Optional heartbeat effect that gets progressively faster as the suppression level increases. This requires the sounds in the requiredassets/ directory to be installed on the client to work, so make sure it's in your server content or disable it for performance.

- Configurable suppression radius, fade delay time, and if suppression can be accrued inside of vehicles.

As always, you are allowed to modify and redistribute this plugin however you wish, provided that it is not for commercial use and that I am properly credited for my work. I also accept bug reports - please open an issue on the GitHub repo and I will get to it when I have a chance.

## License
This work is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License. To view a copy of this license, visit http://creativecommons.org/licenses/by-nc-sa/4.0/.