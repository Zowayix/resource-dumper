For my own evil purposes, this is a list of some games, and how they store their data. So you know how to rip them I guess. I just woke up I don't know how to describe things. This document assumes you know what a resource is and all that sort of thing.

TODO: This should just be a wiki page actually

## Commmon formats

### MADH
This resource is just a MADH file, which Resource Dumper extracts nicely. You just need to put the data of this resource as the data fork of a new file, change the file type to MADH and the creator to PlayerPRO, and then you can listen to it or convert it.

PlayerPRO is open source and once extracted with Resource Dumper it's just a data fork, so it'd be theoretically possible to make a MADH player on Windows/Linux/etc and you wouldn't need conversion. Nobody's done that though. I think.

### snd resource
I'm not sure of the format, it's not necessarily raw streamed audio as you might think, nor are they just snd files you can put in the System suitcase for use as alert sounds. Brian's Sound Tool can extract them (to WAV/AIFF), but it'll just give you every single sound resource at once. i suppose Resource Dumper would do that too with the way it's currently designed.

### nVir
If you see this resource you have the nVir.A virus! Get rid of it, silly.

### System sound
Not sure what the proper name for these are, but these are the ones with a type of sfil and a creator of movr that you can put in your System suitcase and use as alert sounds, or open in the Finder to hear them. I don't know the exact format, though. But if you open one with ResEdit, you get a snd resource, so that's interesting.

### PICT resource
I should find the format of these and how to convert them to BMP or PNG or similar...

### PICT file
Not quite a PICT resource, they have no resource fork actually. They have a file type of PICT and can be opened by ClarisWorks and GraphicConverter and other various things, PictureViewer (from QuickTime) should work if you have nothing else.

### cicn resource
TODO figure out this one too, since it seems to pop up a lot

### icl8/icl4/ics8/etc.
Almost every game and application will have at least one of these, since it's where the icon that you see in the Finder goes.
TODO figure out this one as well

### AppleScript
Just putting this here so one day I'll be motivated to find a way to decompile AppleScript applications...

