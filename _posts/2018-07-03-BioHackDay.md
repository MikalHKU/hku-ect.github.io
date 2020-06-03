---
title: "Biodata Hack day"
excerpt: "Exploring different bio data sensors"
author: Machiel Veltkamp
header:
  overlay_image: /assets/images/IMG_6686.jpg
  image_description: "Exploring different bio data sensors"
  teaser: /assets/images/IMG_6686.jpg

tags: 
  - sensors
  - bio-data
  - freaklab
gallery:
  - url: /assets/images/IMG_6678.jpg
    image_path: /assets/images/IMG_6678.jpg
    alt: "bio hack day in progress"
    title: "bio hack day in progress"
  - url: /assets/images/IMG_6679.jpg
    image_path: /assets/images/IMG_6679.jpg
    alt: "bio hack day in progress"
    title: "bio hack day in progress"
  - url: /assets/images/IMG_6681.jpg
    image_path: /assets/images/IMG_6681.jpg
    alt: "bio hack day in progress"
    title: "bio hack day in progress"
---


One of the topics that students regularly ask questions about is the possiblity to use different bio-data as input for a interactive piece.
This can be to create a sound composition or interactive video installation or something else. The use of bio data of a person as input stays very intriguing.

The question is however how to get that data? What are the best and (easiest) options to directly work with this kind of data. These questions and a healthy dose of curiosity was our starting point for the Biodata Hacking day. We started with looking into some of the sensors and equipment the HKU already has and how to easily use them and have the data availaible as [OSC](https://en.wikipedia.org/wiki/Open_Sound_Control)

<img src="{{ "/assets/images/biohakdagA.jpg" | relative_url }}" width="200" class="align-left">

As a start we made a list of the equipment that we collected for that day and who would do what as you can see in the image to the left. Then it was time to start testing and to start coding. We spent most of the day trying stuff out while documenting what we where doing. With some devices it was reasonable straightforward to get them working and communicating over OSC, but with other devices we ran into some platform or driver issues. For example the Eyetracker we tried worked very good, but unfortunately only under Windows. At the end of the day we presented to each other what we worked on and what we found out. To see the full result of the day with more descriptions of the different sensors and code you can take a look at the github repository here: https://github.com/hku-ect/BioData-Interfaces

We hope to organize more of these days in 2019 to take the time to experiment and learn.

{% include gallery caption="The bio hack day in progress" %}




