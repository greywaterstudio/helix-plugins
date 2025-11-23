---
title: TFA support
date: 2025-11-23
tags: ['combat', 'item']
link: 'https://github.com/bruck-dev/helix-plugins/tree/main/tfa_support'
author: "bruck"
---

Yet another gun base supported on my weapon customization architecture. This plugin adds support for TFA attachments and weapons as items integrated into Helix in an immersive way, along with a server config-level customization suite to quickly adjust options such as free attachments or visible crosshairs.

## Features as of now
- Full support for weapon and attachment items.

- Attachments that are tied to items will now require and consume an item when put on a weapon, and be returned when removed. They can also require a tool to use, which is defined in the attachment item file as just an item unique ID.

- Weapons have their attachments saved as item data, so they can be shared between players and they will persist on server restart. Can also have default set values - see the tfa_weapons sh_example.txt

- Optional restriction that attachments can only be used at weapon workbenches. Compatible with my ARC9 and ArcCW workbenches.

- Optional automatic item generation. Don't recommend using it as TFA weapons and attachments do not have descriptions (largely, it's a bit arbitrary for attachments).

As always, you are allowed to modify and redistribute this plugin however you wish, provided that it is not for commercial use and that I am properly credited for my work. I also accept bug reports - please open an issue on the GitHub repo and I will get to it when I have a chance. This is probably the last weapon base I'll do, as I don't think anyone actually uses MWBase. Right? Right??


## License
This work is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License. To view a copy of this license, visit http://creativecommons.org/licenses/by-nc-sa/4.0/.