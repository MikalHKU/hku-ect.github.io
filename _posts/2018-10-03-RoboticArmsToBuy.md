---
title: "Which Robotic arms can I buy?"
excerpt: "an overview of which robotic arms ar currently on the market."
author: Machiel Veltkamp
header:
  overlay_image: /assets/images/roboarm_header.jpg
  image_description: "Dobot Magician arm"
  teaser: /assets/images/roboarm_header.jpg
tags: 
  - robotics
  - development
  - robot arms
---

# Introduction

Robotics is a term describing a very broad and wide field of machines, devices, technologies and even philosophy or vision of our current or future society. Thinking of robotics different images come to mind. One of these common images is the image of the almost fully automated car factories where long rows of robot arms seamingly without effort construct car part after car part. 

{% include figure image_path="/assets/images/robotarm_carfactory.jpg" alt="Robot arms making cars" caption="Robot arms making cars" %}

Meanwhile robotic arms are now longer just reserved for industrial use. Nowadays there exist robotic arms in all different kind of shapes and sizes. 
With this blog post I want to share my research into the different types of robot arms that are available on the market to buy right now. Many of them come in kits and with the rise of 3D printing there has grown a enthusiastic community of tinkerers that design, print, build and solder their own robot arms.


## Types of robotic arms

The research into robotic arms is geared towards reasonable affordable table top size arms and therefore exclude the bigger and more industrial robots you could get like [Baxter](https://www.rethinkrobotics.com/baxter/) or the different available [Kuka arms](https://www.kuka.com/en-de) 
The robotic arms form the research can roughly be divided into two categories. The first categories is the Arduino/RaspberryPi based arms, which are mostly DIY kits powered by an Arduino or RaspberryPi. The second category is the “buy it on kickstarter” category which are mostly bigger more sophisticated arms that were developed and sold using a kickstarter campaign.

## Things to look for when buying a robotic arm

Most robotic arms are subdivided in how many degrees of freedom (DOF) they have. This refers to how many rotational joints a robot has. These are sometimes also called “axes”. For example, a 4DOF (4 Axis) robot arm will have four discrete axes of motion. More degrees of freedom means more joints that can move so more possibilities of movement, but also more motors which will increase the price.

The different available arms are made of a wide range of materials which greatly influence the build quality of the arms. This will also determine in part what their possible payload can be meaning how much they can lift. Another factor for the payload is the number and type of motors that are being used this will greatly influence the quality of the arm.

The better quality of motors is the more fluent and precise the arm can be, but the more expensive the arm will be, because of the cost of the motors.

Besides the quality of material of the arm, the quality of the motors another important factor is how  the arms are controlled. Some arms are controlled by an Arduino or arduino-like-board others by a Raspberry Pi, a combination of these two or a custom controller. It is important that there is a way you can easily program the robotic arm to execute your commands.




# The Arduino/Raspberry Pi arms

## TINKERKIT BRACCIO 

*[Link](https://store.arduino.cc/tinkerkit-braccio)*  | *Price 240 euro*

{% include figure image_path="/assets/images/roboarm_arm1.jpg" %}

Braccio is a fully operational robotic arm that has been designed for desktop use and connects to an Arduino board for control functions. Users can assemble it in a number of different ways to meet application requirements. The arm integrates six servomotors for positional control, enabling it to pick up and move objects. It can be used to support a wide variety of objects for different applications – for example, as an automated tracking camera mount or a solar-panel positioner to track the sun, or to mount a mobile phone or tablet to follow attendees on a videoconference. The Braccio offers a load capacity of up to 400g in the minimal configuration and a maximum weight of 150g at an operating distance of 32cm.

The Arduino TinkerKit range provides a platform to prototype Arduino-based designs without the need for breadboards or soldering irons. The TinkerKit delivers a simple and quick set-up including sensor and actuators that connect to the TinkerKit interface and the Arduino control board via the Arduino Sensor Shield.

## Ultimate 2.0 robot kit / Makeblock

*[Link](https://www.kiwi-electronics.nl/kadotips/ultimate-robot-kit-2-0-blauw)* | *Price: 365 euro*

{% include figure image_path="/assets/images/roboarm_arm2.jpg" %}

Makeblock is robotic /mechatronic platform with parts made from anodised aluminum with a clever design, many features and is open for other platforms. Makeblock is a good choice to make all kind of robots. They have many parts which can be combined to create many different things. The Ultimate 2.0 robot kit a good example of a collection of parts which enables you to make a robot arm or one of the ten other possibilities. Ultimate 2.0 is the flagship kit of Maekblock 

## MeArm

*[Link](https://shop.mime.co.uk/collections/mearm)* | *Price: 80 euro*

{% include figure image_path="/assets/images/roboarm_arm3.jpg" %}

MeArm is a robotic arm from the company Mime. At it’s center is the RaspberryPi. The MeArm Pi can be controlled directly through the on-board joysticks, or you can learn to code by making it move using one of the many programming languages run on the Raspberry Pi. All of the software is free and covers a wide range of skill levels, from absolute beginner to experienced programmer. To make things even easier, it can all be controlled straight from your web browser, with no need to buy additional hardware like monitor, keyboard and mouse.


# The Kickstarter campaign Arms

## DOBOT Magician

*[Link1](https://www.dobot.cc/dobot-magician/product-overview.html) / [Link2](https://www.youtube.com/watch?v=1HB6FfNqF1s* | *Price: 1650 euro)*

{% include figure image_path="/assets/images/roboarm_arm4.png" %}

The Dobot Magician was funded using a Kickstarter campaign in september 2015. It is a desktop robot arm which connects with your computer over USB, WiFi or Bluetooth. You control it using their own software called: “Dobot studio . You can learn it moves by grabbing it and teaching it the movements. The arm has different ports and extension possibilities. You can equip the arm with different accessories for different tasks such as a suction cup, a pen holder or a laser cutter.

## DOBOT M1

*[Link](https://www.dobot.cc/dobot-m1/product-overview.html)* | *Price: 5000 euro*

{% include figure image_path="/assets/images/roboarm_arm5.png" %}

The second robot by DObot is the Dobot M! Which was also funded using a kickstarter campaign in november 2016. It is also a desktop robot arm sold as a industrial robot for small businesses. You can connect with it over Wifi and Bluetooth and just like the Magician it has different interchangeable heads for different tasks

## Dorna

*[Link](https://www.dorna.ai/)* | *Price: 1200 euro ??? / project is still under development*

{% include figure image_path="/assets/images/roboarm_arm6.png" %}

Dorna is a affordable 5 axis robot arm funded by Kickstarter in october 2017.  The goal was to create an robot arm with high-end specs for a low-end budget. The arm can be outfitted with different heads enabling you to do a wide variety of things with it. The arm is connected through USB with a computer and can be controlled using Dorna Lab which is opensource software. 
At the moment though is seems you can only download the binary of the software for Windows.
The arm is set to ship in June 2018.

## Niryo One

*[Link](https://niryo.com/niryo-one/) | Price: 1300 Euro*

{% include figure image_path="/assets/images/roboarm_arm7.png" %}

The Niryo one is yet another open source robot arm funded through a kickstarter campaign started in september 2017 and the robots were shipped at september 2018. The robot arm is based on a raspberry pi with Arduino and runs on ROSS. The robot comes across a little wobbly, but it has a Github repository for the code (https://github.com/NiryoRobotics/niryo_one) and a reasonable active community.

## uArm Swift / Pro

*[Link](https://www.indiegogo.com/projects/uarm-swift-your-personal-robotic-assistant)#/* | *Price: 78 euro*

{% include figure image_path="/assets/images/roboarm_arm8.jpg" %}

The uArm Swift/Pro was funded using Indiegogo campaign in march 2017 and can now be bought from the website. It is based on Arduino and supports Arduino, Python, GRABCAD and ROS programming. It can be extended with different heads and comes with a github where you can find the SDK for C++ and Python. It is made by uFactory.

## xArm

*[Link](https://www.ufactory.cc)* | *Price: < 10.000euro*

{% include figure image_path="/assets/images/roboarm_arm9.jpg" %}

The xArm is the second robotic arm developed by uFactory. It is a bigger and more serious robot arm then the uArm meant for industrial use in small/medium businesses. It will be available with 5,6 or 7 rotation axis. You can find more information about the arm [here](https://www.ufactory.cc/?gclid=Cj0KCQjw0dHdBRDEARIsAHjZYYB9EdOKpsWios1gx_Egmm4zGlO4YohCazes6hN8wUpMGEuAPUhkPWUaAkwSEALw_wcB#/en/xarm) It is not clear yet when it will be ready for sale.

## Thor

*[Link1](https://github.com/AngelLM/Thor) / [Link2](https://hackaday.io/project/12989-thor)* | *Price: 500 euro (in parts)*

{% include figure image_path="/assets/images/robotarm_arm10.png" %}

Thor is a complete DIY robot arm meaning that the only thing you can “get” is the Github repository. From there you will need to buy all the parts separately and 3D print the body of the robot yourself. From all the “kickstarter campaign” category robots this is the only true opens source robot arm in my opinion.

## RobotGeek Snapper Arduino Robotic Arm

*[Link](https://www.robotgeek.com/robotgeek-snapper-robotic-arm)*

{% include figure image_path="/assets/images/robotarm_arm11.jpg" %}

The RobotGeek Snapper is a sturdy 4 DOF full metal robot arm featuring custom built servos for a payload of over 50 grams, and a reach of around 29 cm from the shoulder to the gripper.

The arm comes with everything you need to get started, including the Geekduino/Arduino board, ships in one kit, and even includes a 3-joystick control panel. The claw uses a parallel grip system for actuation, giving this arm a firm handshake, which is to say, it has a really strong grip.  It seems this robot arm has an extensive online documentation with different example projects that has been made with this arm.

## Trossen Robotics

*[Link](https://www.trossenrobotics.com/)*

{% include figure image_path="/assets/images/robotarm_arm12.jpg" %}

Trossen robotics is an company that has different robot arms in their product catalogue ranging from an arduino based mode of 240 euro up until metal hardware arms up until 4000 euro.
From the design the arms seem very sturdy, with a good build quality. All arms come fully assembled and tested, but you mostly buy the hardware and need to do your own programming to get them moving.


# Links

* [Top 10 Robotic arms in 2018 (curated by dobot)](https://www.dobot.cc/resource/top-10-robotic-arms-in-2018-review.html)
* [Best Entry-Level Robotic Arm on the Market](https://www.fullydroned.com/best-robotic-arm-kit/)
* [Article about robots and artificial intelligence](https://www.technologyreview.com/s/611424/this-is-how-the-robot-uprising-finally-begins/)
* [How to buid a robot arm based on MeArm](https://lifehacker.com/build-a-kickass-robot-arm-the-perfect-arduino-project-1700643747)
* [How to build a robot arm yourself](https://www.instructables.com/id/ROBOTIC-ARM-Arduino-Controlled/)
* [Top 5 Arduino based robot arms](https://all3dp.com/2/arduino-robot-arm-the-5-best-robot-arms-for-your-arduino/)



