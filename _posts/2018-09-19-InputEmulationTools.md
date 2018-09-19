---
title: "Input Emulation Tools"
excerpt: "Using tools like GlovePIE to easily emulate inputs"
author: Aaron Oostdijk
header:
  overlay_image: /assets/images/input-emu_header.JPG
  image_description: "Arduino knobs & button become mouse-inputs"
  teaser: /assets/images/input-emu_header.JPG
tags: 
  - input
  - development
  - emulation
---

# Input Emulation, what and why?
As developers, whenever somebody asks us if something can be done we're quick to jump to a tool that we know to do it with. For me this tool is Unity. Sometimes, the solutions can be a lot easier, and it can be a good idea to keep in mind that without a lot of complicated coding, you can create interactive setups using existing applications.

To do this, you'll probably need to use Input Emulation: mapping one kind of input, onto another kind of input (that the program you're using already understands). A simple example that I'll be showcasing today: using Arduino analog/digital inputs, to simulate a Windows mouse. This requires a minimal amount of coding in a tool called GlovePIE and of course a bit of setup with an Arduino.

I first encountered GlovePIE specifically a little over ten years ago when I was asked to [integrate a Nintendo WiiMote into the Source Engine](http://stunningcreations.nl/) (to control Half Life 2). My head exploded with the complexity of the demand (I had no idea how to even start to integrate a WiiMote into Source), until I figured you could just emulate the mouse (which Source already understands) and bypass the whole problem. So when a colleague asked me for a low-tech solution to alternatively control a 360 video installation (that uses existing image viewers or YouTube), I wondered if these tools were still usable today. Good news: they are!

# What you'll need
So, what are you going to have to install to get this demo to work?
 * Arduino IDE (through the Windows Store)
 * [GlovePIE 0.45](https://glovepie.software.informer.com/download/)
 * [vJoy](https://sourceforge.net/projects/vjoystick/) (to simulate a virtual joystick)
 * [vJoySerialFeeder](https://github.com/Cleric-K/vJoySerialFeeder) (to link the Arduino to vJoy)

After installing all of these things, I started up the example Arduino script from vJoySerialFeeder, and there were two things I needed to change:
 * NUM_ANALOG_INPUTS was already being used by Arduino, so I just removed the NUM_ from all of these in the script.
 * ANALOG_REFERENCE was set to EXTERNAL, but this needs to be DEFAULT for my setup

From there, I could start building my setup, which looks as follows:

{% include figure image_path="/assets/images/input-emu_header.JPG" alt="Arduino setup" caption="Arduino setup" %}

What you see here are two [Phidgets with knobs](https://www.phidgets.com/?tier=3&catid=15&pcid=13&prodid=79), and one [Phidget with a pressure sensor](https://www.phidgets.com/?tier=3&catid=6&pcid=4&prodid=76).

The two knobs are connected to Analog inputs 0 and 1, and the pressure sensor is connected to Digital 13 (green & white wires). They're all connected (with the little white breadboard) with the 5V power (purple and blue wires), and the ground (brown wires).

From here, I tell the Arduino script (from vJoySerialFeeder) to use the Analog inputs and Digital 13:

{% include figure image_path="/assets/images/input-emu_arduino-ide.png" alt="Arduino IDE settings" caption="Arduino IDE settings" %}

# vJoy and vJoySerialFeeder
vJoy is a tool that simulates a virtual joystick (hence the name) on Windows. This allows you to play all kinds of games or use applications that already understand joysticks. If your end-goal is thus a joystick, you won't even need GlovePIE! But back to vJoy.

In order to get our Arduino outputs (which are sent over the Serial port) into vJoy, we use a tool called vJoySerialFeeder to map the serial inputs to the virtual joystick. This means we create three controsl for the serial channels from Arduino: 1, 2 and 7 (it's 7 because we have 6 analogs, even though we just use 2, and one digital), and then we tell vJoySerialFeeder what values to expect.

So important to know for this particular setup:
 * We're using channels 1, 2 (analog -> axis) and 7 (digital -> button)
 * The values from our buttons vary from 0 to 1023
 * The Arduino script uses the IBUS protocol

Once it's setup and functional, it'll look something like this:

{% include figure image_path="/assets/images/input-emu_serialfeeder.gif" alt="vJoySerialFeeder setup" caption="vJoySerialFeeder setup" %}

And we can monitor that this works correctly by opening the vJoy Monitor application:

{% include figure image_path="/assets/images/input-emu_vjoy-mon.gif" alt="vJoy Monitor" caption="vJoy Monitor" %}

# GlovePIE to put it all together
Finally, we're ready to actually start emulating the mouse. I was happy to discover GlovePIE still works for the most part, although audio input seems to be broken. But for joysticks, mice and (hopefully) kinect it should be functional.

The script I used to translate the virtual joystick to mouse positions is very short and simple enough:

{% include figure image_path="/assets/images/input-emu_glovepie.gif" alt="GlovePIE script" caption="GlovePIE script" %}

# Using Microsoft Paint with at least three hands (a feature, not a bug!)
 And finally, a small example of using the setup to use a program that understands the mouse (Microsoft Paint):
 
 {% include figure image_path="/assets/images/input-emu_paint.gif" alt="GlovePIE Microsoft Paint" caption="GlovePIE Microsoft Paint" %}
