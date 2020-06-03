---
title: "BioHakDag #2 and #3 Biodata Hack day"
excerpt: "Exploring different bio data sensors"
author: Than van Nispen
header:
  overlay_image: /assets/images/IMG_6686.jpg
  image_description: "Exploring different bio data sensors"
  teaser: /assets/images/IMG_6686.jpg

tags:
  - sensors
  - bio-data
  - freaklab
  - biohakdag
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
  - url: /assets/images/IMG_6681.jpg
    image_path: /assets/images/Jasmina-breath-heart-sensor.png
    alt: "Illustration BioArt Jasmina Avellanedas and Guillem Gongora"
    title: "Illustration BioArt Jasmina Avellanedas and Guillem Gongora"
---

This Blogpost extends the short post on BioHakDag #1, with BioHakDag #2 and #3 (Feb. 2019 & 2020)
See also https://pong.hku.nl/blog/BioHackDay/ for an impression of earlier BioHakDays.

# BioHakDag : “I have some good news and some bad news”.

## BioHackDay #3
The 3d BioHakDay took place on 12 February 2020 at HKU IBB.
It was great to experience so much interest in the topic of BioSensing amongst participants from Media, Interaction Design, Fine Art, Music & Technology, ECT and some non-HKU external participants Mimeto (MBO).

After a short and basic introduction to senses, sensors, biosensing & biohacking we made an assessment of the hardware present and got started.
After the lunch break we had a short inspiration presentation from the people behind https://www.goldenemotionanalytics.com

When we talk about BioSensors one can think of sensors with which the heart rhythm, muscle tension, skin humidity, breathing, movement and brain activity can be measured.
We explore how different sensors for biofeedback work and how they can be used to measure the physical change as a result of a variable experience.
This type of data enables designing for specific user experiences using sensors for implicit feedback (user-centered design). We can thus focus on "the inner workings of the user": what does the user experience?
Think for example of a game that becomes more difficult, more exciting, or easier when the player's heart rate increases, a meditation application, an installation that you can influence with your brain activity, or an application that gives you feedback based on the muscle tension in your arms.

In addition to measuring muscle tension, a special experience in BioHakDag # 2 was to control muscle tension through Electro Muscle Stimulation (EMS). With an electrical current in the right place, a muscle pulls together from the user. So you can, for example, let someone play the piano ; )

Examples of biosensors can be found at:
http://heartlive.nl , https://www.myo.com , https://store.neurosky.com/pages/mindwave , http://bitalino.com
A number of the sensors are available in the HKU werkplaats ‘uitleen’, but participants were also invited to bring their own sensors for further exploration.

## “First the Bad News”
Although some of the hardware is very easy to use (think of a blood pressure meter and the HeartLive with the included Windows software), getting most of the hardware up-and-running (anew, for the first time or ‘again’ after a year) is quite time consuming.
An important find in these BioHackDays is that the time required to find out how to get ‘it’ working, or what seems to be a problem (debugging), etc. was quite a challenge and demotivating.
Sometimes this is depending on the technical background of the person, but sometimes this has also to do with deprecated software, drivers, support and sometimes faulty hardware.
Some of these last finds include the Mindwave (even the new one, Mindwave 2), the difficulty to get Bitalino running, getting the relevant Myo data (via Myo Sender), HeartLives etc.
Some of the HeartLive sensors easily break at the joint of the ear clip, are very ‘defect’ and repaired with rubber bands & hair ties.
Besides that, the newer versions of Unity do not support UnityScript anymore. The updated script seems to have some audio filtering, making the raw output of the Heartlive sensor not able to visualise. This is something to further elaborate on in another BioHakDag.)
Another challenge is to get meaningful data out of the BioSensors. Data in many devices is ‘closed’, so that it requires some ‘hacking’ to get (some) of the data for creative purposes. Many devices (such as MindWave, Muse, HeartLive, Myo, etc.) offer their own applications, but do not offer any connectability to other applications.
Bio data can be ‘noisy’, varying to different contexts and users. Some of the hardware has built-in calibrations and some ‘smoothening’, like the Bitalino en Heartlive.

## “Then The Good News”
The basic concept of a quantified self, as well as the opportunities that BioSensing offers for user centred (interaction) design are very inspiring.
The students that participated in the last couple of BioHakDays were highly motivated to realise some of their work with biosensing.
Some interesting end results are discussed at the end of this section and include the work from Jasmina Avellanedas and Guillem Góngora.


{% include gallery caption="Illustration BioArt Jasmina Avellanedas and Guillem Gongora" %}

