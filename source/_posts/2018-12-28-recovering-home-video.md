---
title: Recovering Home Video
author: Stephen Cross
tags:
    - Tech
list_image: /images/blog/recover-video-listing.jpg
list_image_alt: Recoving Home Video  
primary_image: /images/blog/recover-video-primary.jpg
primary_image_alt: Recovering Home Video 
---

I have forty-six tapes with home videos that cover family events from 1996 to 2005.    These tapes have been stored in a box for as many years.   I recently took on the project of moving them to a format we can enjoy.   My two challenges: how to get them off of the tapes and how to make them accessible to everyone in the family.

## Camera to Computer 

The camera used to take these videos, a [Sony Digital HandyCam DCR TRV 120](https://www.sony.com/electronics/support/camcorders-tape-camcorders/dcr-trv120) ,  is still operational.   I made that discovery after purchasing a power cord from Amazon.   Then I needed cabling to connect the camera to my computer.   This was hit and miss because it wasn't clear to me which cables would work.  I'm thankful Amazon has a generous return policy.  I had three cable attempts fail.  I settled on a combination of two cables that allowed me to go from a 1/4 inch camera output to composite and then composite to USB.    The composite to USB came with drivers and software to capture video on a Mac.  

Cables:

[HDE 3ft. Feet RCA Male to 3.5mm Male Jack Composite Audio Video A/V Cable](https://www.amazon.com/gp/product/B00GO4EPKC)

[S-Video / Composite to USB Video Capture Cable Adapter w/ TWAIN and Mac Support - VHS to USB Composite Svideo](https://www.amazon.com/gp/product/B00535BRBI)


## Capture Process 
The capture process requires each tape to be played from the camera and recorded on the Mac.  A 45-minute recording takes 45 minutes to capture.   I learned the capture process is a bit fragile.  After recording eighteen videos (aka eighteen hours of recording), I discovered eleven videos had no audio or the audio was out of sync.   I made some changes to my process to ensure the remaining recording would go well. 
* The video capture software should be the only application running on the Mac during the capture process
* Play the audio through the Mac, not the camera, to verify the audio is getting to the camera
* Rebooted at the start of each recording session or after every four tapes

Some tapes had sixty minutes of content while others had thirty-five.   The best process for me was to let the 60-minute tape run through and edit out the blue screen when it completed.   This allowed me to do other things while capturing the video.    When the recording was complete, I would open the resulting .mov file in QuickTime and trim out the blank recording from the end.  

## Serving Home Video

I chose to serve the home videos through Plex (https://www.plex.tv/).  Plex allows you to store, manage, and stream your personal media.  I expect I will be using Plex home movies and maybe photos in the future.   Plex is an open source application that requires a central server to stream content to Plex clients.   A Plex client can be almost any device. For me it will be Apple TV, iPads, iPhones, a Roku, and Fire TVs.  Content can be streamed in and out of my home network.  With grown-up children, having remote access to the video content is important.

After a bit of research, I learned that a Raspberry Pi could be used as a server, but it may not be powerful enough.  Since I had a Pi 3, I decided to give it a try.  Comfortable with Linux and the command line, I had a Plex server running on the Pi in 15 minutes using a resource like [How to set up a Raspberry Pi Plex server](https://thepi.io/how-to-set-up-a-raspberry-pi-plex-server/).  I connected a USB external drive to the Pi to store the 140GB of home videos.

It worked!    The quality of the video is fantastic.   When streaming a 30-minute video from a device, it will stop a few times and buffer.   A "your server is not powerful enough..." type message will also appear, but it works.

## Next Steps

**Plex Server Upgrade** - My next project is to upgrade the $35 Raspberry Pi to a more powerful single board computer (SBC).    I'm looking at a RockPro64 or NanoPC T4 with 250GB m.2 storage.   I think this will deliver my minimal needs and not break the bank.    And more importantly, it's a fun tech project.  Stay tuned. 

**Video Editing** - I discovered that the 19-year-old video labeled as Christmas 1999, was really four events starting in December, 1999 and ending in July, 2000.   Now that I have the videos on my computer, I'll be breaking them into smaller videos.  No commitment on when this will be complete. 

**Moving forward** - We all take lots of video with our smartphones.  For me, it's not intentional, long-form video, like my Digital 8 tapes.  It's short bursts of interesting things.   Moving forward, I need to figure out how to aggregate that video in a format my kids can enjoy in 25 years.