--------
## A Day at Work
Unknown. Uses the Cocoa engine (the one that was an engine before Cocoa was an appliction framework. It's okay to be confused, just know that the engine's called Cococa, and there's a DITL resource which credits the "Cocoa Autoplayer Engine" copyright Apple 1998 written by Peter Jensen). CanOpener can't even see anything except a picture of a bird thing on a hoverboard used in that DITL.

## Ares
### Text
The main executable contains the shareware nag dialog in the TEXT/styl resources 900, 901, and 902. 6500 is the credits, which seems to have a few formatting directives in there and doesn't even need to be a styl resource at all.

STR# resource 750 is named "cheats", but they look like garbage. But hey, they could be actual cheat codes, I haven't really played this game.

### Graphics
PICT 900 in the main executable is the Ambrosia logo from the splash screen, and 502 is the title screen.

Ares Sprites logically would contain the sprites, but when you open it up you just get a lot of SMIV resources. The names would suggest these are indeed the sprites, but I don't know the SMIV format yet.

### Music
MADH resources in Ares Sounds (in Ares Data f folder). If you just want to listen to it Ambrosia has mp3s on the game's addons page.

### Sound effects
They're all snd resources inside Ares Sounds.

## Avernum
### Text
There's a lot of interesting things in the STR# resources in the main executable. Spell names and special abilities and whatnot.

### Graphics
The main executable has a bunch of ppat resources which seem to be the tiles used in the game.

Avernum Character Graphics is where it gets fun, as you have a bunch of sprite sheets in PICT resources, divided by a 1 pixel black border. And some big character pictures too. Avernum Graphics also contains a whole bunch of PICTs that are sometimes also divided by black 1px borders, and seems to have all the items and UI elements in the game.

### Music
Opening music is snd resource 20022 in Avernum Sounds.

### Sound effects
All snd resources inside Ares Sounds.

## Bub & Bob
### Music
Stored in the main executable, snd resources 128-132. The fish and death jingles are 134 and 138 respectively.

### Sound effects
snd resources inside main executable.

### Graphics
Title screen is PICT resource 129 in main executable. Game over screen is 130, highscore list header is 151, you get the idea, there's a bunch of UI elements in there.

Tiles are ppat resources inside Bub & Bob Levels. Adorable sprites are cicn resources in Bub & Bob Sprites. Larger graphics like bonus fruit is stored as PICT resources in Bub & Bob Sprites.

### Game data
Levels are LEVL resources in Bub & Bob Levels. I'm not sure of the format but they all seem to have a size of 1090 bytes.

Bub & Bob Dreamland is an alternate level set I think, so it also has LEVL resources (and ppat for the tile graphics).

## Bubble Trouble
### Graphics
PICT resources in the main executable have the Ambrosia logo, the title screen logo, the "By Alex Metcalf & David Wareing" graphic, the "Press Caps Lock to Resume" graphic, and... a poem? Is that unused?

There's a TMPL resource in there which lets you edit Rect resources, which seems to be used for telling the game where to render UI elements to (what size and position).

Super ResEdit says the ppat resources in BT Levels are corrupted, so I guess it's a different format than the usual. Whatever they're used for here.

Sprites would be in BT Sprites, but they're in a weird format. There's some btSP resources which don't seem to be in any particular normal format used by normal people.

Title screen graphics and UI elements are PICT resources in BT Titles. There's also some PICT resources with IDs 9001 and 9002 for green text and yellow text respectively.

### Text
STR# 129 in main executable has a list of names to the other files needed by the game, so I wouldn't touch it, but it's interesting. The other ones are just errors and preferences dialogs text, but what's interesting is 4000, which contains a single string:  
"Heh! Do you really think we'd hide the cheat codes in here?"

### Sound effects
snd resources in BT Sounds.

### Game data
Levels seem to be stored in MAZE resources in BT Levels, which is a format that I'm not quite sure about, but they're also 176 bytes. There's also corresponding LEVL resources which are presumably not the same as Bub & Bob LEVLs, and are all 64 bytes.

### Music
MADH files in the BT Music folder. The creator code is set to PlayerPRO already.

## Captain Bumper

### Music
snd resources in main executable.

### Sound effects
Also snd resources in main executable.

### Graphics
All the title screen graphics and sprites and whatnot are PICT resources in the main executable.

## Where in the World is Carmen Sandiego? Deluxe

### Sound effects
There's some in snd resources in Sound.rsrc (in the misc resources folder), but then there's also Sound2.rsrc which has some csnd resources.

### Music
testsong.rsrc contains some MIDI resources, which are probably just MIDI files in resource form, but I haven't tried dumping them yet. There's also instruments in the snd resources there, plus INST resources which seem to describe the instruments, and a TMPL for editing SONG resources which seem to contain information for how the MIDI engine should play the songs.

### Graphics
Title screen graphics are PICT resources in the main executable.

The animations would be stored in the anims folder, and there's .anX files in each subfolder there, but I'm not sure what that format is. All I can figure out is that there's a STR# resource that seems to contain which sounds are played in that animation, and a clut for the palette. The PBIT resources possibly do something.

picts1.rsrc, picts2.rsrc, picts3.rsrc, and picts3b.rsrc all contain clut resources and PBIT resources. Still dunno what PBIT is.

There's graphics for the phone in phone anim.rsrc, and profiles.rsrc and screen.rsrc have some UI elements. Those are all in PICT resources.

### Text
carmen.rsrc has a whole lot of fun STR# resources, which seems to have UI elements, clues, names of characters... damn well everything.

country.rsrc has a list of countries and cities, and educational information about those countries and cities (cool!), but the STR# resources which have those are unnamed so there doesn't seem to be organization there. There's also some INFO resources, which is a weird binary format, but I can see that each INFO resource has the name of a currency and some colours (colours used in that country's flag I guess?)

## Cave Dig 3
### Music
The Cave Dig Music folder in the Data folder has some QuickTime movies, which are just mp3s in a QuickTime container. You can extract them to actual sound files using QuickTime Player (might need Pro version) by using Export... and then Sound to Wave (or other things depending on what QuickTime components you have). VLC should be able to just open them though if you give them a .mov extension.

### Graphics
Various title screen graphics and what I think is cutscenes and pics of the developers are all in PICT resources in the Cave Dig Classic executable (in the Data folder), but what may be most interesting is PICT 2000, which has all the sprites.

### Sound effects
snd resources in Cave Dig Classic executable.

## Change My Image
### Graphics
Title screen graphics is PICT 128 in the main executable. Also there's an outline of a face.

The hairstyles are in r/long r/short s/long s/medium etc whatever inside the HairData folder, and then there's some png files. There's a way to add new hairstyles I think, Infinisys's website says something about that.

Models are just JPEG files inside the Models folder.

### Text
The STR# resources in the main executable seem unorganized, but there's error messages, help messages, UI text, and stuff involving shareware reminders.

## Chronicles of Ekan
### Sound effects
System sound files in the Data Files folder. There's also snd resources in the main executable, which seem to be just phone dial tones and instuments.

### Music
MIDI files in the Data Files folder, but they're in a QuickTime container for no good reason (must be an old format or something because VLC can't play them, you have to extract them using QuickTime Player. Luckily you can just do Export and Sound to General MIDI)