[Illustration BioArt Jasmina Avellanedas and Guillem Gongora](/blog/assets/images/Jasmina-breath-heart-sensor.png)

The domains of BioArt, BioSensing and BioHacking are in a lift and the number of (commercial) applications is growing every moment. It was a welcome, inspiring, presentation by Golden Emotion Analytics, a new startup that has the ambition to have some of the ‘quantifiable biodata’ connected to optimizing user experiences involving media and entertainment.
https://www.goldenemotionanalytics.com
Another interesting find was the commercial applications around “Plant Music” → Plant Sensing, with sound / music as a result.  
One of the student groups started working with a concept of plant personalities and some ‘presence sensing’ required to give auditive feedback to a visitor on whether to approach (or not) the plant. This early prototype of ‘plant touching’ was realised with the Bare Conductive Touch Board.

It’s especially nice when a concept is realised in the limited time of one ‘BioHakDag’.
The realisation of ‘breathing the life into a digital Pinguin’ with an E-health sensor and PinGui is especially noteworthy:
Documentation of E-health sensor and PinGui: http://laczkojuli.net/biohackdag-hku-ibb-feb-2020/
Embed video : https://youtu.be/p3OwxICeS_A


## What we explored / worked on / with :

### Kinect :
As a potential ‘presence detector’, ‘pose detection’, but also heartrates the Kinect is a promising sensor.
It’s good to mention that Kinect won’t work on OS X Mojave, because openNI is not supported.
For pc use NiMate to ‘translate’ skeleton data to OSC.
“Beware: use microsoft drivers, not the one NiMate wants to install”
Check for more information : https://trello.com/c/s0eVb1zk

### Tobii Eye tracker (no updates, only works on Windows), see https://github.com/hku-ect/BioData-Interfaces

