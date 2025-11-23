---
title: Voicelines
date: 2025-11-23
tags: ['chat']
dependencies: ['netstream']
link: 'https://github.com/mage-tearz/ix-plugins/tree/main/voicelines'
author: 'magetearz'
---

A plugin that lets your character chain together voice lines in a single chat message.

## API preview
```lua
--- Register a voiceline category
-- @string id
-- @fun(client: player): nil canUse
-- @fun[opt=nil](client: player, sounds: table, chatType: string): nil modify Edit the voiceline table
ix.voice.RegisterClass( id, canUse, modify )

--- Which voiceline classes does the player have
-- @player client
-- @treturn table Classes available
ix.voice.GetClasses( client )

--- Register a new voice line for use
-- @string class Voiceline category created by ix.voice.RegisterClass
-- @string trigger Phrase that triggers the voice line
-- @string textReplacement What replaces the trigger phrase in chat
-- @string|table soundPath Sound file that is played. If this is a table, it will choose randomly.
ix.voice.Line( class, trigger, textReplacement, soundPath )
```
## Usage example

```lua
-- our beep sounds
local METROCOP_BEEPS = {
    on = {
        "npc/metropolice/vo/on1.wav",
        "npc/metropolice/vo/on2.wav"
    },
    off = {
        "npc/metropolice/vo/off1.wav",
        "npc/metropolice/vo/off2.wav",
        "npc/metropolice/vo/off3.wav",
        "npc/metropolice/vo/off4.wav"
    },
}

-- create a new voiceline class
ix.voice.RegisterClass(
    -- name of our new voiceline class
	"metrocop",

    -- restrict usage to metrocops only
	function( client )
		return client:Team() == FACTION_POLICE
	end,

    -- modify the sound list before it's all played
	function( client, sounds, chatType )
        -- add the 'on' and 'off' beeps to the start and end of the sound list, respectively
		table.insert( sounds, 1, { ( table.Random( METROCOP_BEEPS.on ) ), 0 } )
		sounds[#sounds + 1] = { ( table.Random( METROCOP_BEEPS.off ) ), nil, 0 }
	end
)
```

## License
```
This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or
distribute this software, either in source code form or as a compiled
binary, for any purpose, commercial or non-commercial, and by any
means.

In jurisdictions that recognize copyright laws, the author or authors
of this software dedicate any and all copyright interest in the
software to the public domain. We make this dedication for the benefit
of the public at large and to the detriment of our heirs and
successors. We intend this dedication to be an overt act of
relinquishment in perpetuity of all present and future rights to this
software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.

For more information, please refer to <https://unlicense.org>
```