### Game data
Hypercard stacks? Well okay then. So you can in theory just edit them with HyperCard.

### Graphics
There's some PICT files in the Data Files folder, as well as PICT resources in the Hypercard stacks.

## Cortex
### Graphics
Tiles are in ppat resources, as you might expect. Seems to be a recurring thing with games.

The rest of the graphics are naturally in PICT resources, except for the sprites, which are cicn resources.

### Music
snd resources, most are named "M1" "M2" "M3"... "M30" but some aren't.

### Sound effects
The snd resources that aren't music.

## Deathground Demo
(Some of these might be the same for the full game, I don't have the full game so I dunno)
Apparently there's a manual chapter called "Changing the Code" which contains information on a lot of this.
### Graphics
PICT resources in main executable contain an ad for the full game and other demo-related things.

Graphics for the characters are PICT resources in DG Player 1, DG Player 2, etc; they have what looks to be an alpha mask as well as the actual graphics. Some don't have any graphics except for a face, those ones are probably exclusive to the full game.

The rest of the graphics are PICT resources in DG Graphics.

### Sound effects
Voices for each character are in DG Player 1, DG Player 2, etc. as snd resources.

The sound effects and other voices are snd resources in DG Sounds. snd 1013 ("intro") seems to produce an I/O error when I try to play it, maybe it's too big for Super ResEdit to handle.

### Text
There's a biography for each character in DG Player 1, DG Player 2, etc. in the TEXT resource 128. The accompanying styl resource just makes it bold.

There's also some TEXT/styl resources in DG Data which describe the game world.

### Game data
Some of the TEXT resources in DG Data seem to describe the game modes in some kind of human readable description language.

DG Data has a few TMPL resources for editing various things, but they all seem to be invalid according to Super ResEdit, which complains about LCNT being an invalid field type.

### Movies
The animated Freeverse logo is a QuickTime movie called "Freeverse Movie" in the Data folder. VLC can play it just fine.

## Double
TODO

## Escape Velocity
There's a program by the name of [EV-Edit](https://www.macintoshrepository.org/2215-ev-edit-2-1) which can edit the game data, but you can do all that with ResEdit too.
TODO: Describe the game data resources anyway (you have sÿst = star systems, spöb = planets/moons/etc, shïp = ships, dësc = various text, wëap = weapons, oütf = equippable items (IDs seem to correspond to wëap IDs if they're weapons), düde = generic NPCs, gövt = factions, mïsn = missions, përs = named NPCs, öops = random events/news items, nëbu = nebulas (or is it nebulae?), flét = fleets, jünk = cargo types; these all have TMPL resources in EV Data, there's also something called a dsïg which doesn't seem to be used and also spïn and spït which are described in EV Graphics)

### Music
snd resources in EV Music.

### Sound effects
snd resources in EV Sounds.

### Graphics
EV Titles contains PICT resources for the title screen UI, the litte door opening animation, the Ambrosia logo, the side panel UI in-game, the Interstellar News Network banner, and the various planets/moons/space stations/etc that you can land on.

EV Graphics also has PICT resources containing sprite sheets for ships and weapons and floating asteroids and explosions, planets/moons/etc (as they appear on the overworld), the image that displays on the in-game HUD when you select another ship, pictures of other ships when you talk to them, pictures for items/weapons in the shops, UI buttons, slot machine graphics, as well as duplicates of the spinning planet menu thingy and a rocky planet graphic from EV Titles. And nebulas.

The ppat resources in EV Graphics are used for map static when there's jammer inteference.

There's also TMPL resources in EV Graphics for spïn and spït, which describe the sprite sheets and count the total number of sprites respectively.

### Text
STR# resources in EV Data. There's some STR resources as well. The intro text is STR# 20000, with each line being a different string.

## Factory: The Industrial Devolution
TODO

## Fakie Flair Challenge 2002
TODO

## 3D Hearts Lite
TODO other stuff

### Music
MIDI inside a QuickTime container in Soundtrack folder.

## Burning Monkey Solitaire
TODO other stuff

### Music
MIDI inside a QuickTime container in Soundtrack folder.

## Frog Xing
TODO other stuff

### Music
snd resource 201 in main executable.

## Game Doctor
TODO

## GopherGolf
TODO

## Greebles
TODO (Music seems to be in MDAT resource)

## Gryphon Bricks
TODO

## Harry the Handsome Executive
TODO

## Holiday Lights
TODO bulbs etc (there's a guide included), pictures, anything else

### Music
MIDIs in a QuickTime container in the Music Files folder, but if you put your own plain MIDI files in there it'll still recognise them

## Zador
TODO other stuff
Uses the METAL engine, which has nothing to do with Apple's new graphics API

## Mavis Beacon Teaches Typing 5
TODO other stuff

### Music
\*.MID files in the Sounds folder, but they're actually AIFF files

## MemoryPICT
TODO

## Miniature Golf
TODO

## Nanosaur
TODO other stuff

### Music
AIFF files in Data\:Audio folder

## Realmz
TODO other stuff

### Music
ProTracker MOD files in Realmz Music folder, except for Outdoor Music which is an XM; most module players can play both formats anyway

The "Where to find more music files" text file there would imply that you can also put MADH, MIDI, and S3M formats in here and they'll be usable for custom scenarios or whatever; in the Plugs folder you see S3M, XM, IT, MED, MOD, OKTA, MADfg (whatever that is), and MTM plugs so it'd most likely support those

Also those modules aren't originally from this game

## Reckless Drivin'
TODO

## Royal Flush
TODO (I thought this had music but I don't see anything relevant)

## Sim Cinema Deluxe
TODO

## SimCity 2000
TODO (Music is not in a normal format, there's INST and MIDI and SONG and SMOD resources that all seem related to this, I think it uses MIDI with its own built-in player or something)

## SlopeRider
TODO

## The Trials of Achenar
TODO
It's a Hypercard stack but it puts its data in external files

## Tiger's Eye Pub
TODO other stuff

### Music
MIDI files in the Music folder. There's also a text clipping that informs you that you can put any QuickTime-compatible music file in there

## Ultima III
TODO other stuff

### Music
ProTracker MODs in the Ultima Music folder

## Vortex NG
TODO

## Wanderer I: The Cult of Misery
TODO

## Card 99
TODO

## Desert Trek
TODO

## Elf Forest
TODO

## MacSnack
TODO

## Mille Bornes
TODO

## Coloring Book
TODO

## Cube Strategy
TODO

## DoodleFish
TODO
This uses a common engine that I've seen in other text/clicky adventure games, but I don't know what it is, let's call it the Park Quest engine for now since that seems to be the most notable game

## Eric's Ultimate Solitaire / Eric's Solitaire Sampler
TODO

## Fluffy's Adventure
TODO

## Hang3000
TODO

## The Journeyman Project Turbo
TODO (the data itself would be on the CD)

## Pop-A-Penguin
TODO (Macromedia Director 4 engine, this is a minigame from Stay Tooned! with the same assets anyway)

## MacQubic
TODO

## Monopoly (Thomas E. Fosson)
TODO

## Pararena
TODO

## Scarab of RA
TODO

## SimTown
TODO (has the same INST/MIDI/SONG/SMOD shenanigans as SimCity 2000)

## Smashing Windows II
TODO other stuff

### Music
MADH resource 128 (only one), but it's not originally composed for this game, it's just [Airdance by The Wizard](https://modarchive.org/index.php?request=view_by_moduleid&query=121558)

## The Great LightBulb Adventure
TODO (Park Quest engine again)

## VirtualHamster
TODO

## WiggleWorks Demo
TODO

## 3 in Three
TODO ("3 puzzles" only has a version in its resource fork, the rest can only be seen in CanOpener etc)

## 3D Hearts Deluxe
TODO

## 3D Ultra Pinball: NASCAR
TODO

## Chuck Yeager's Air Combat
TODO

## Apeiron
TODO other stuff

### Music
snd resources in Apeiron Music

## Apple Company Store VR Demo
TODO

## AstroRock 2000 Demo
TODO other stuff
Might be the same for full game

### Music
AIFF files in music folder

## At the Carnival
TODO

## Avara
TODO

## Avernum 3
TODO (I suspect all 3 original Avernum games work the same way)

## Barrack
TODO other stuff

### Music
snd resources in Barrack Music

## Battleship (Craig Hoyt/Pyramid Software)
TODO

## Beat the Dragon
TODO

## Bugdom (shareware)
TODO other stuff
Probably same thing for full game

### Music
.aiff files in SWData:Audio

## Buried in Time Demo
TODO other stuff
Might be more music in full game?

### Music
"Music - opening" file is just an AIFF file

## Candy Crisis
TODO other stuff
Should be the same for 1.0 and 1.2 (open source re-release), the music is at least

### Music
.mod resource, all nicely named and credited. They should just be various module files (I haven't tried dumping them yet), depsite the name I know some of them are in .s3m format as they are in the Mac OS X/Windows version

## CartoonShy
TODO

## ChessWorks
TODO

## Chiral
TODO other stuff

### Music
snd resources in Chiral Music. It's really just one song, it's just split into two parts so that it can have an intro but loop seamlessly without playing the intro again.

## ChristmasTime
TODO
SuperCard engine

## ClarisWorks For Kids
TODO
Not really a game, but it'd be interesting to dig into the resources and data files (clip art, etc)

## CrashBall
TODO

## Cricket Demo
TODO
Probably works same way as full game

## Crystal Crazy Demo
TODO
Probably works same way as full game

## Cyberopoly
TODO

## Dart Board
TODO

## Dirt Bike
TODO other stuff

### Music
snd resource 15445 in main executable

## Monsters Inc. Wreck Room
TODO
Only have Bowling
Macromedia Director engine I think

## Dollhouse Time
TODO
HyperCard engine

## Doom (Shareware)
TODO
It'd be just in the WAD files really

## EA Kids - Eagle Eye Mysteries in London
TODO
I see some "Midi" resources in that resource fork but also a lot of csnd/INST/SONG shenanigans

## EV Override
TODO

## Faces ...Tris III
TODO
Yay INST/SONG resources my favourite also BGAS and PHAZ

## Ferazel's Wand Demo
TODO other stuff
Full game probably works the same way

### Music
AIFF files in Ferazel Demo Music folder

## Flight Unlimited Demo
TODO
Probably works same way as full game

## Foobar versus the DEA
TODO

## Food Chain
TODO other stuff

### Music
snd resource 1011

## Banshee
TODO other stuff (pretty simplistic)

### Sound effects
snd resources, 9130 is the main one

## Jared
TODO
Jared Choir probably uses the same data, Jared's Christmas probably just replaces the song and graphics

## Menu Madness
TODO

## Mr. Relaxer
TODO

## Galaxis
TODO

## Garcia's Guitars
TODO

## Gearheads Demo
TODO
Maybe works same way for full game?
The .mid files in the wav folder aren't MIDI files, and are only about 300 bytes

## George Stock Game
TODO

## Gerbils!
TODO

## Glider PRO
TODO other stuff
Source code may give insight into how the resources are used

### Music
snd resources in main executable with ID > 2000, seems to be one song split into multiple parts

## GoldPusher
TODO

## Grag & Thog Bonkheads
TODO

## IQ Test
TODO

## iTarget
TODO

## Jewelbox
TODO
There's a lot of snd resources that ResEdit can't play due to a "bad sound format"

## Jingle Bell Mac
TODO other stuff

### Sound effects
The Sounds folder contains a bunch of System sounds and you can add your own, when you select one in the application it replaces snd 27573 inside itself with that sound

## Josh's Apple Game
TODO

## Kid Pix
TODO
Not really a game, but it'd be interesting to dig into the resources and data files (clip art, etc)

## Kid Pix Studio Deluxe
TODO
Not really a game, but it'd be interesting to dig into the resources and data files (clip art, etc)

## Kid Pix Studio Deluxe 3
TODO
Not really a game, but it'd be interesting to dig into the resources and data files (clip art, etc)

## King's Quest V: Absence Makes the Heart Go Yonder
TODO
SCI engine
ScummVM supports the Mac version so its source may be useful

## Little Red Wagon
TODO
SuperCard engine

## Live & Kicking: Show Maker
TODO
Macromedia Director engine
Runs from the CD, a lot of the content is just there

## MacChess
TODO

## MacDo
TODO

## macloned
TODO other stuff

### Music
discloned.xm is right there and it's an XM module what more do you want

## MacPipes
TODO other stuff

### Music
snd 30000 in MacPipes Music

## Populous II
TODO

## MACrostrange
TODO other stuff

### Music
5tfina.mp3 in data folder

## Syndicate
TODO

## Theme Park
TODO

## ManicMinefields
TODO

## MegaSimpsonHomer
TODO

## MineSweeper Pro
TODO

## The Missions of Starship Reliant II
TODO

## Ms. MacPherson Demo
TODO
Maybe works same way in full game

## Fine Artist
TODO

## Creative Writer
TODO

## Mythos
TODO

## NameThatGame
TODO
Macromedia Director engine

## Odyssey: The Legend of Nemesis
TODO
"Music File" has an empty resource fork, but CanOpener can't find anything, and QuickTime Player won't open it, but if you copy it to Linux and use the file command it'll say it's an unoptimized QuickTime movie. It'd have to be MIDI given the small size

## Owari
TODO

## PacMac Deluxe
TODO other stuff

### Music
Module files in the Music folder (all ProTracker I think). The readme explains that you can add your own music to that folder, and given the plugs, that can be 669, IT, MADfg, MADH, MED, MIDI, MOD, MTM, OKTA, S3M, or XM

## Pararena 2
TODO
Source code may come in hnady

## Park Quest Demo
TODO
Park Quest engine, natch

## PGA Tour Golf II
TODO

## PowerPOKER
TODO

## Prometheus
TODO

## Ricochet
TODO

## robotfindskitten

### Text
STR# 128 contains all the responses to things that aren't kitten.

## Rogue
TODO

## Scholastic Colouring Book Creator
TODO

## Sim Tape Dispenser
TODO

## SimAnt
TODO
INST and SONG and MIDI oh my

## SimEarth
TODO
There's SONG resources and a TMPL for them but not INST or anything else that could be instruments

## SimFarm
TODO
If you open this with ResEdit it'll tell you off because it was apparently checked out as locked from an MPW project
Also there's the INST/SMOG/SONG resources yay

## SimHolePunch
TODO

## SimLife 
TODO
Sigh more INST/Midi/SONG resources

## Space Sirens 2: Megababes from Ajia
TODO

## Slithereens
TODO other stuff

### Music
MADH resources in Slithereens Music

## Solitaire Till Dawn
TODO

## Space Cab
TODO other stuff

### Music
AIFF files in Music folder

## Spaceward Ho! 5
TODO
Because this is a Carbonized application package it won't work the same way as older versions

## Spaceway 2000 Demo
TODO
Might work the same way in full game

## Spectre VR Demo
TODO
Might work the same way in full game

## Squish
TODO

## Strange Adventures in Infinite Space
TODO
Uses .app bundle

## Tetris Max
TODO
Animal Instinct Music and Peter Wagner Music contain snd resources, but the latter has multiple so I'm confused

## The Fantastic War
TODO

## The Fool's Errand
TODO

## PokeROMs / Pokemon Sanctuary
TODO
Macromedia Director engine

## Logical Journey of the Zoombinis (2001 re-release)
TODO
Macromedia Director engine I think

## The Virtual Stock Market
TODO

## A Case for TKKG: Deadly Chocolate
TODO

## Tomato Head
TODO
SuperCard engine

## Trainset +10
TODO

## Tristan
TODO

## Virtual Veronica
TODO
:^)

## Water Town Beta
TODO
Park Quest engine
Not sure if there was ever a finished version

## WaterRace Demo
TODO
Maybe works same way in full game

## Weekend Warrior
TODO

## White House Tour VR Demo
TODO

## Widget Workshop Demo
TODO
Maybe works same way in full game

## Woden
TODO other stuff

### Music
MADH resources with track titles as names

## Wrath of the Aliens
TODO

## Wrath of the Gods Demo
TODO
Maybe works same way in full game

## Zroids
TODO
I think my installation is borked because there's a Music folder with nothing in it

## My Little Kitchen
TODO
Hypercard stack

## Camping Story
TODO
Hypercard stack

## Virtual Springfield
TODO

## Ingenious
TODO

## Stay Tooned!
TODO
Macromedia Director engine

## The Labyrinth of Time
TODO
ScummVM plays this but I dunno if the Mac version works

## Xpand Xpo
TODO
Just a glorified QuickTime VR movie really

## Reading Blaster Jr.
TODO

## Indiana Jones and the Fate of Atlantis
TODO
SCUMM engine
ScummVM plays the Mac version so its source might come in handy

## What's For Dinner, Thankyou!
TODO

## Dark Seed
TODO

## SuperSolvers OutNumbered!
TODO

## SimTower
TODO
