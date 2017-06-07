# A sampler module for AUTOMATONISM

![](https://raw.githubusercontent.com/megalon/pd-AUTOMATONISM-sampler/master/images/AUTOMATONISM-sampler-image3.PNG)

This module is a stereo sampler built for [AUTOMATONISM](https://www.automatonism.com/) that fully supports state saving, parameter nudging, and works like any other AUTOMATONISM module.

## FEATURES:
* Variable pitch, length, and start position.

* Negative pitch values play the sample in reverse.

* Preset buttons above the pitch slider set the pitch to the corresponding speed multiplier.

* When the sample reaches it's end, a trigger is sent out of the END_TRIG outlet.

* Open any audio file that Pure Data supports (WAV and AIFF), at any sample rate.

* The path to the sample file is stored within the statesave (when you press space), so it should reload the sample when AUTOMATONISM starts up... Unless you move the sample file!

[Here is an image of the patch if you would like to see what it looks inside.](https://raw.githubusercontent.com/megalon/pd-AUTOMATONISM-sampler/master/images/internals-preview.png)

## UPDATES:
**2017-6-7: v1.3**
* Added filename display to GUI. Spaces in the filename are replaced with underscores in the display, since it uses a canvas label. Filenames that are too big to fit on screen are truncated and have "..." placed at the beginning.
* Added trigger indicator next to the END_TRIG outlet.

**2017-5-24: v1.2** 
* Added support for file paths that have spaces in them.

**2017-5-23: v1.1** 
* Added trigger indicator next to TRIG inlet to show when a trigger has been recieved.
* Fixed param-nudge for the PITCH slider. It should now nudge like any other slider.

# How do I install it?

Download **sampler.pd**, **sampler-help.pd**, and **sampler-EASY-COPY-PASTE.pd** from this github repo.
 
Within the *AUTOMATONISM_1.1* folder, there is another folder called *patch_editor_abs*. Drop the files "sampler.pd" and "sampler-help.pd" into this folder.

![](https://raw.githubusercontent.com/megalon/pd-AUTOMATONISM-sampler/master/images/sampler-location.PNG)

In order for the sampler button to show up in the MODULES window, we need to do two more things. I have made this easier by including the file called **sampler-EASY-COPY-PASTE.pd**.

First we create a button for the sampler within the MODULES window that will send a bang to the load subpatch. Copy the one I've created in sampler-EASY-COPY-PASTE.pd. I placed the button in a new subsection called EXTRAS.

![](https://raw.githubusercontent.com/megalon/pd-AUTOMATONISM-sampler/master/images/sampler-button.gif)

Then we need to create the subpatch to load the SAMPLER module into the main window, and handle incrementing the number each time a new one is created. These are contained within the [pd patch-editor-do-not-delete] subpatch. Copy the one I've created in sampler-EASY-COPY-PASTE.pd, and paste it into  [pd patch-editor-do-not-delete]. I again made a new subpatch for extra modules.

![](https://raw.githubusercontent.com/megalon/pd-AUTOMATONISM-sampler/master/images/sampler-open.gif)

# FAQ

## Why can't I hear anything?
Do you have the pitch or sample length set to 0?

Did the sample fail to load? (Check the pd console to see why. Only WAV and AIFF are supported in PD)

Does your sample actually contain any sound?

## Do mono samples work?

Yup. Mono samples will only play out of the left outlet, OUT_L.

## Why are files over 4000000 samples truncated?

This is just how PD loads samples into arrays. It's over 90 seconds (at 44.1 kHz), so it shouldn't be a problem for most. Some people have gotten around this in other projects, but it wasn't the purpose of this one.

## Why don't you show the waveform in the GUI?

I found it to be very laggy, especially when I had multiple samplers running.

## Why did you make this?

I thought it would be fun to play with, and it is!
