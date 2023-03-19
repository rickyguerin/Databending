<p align="center">
[IMAGE PLACEHOLDER]
</p>

## What's Databending?
Databending is the process of editing a file using software that is not meant to edit that type of file. This document is a basic introduction to editing images using audio software to achieve weird, glitchy visual effects.

To follow along, you'll need an application for editing images, and an application for editing audio. I use [GIMP](https://www.gimp.org/) for images and [Audacity](https://www.audacityteam.org/) for audio. They're great, free, open-source, cross-platform tools, but your personal editors of choice will probably work too.

## Prepare an Image for Databending
Any image you want to databend must be an **uncompressed file type**. I only use **.tiff** files, but other uncompressed file types should work too. If your image is in a compressed format like .png, just open it with GIMP and export it as a .tiff file.

Additionally, your image file **shouldn't have multiple layers**. If you're databending a photo, you probably don't have to worry about this, but if your image file was composed from multiple layers in GIMP, you'll have to merge down to one layer before you export the file.

In general, I would also recommend that you open your image in GIMP and make sure that your image has an **alpha channel**. This allows your databending result to have transparency, and will make it easier to put together a cool final product in the Postprocessing section.

<p align="center">
[IMAGE PLACEHOLDER]
</p>

## Databending Your Image

### Get Your image into Audacity
1. Open Audacity
2. Do File > Import > Raw Data and select your image
3. Configure your import settings and click open
    1. Encoding &rarr; U-Law
    2. Byte order &rarr; Big-endian
    3. Channels &rarr; Mono
    4. Start &rarr; 0
    5. Amount &rarr; 100
    6. Sample Rate &rarr; 44100

### What NOT To Do
+ I don't recommend "listening" to your image, it will probably sound like nails on a chalkboard
+ Do NOT edit the audio at the beginning and end of the track
  + There is metadata stored at the beginning and end of an image file that tells the computer how to read the file. If you edit the metadata, the exported image will be unusable.
  + You should be able to edit everything except the first and last ~0.1 seconds of audio
+ Do NOT do anything to change the length of the audio
  + If your exported data is shorter/longer than your imported data, it won't line up with the metadata, and your file will be unusable.

### Apply Effects
Here's where the magic happens. Almost anything you select from Audacity's Effect menu is going to do some cool stuff to your image. Exploring all your options is part of the fun of databending, so I'll leave it up to you to experiment, but I do want to call out Noise Reduction specifically, because I think it's so cool that I use it in almost all of [my art pieces](https://www.instagram.com/oofy.doodle/)

Noise Reduction will strip away parts of your image that match the current "Noise Profile". You can import another track into Audacity (this could be actual audio, or another image), select a portion of that track, and click "Get Noise Profile" from the Noise Reduction window to tell Audacity what "noise" you want to deal with.

The "Reduce" mode will reduce any "noise" it finds in your image. The "Residue" mode will reduce anything that ISN'T "noise". Both are cool, but I usually end up using Residue mode in my art.

I have not done enough experiments to know what makes for a good Noise Profile. I almost always use snippets of audio from the Super Mario RPG OST because doing so suits my \~aesthetic\~.

### When You're Done
1. Make sure to delete any extra audio tracks from the Audacity project
2. Do File > Export > Export Audio
3. Configure your export settings and click save
    1. File name &rarr; should be a .tiff file
    2. Save as type &rarr; Other uncompressed files
    3. Header &rarr; RAW (header-less)
    4. Encoding &rarr; U-Law
    
Try opening the new image in GIMP. If it works, congratulations! You just bent some data. If it doesn't work, you probably edited data that was too close to the start/end of the audio track.

## Postprocessing

### Transparency
Depending on the source image you used, the effects you applied, and your desired look, you may already be done. You can just re-export the image to a compressed file type like .png and be on your merry way.

I generally find, though, that some post-processing is necessary. Some effects like Noise Reduction (_especially_ Residue) will make your result very transparent. In GIMP, you can layer the result image on top of the source image, or just a plain black background layer to see it better.

<p align="center">
[IMAGE PLACEHOLDER]
</p>

<p align="center">
[IMAGE PLACEHOLDER]
</p>

### Color
The way I make art, I usually databend grayscale images and then re-color them in GIMP, making HEAVY use of the Hue-Chroma tool:
1. Do Color > Hue-Chroma
2. Turn the Chroma setting up to 100
3. Mess around with the Hue and Lightness settings until it looks cool

<p align="center">
[IMAGE PLACEHOLDER]
</p>

