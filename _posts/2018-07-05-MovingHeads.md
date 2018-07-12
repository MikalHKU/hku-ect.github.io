---
title: "Moving a light with Isadora"
excerpt: "Let the light follow where I walk with my MOCAP rigidbody"
author: Machiel Veltkamp
header:
  overlay_image: /assets/images/isadora_movingheadB.jpg
  image_description: "Let the light follow where I Walk"
  teaser: /assets/images/isadora_movingheadB.jpg

tags: 
  - Isadora
  - MOCAP
  - Light
---


During the FutureLabs #2 at the end of august 2017 we where experimenting with controlling four moving heads over DMX. We used [QLC+](http://www.qlcplus.org/) and a Entec [USB DMX Pro](https://www.enttec.com/eu/products/controls/dmx-usb/2-universe-usb-computer-interface-dmx/). The nice thing about QLC+ is that you can also control it using [OSC](https://en.wikipedia.org/wiki/Open_Sound_Control) meaning that any software that speaks OSC can control the stage lights! We used [Isadora](https://troikatronix.com/) to send OSC and played around with directing the moving heads. One of the first ideas was to use the MOCAP installtion with which we where working during the FutureLab to control the light. We thought it would be relatively simple to let the lights follow a MOCAP rigid body, but in the little time we had during the lab we could not get it working.

Some time after the lab my colleague sat down to figure out the math that we would need. The goal was to take the x,y,z position of a MOCAP rigidbody and convert it to a pan and tilt of a moving head so that the moving head would folow the rigidbody and shine where the rigidbody would move to.

{% include figure image_path="/assets/images/IMG_1080.jpg" alt="the math to move the light" caption="the math to move the light" %}

Finally last week we got the oppertunity to play around with the moving heads hanging in the grid, MOCAP, Isadora and the math we needed. 
The first challenge was to impelent the math in Isadora using the javascript actor and testing of the math. Once we had that figured out the next challenge was to convert the angle's we got from the calculations to the right instructions for the moving head. 

To control the movinghead over OSC we made an user actor where each parameter of the lamp would accept a value form 0 to 1. So we needed to translate the angles that we got from our calculation to a fitting value between 0 and 1 for this we used the limit-scale value actor. Then we figured out that the pan of the moving head was between 0-540 degrees, while form the calculation we could get a value from -180 to 180 so we first used a limit-scale value actor to go from the range of the actor to the range of the lamp and used that output as input for the limit-scale value actor the converted the range of 0-540 to the 0-1 rage we usedn when sending the value over OSC. It actually sounds more complicated when I write it out than when you need to do it.

{% include figure image_path="/assets/images/isadora_movinghead.jpg" alt="the Isadora patch" caption="the Isadora patch" %}

For the pan of the light we started out to feed the putput of the calculations in a similiar way until we realises tha whiel the pan has a range between 0 - 180 degrees we actually only use roughly a 0-90 degrees range becaus we use the pan in combination with the tilt of the lamp. Form the calculations we got a range form 0-90 degrees this we converted to a 0-1 range and that ragne we converted to tha actual value for the light where 0 would be 0.5 at which the light woul look straight down and 1 would become 0.088 where the lgiht would be level with the ceiling. Again it sounds more complictated writen down then wehen we made it.

So after figuring out the math and a lot of tweaking we had a nice automated lamp to light wherever we would walk with out magic stick.

{% include video id="qDYmxxL7K1c" provider="youtube" %}

If you are interested you can take a look at the Isadora file [here]({{ "/assets/files/movelight_MOCAP.izz" | relative_url }})




