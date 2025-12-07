# Making Custom SM64 Music
My team and I figured this shit out from 7 year old tutorials at 3 in the morning.\
Do note that this is primarily for Super Mario 64 Coop Deluxe!\
Let's go through the process.

## Part 1: Setup FL Project
Get your SM64 MIDI, any will do that contains the same-ish instruments.\
![Image of Soundfont Player with a soundfont loaded.](/docs/img/music_guide/1.png)

Just make sure that you name your instruments to what they're supposed to represent.\
E.g. ```Electric Piano```

## Part 2: Make Your Beat
You're limited to a polyphony limit of 3 per channel. (I COULD be WRONG!)

Start by going to your soundfont player and click on the gear option, then the revealed wrench icon.\
![](/docs/img/music_guide/2.png)

Then set the polyphony setting to 3.\
![](/docs/img/music_guide/3.png)

Make sure to set the track for each instrument.\
![](/docs/img/music_guide/4.png)

You only get 15 midi tracks.\
A trick to bypass the polyphony limit is to split your complex chords up into two dupe instruments on separate tracks.

## Part 3: Prepare to Export from FL Studio
Once you have your awesome beat, you have to export it to use it in the game!\
This can be a little technical, but its okay.

Backup your project first!\
This next step permanently modifies the project.\
First open ```Tools```, then ```Macros```, then ```Prepare for MIDI export```.\
![](/docs/img/music_guide/5.png)

Make sure your instruments are on the correct channels.\
Next, make sure that the soundbank is set to the correct instrument that corresponds with your wanted instrument in the game.\
A document with a list of these can be found [here](https://docs.google.com/document/d/1WbFM2MeP15NDMhYS9yA2Nv2xQEGljtMuQrWrHtGTWAc/view).
<!-- ! MAKE SURE THIS IS CORRECT! -->
This next step is optional,  but set the correct instrument from the patch list.\
![](/docs/img/music_guide/6.png)

<!-- TODO: Reword this!!! -->
You're now ready to convert your MIDI file to the N64 format.

## Part 4: Convert the MIDI to M64
First, download the latest release of [SEQ64](https://github.com/sauraen/seq64).

Next, in the list of games, select ```1 - SM64```.\
![](/docs/img/music_guide/8.png)

Select the ```FL Studio compat``` option.\
This is needed because FL Studio just has to export MIDIs differently.\
![](/docs/img/music_guide/9.png)

Select ```Import MIDI``` and select your exported MIDI file.\
![](/docs/img/music_guide/10.png)

Make sure that the ```MIDI import succeeded``` message box pops up.\
If you get an error, your MIDI exported incorrectly, or you misconfigured FL Studio somewhere.\
![](/docs/img/music_guide/11.png)

Finally, click ```Export binary``` and save the ```.m64``` file somewhere.\
![](/docs/img/music_guide/12.png)
You'll know it exported correctly if a popup appears saying ```bynary export succeeded!```.

## Part 5: Put the Song Into The Game
We're in the home stretch!\
All you have to do is put the ```.m64``` file into your mod's ```sound``` folder.\
![](/docs/img/music_guide/13.png)

Finally, in your lua file, add this function to your file.\
Follow the arguments to load your sequence.
```smlua_audio_utils_replace_sequence()```