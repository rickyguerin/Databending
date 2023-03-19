<p align="center">
[IMAGE PLACEHOLDER]
</p>

## What's Databending?
Databending is the process of editing a file using software that is not meant to edit that type of file. This document is a basic introduction to editing images using audio software to achieve weird, glitchy visual effects.

To follow along, you'll need an application for editing images, and an application for editing audio. I use [GIMP](https://www.gimp.org/) for images and [Audacity](https://www.audacityteam.org/) for audio. They're great, free, open-source, cross-platform tools, but your personal editors of choice will probably work too.

## Prepare an Image for Databending
Any image you want to databend must be an **uncompressed file type**. I only use **.tiff** files, but other uncompressed file types should work too. If your image is in a compressed format like .png, just open it with GIMP and export it as a .tiff file.

Additionally, your image file **shouldn't have multiple layers**. If you're databending a photo, you probably don't have to worry about this, but if your image file was composed from multiple layers in GIMP, you'll have to merge down to one layer before you export the file.

I would also recommend that you open your image in GIMP and make sure that your image has an **alpha channel**. This allows your databending result to have transparency, and will give you more flexibility later on, in the Postprocessing section.

## Databending Your Image

### Get Your image into Audacity
1. Open Audacity
2. Do File > Import > Raw Data and select your image
3. Configure your import settings
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
Here's where the magic happens.

### When You're Done
+ Export as the same file type as your source image

## Postprocessing
+ You have successfully databent an image
+ Depending on the effects used, your result may be very transparent
+ I layer the result on top of a black background, or sometimes the source image

## Misc Notes

+ If you grayscale your image before databending, your end result will be a little less glitchy/grainy
