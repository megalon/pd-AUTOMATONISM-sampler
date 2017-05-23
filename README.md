# A sampler module for AUTOMATONISM

![](https://raw.githubusercontent.com/megalon/pd-AUTOMATONISM-sampler/master/images/AUTOMATONISM-sampler-image.PNG)

This SAMPLER module is a stereo sampler that will open any audio file that Pure Data supports (WAV and AIFF), at any sample rate.

**FEATURES:**
* Variable pitch, length, and start position.

* Negative pitch values play the sample in reverse.

* When the sample reaches it's end, a trigger is sent out of the END_TRIG outlet.

* The path to the sample file is stored within the statesave (when you press space), so it should reload the sample when AUTOMATONISM starts up... Unless you move the sample file!

# How do I install it?

Within the AUTOMATONISM_1.1 folder, there is another folder called patch_editor_abs. Drop the files "sampler.pd" and "sampler-help.pd" into this folder.

![](https://raw.githubusercontent.com/megalon/pd-AUTOMATONISM-sampler/master/images/sampler-location.PNG)

In order for the sampler button to show up in the MODULES window, we need to do two things. I have made this easier by including a file called **sampler-EASY-COPY-PASTE.pd** within this github repo. 

First we create a button for it within the MODULES window that will send a bang to the load subpatch. Copy the one I've created in sampler-EASY-COPY-PASTE.pd. I placed the button in a new subsection called EXTRAS.

![](https://raw.githubusercontent.com/megalon/pd-AUTOMATONISM-sampler/master/images/sampler-button.gif)

Then we need to create the subpatch to load the SAMPLER module into the main window, and handle incrementing the number each time a new one is created. These are contained within the [pd patch-editor-do-not-delete] subpatch. Copy the one I've created in sampler-EASY-COPY-PASTE.pd. I again made a new subpatch for extra modules.

![](https://raw.githubusercontent.com/megalon/pd-AUTOMATONISM-sampler/master/images/sampler-open.gif)

# FAQ

## Why can't I hear anything?

Do you have the sample length or pitch set to 0?

## Why don't you show the waveform in the GUI?

I found it to be very laggy, especially when I had multiple sampler's running.

## Why did you make this?

I thought it would be fun to play with, and it is!