### Bose AR ready headphones : Frames
A new development we see for BioSensing is the simple implementation of gyroscope data in Bluetooth devices, such as headphones (Bose AR ready headphones).
A special mention and worth exploring is the Bose Frames (sunglasses with built in miniature speakers and ‘AR-ready’). To start experimenting with these frames : https://developer.bose.com (or ask Than van Nispen for the Unity demos)
Step 1:
Firmware updates (required) Bose Update application (works with Google Chrome)
Bose Frames werkt via USB Audio Support ook in Unity op Mac. Echter... is een USB kabel benodigd. Builden naar een mobile device kan voor beide apparaten (en dan dus wel handsfree).
USB Audio Support (BOSE NC 700 HP (doesn't support USB Provider)
If your Bose AR device supports USB Audio, the device should enumerate as an audio output device on your operating system shortly after connecting to the device at runtime.
Currently, the following Bose AR devices support USB Audio: • Bose Frames
To hear audio through your supported device:
Connect to your device via the USB Provider
Go to your system audio settings and select your Bose AR device as the default audio output.
Next level: (including Bose Frames for Max/MSP 8 ea)
https://github.com/zakaton/Bose-Frames-Web-SDK
chrome://flags/#enable-experimental-web-platform-features
Chrome for Desktop [PREFERRED]: enable Web Bluetooth by going to chrome://flags/#enable-experimental-web-platform-features and check “Experimental Web Platform features”
http://localhost:8888/bose-ar-explorations/

### Heartlive & Unity (Sander)
Microphone input does work
Heartlive does not give any form of response (but I can see the data in Audition).
I think some filtering or buffer size cancels the signal. To be continued.

### MakeyMakey
Although debatable whether this device is a ‘biosensor’ the https://makeymakey.com is a very simple usb interface that literally “Connects the world to your computer” (-as is the company’s slogan), by offering 6 inputs to connect ‘conducting things’ to, like bananas, tin foil, humans, or anything else in the world. . .
Makey Makey work just like a USB keyboard or mouse, sending keyboard (WASD, spacebar, etc) and mouse (left click, right click, etc) signals to your computer.

Makey Makey Classic works through opening and closing circuits, just like any other button. Instead of the circuit being closed underneath your keyboard, the circuit is closed through the conductive objects you connect with alligator clips like your hand or your lunch or some tinfoil. When the circuit is closed, the Makey Makey sends a command to your computer, just like a button pressed on a keyboard.

(Relatively new is the “Makey Makey GO” which is much smaller and works through capacitance).

For rapid prototyping and for instance to recognize a person ‘touching’ an object, the MakeyMakey is considered as a relevant device in BioSensing.

There are many variations based on the MakeyMakey principle, but a special mention goes to the Touch Me ‘sensor’ :
https://shop.playtronica.com


### BareConductive
The group that used the BareConductive for a ‘Plant communication’-project modified the Bare Conductive, so that the output is midi. You can either solder, or use electronic paint on the midi-connection. See : https://www.bareconductive.com/make/on-board-midi-mode/ for more information

### MYO

http://diagnostics.myo.com
ECT previously developed the MYO OSC sender https://github.com/hku-ect/Myo to make use of the MYO data possible, via sending it over the network as OSC. The application works fine in Mojave.
A new feature request for this MYO Sender was to have myo/emg data in OSC (as can be seen in https://github.com/Sindel/myo-osc ). The 8 EMG-data pods are relevant for using the muscle tension and is an important addition to the gyroscope data and pre calibrated gestures.
Another question -and feature request- is whether the updated application could send ‘pings’ to the Myo (can you have the MYO trill on command?)
These features will be implemented later this year.



### MindWave 1 & 2 (new)

Niet aan de praat gekregen.
Documentatie doet vermoeden dat ‘het’ moet werken, maar geen installaties mogelijk onder 10.14.6 . Advies contact opnemen met bedrijf voor support.

The Muse headband was under reparation during BioHakDag #3

### Bitalino

Bitalino presents itself as a “personal biomedical research system” and “an all-in-one hardware design, with all the blocks pre-connected between them and ready-to-use, making it perfect for biosignal exploration and lab activities. The kit includes all the basic accessories needed to get started, namely the hardware modules, battery, cables and electrodes. Along with our cross-platform OpenSignals software, it enables instant biosignal data visualization and recording out-of-the-box.”

https://bitalino.com/en/
https://bitalino.com/en/learn/get-started

Some of the sensors included in the kit are Electromyography (EMG), Electrocardiography (ECG), Electrodermal Activity (EDA), Electroencephalography (EEG), Accelerometer (ACC)
From the BioHakDag #1 : A Python script to get in the Bitalino data, and send it over OSC, tested on Mac OS Sierra, and with Python 3.7 and libraries mentioned here: https://github.com/BITalinoWorld/revolution-python-api
There is also a Bitalino Max/MSP object available https://github.com/Ircam-RnD/bitalino-max

As many students seem to have difficulty in getting the Bitalino up-and-running, one of the R&D-colleagues of ECT experimented with the Bitalino.
It is important to follow the online instructions, step-by-step. Also check if the sensor is connected to the correct input (beware : the information of the inputs is on the underside of the board, while it seems more logically to only look on the topside of the board).
As Job said : “We zijn geneigd om vanaf boven te kijken en simpelweg te tellen wb poorten”
Furthermore : “Data in tekstbestanden verdient geen schoonheidsprijs.” The data is primarily updated in a text file. This is not very practical for interactive applications. Bitalino offers an Arduino SDK, which should make more interactivity possible (without having to work with updated text-files).
It’s also good to mention that the Bitalino hardware gives good and coherent results → apparently there is some Auto-calibration in the hardware.
Is you connect the sensors directly to an Arduino this results in very noisy data, practically unusable, so use the Bitalino hardware with the sensors!
Furthermore : ignore the urge to break the board in separate components (it really looks very inviting to do so), because this will require to make all the connections anew....


### Kodea KD-202F Blood Pressure monitor

Dit is een Blood pressure Monitor waarover weinig te vinden is online. Echter na wat snuffelen blijkt dat de monitor hoort bij de e-health sensor platform van cooking hack.
Main tutorial page of the e-health shield
(https://www.cooking-hacks.com/documentation/tutorials/ehealth-biometric-sensor-platform-arduino-raspberry-pi-medical/)
[Error in e-health arduino library](https://www.cooking-hacks.com/forum/viewtopic.php?f=20&t=6023)

Het lijkt alsof je met de bloodpressure sensor alleen de gegevens in het geheugen kan uitlezen. Dus je kan alleen meetingen die al gedaan zijn uitlezen.
Je verbindt hiervoor de hartslagmeter met de e-health shield die je op Arduino zet. Alleen als je nu in de Seriele monitor kijkt zou je de gegevens moeten kunnen binnen halen, maar dat werkt helaas niet..



### Electro Muscle Stimulation (EMS)

Filipe: "voordeel van EMS vs. trill motors is dat het een zeer specifieke sensatie is"
Hans: "unpleasant feeling, too intrusive"
Tested on arm, thumb.
Experimented with size and form: too small form feels more 'painful', original (square) size seems best.
More literature : Pedro Lopes EMS
http://plopes.org/ems/#testingEMSmachine




{% include gallery caption="The bio hack day in progress" %}
