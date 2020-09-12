# vTuber-Virtual-Production-Studio-Assets

![](https://i.imgur.com/2kgB34a.jpg)

## Summary
This is an asset pack for doing virtual productions. You can apply these assets and workflows to your games, or vr simulations to capture multi-camera realtime footage from within a video game running Unity3d. This package would be a good starting point for anyone interested in a do-it-yourself approach to making virtual productions inside Unity. 

Inside Unity, you can import / create your own set and then use this camera system to help you speed up production with access to 9 cameras, and 12 overlay slides.

## What is Included
Included is the this package are the assets to make a full studio environment setup for virtual production in Unity3d. We arrage the multi-camera assets to fit each unique production. (podcast, film, vfx, performance, vr room, stream, vTubing) 

There are no avatars included, but this package is a great starting point to create a virtual world to produce content on the platform you would like to create content on. 

## Instructions 
(C# control system included in _assets version runs in the Editor when you push Play)
* 1-9 keys will swap between cameras
* 0 goes to Overlay mode to display 

Slides (Use Numeric Keypad)
* 0-9, (.), (+) to change slides
* F - Map Cam To Screen
* R - Realtime Reflection Probe
* L - Camera Light
* U - Toggle All Cameras
* P - Camera Previews Toggle
* T - Studio Lights Toggle

## Camera Controls
When the keyboard controls are pressed (1-9) the camera seleted will be Set to Active, while the others are set to Inactive. This will feed the main camera output(render texture) The camera previews can be seen on the camera preview panel using Render textures as well( at a lower resolution for optimization. ) The camera previews are a duplicate of the main camera with all of the exact same parameters, except they feed a render texture so that you can preview the cameras before switching.

## General Workflow
To make a custom production, we create and customize a set, configure the locations of the cameras, animate the cameras, then during runtime, we use the camera control panel to switch between these cameras with a camera operator in real time. We have a version of this studio running inside VRChat, and use that software as our networked IK, motion capture, and avatar layer. We are capturing the video output with OBS (Open Broadcast Software) from the game engine we are rendering our scene in. 

Depending on the platform you are planning to work on. The approach will be different. Currently we use platforms like VRChat (Unity3d), and Unreal Engine to do virtual productions over the network.

It is common to use many platforms to create a virtual production.

## Slides / Overlay
This system was designed with presentations in mind so we have an extra camera that renders planes in front of a camera to create the illusion of an Overlay by pushing 0. It is sort of a work around, and if you would like to extend or make this package better or more optimised, please feel free to submit a pull request. Thanks!

We swap out 12 different Slides(show/hide gameObjects) using the numeric keypad and also the (.) key and the (+) key. 

You can swap out the pictures of the slides before building the production, by editing the materials. We import jpegs, and add them to the respective materials before we do the production. A possible extention to this would be to use a URLLoader to have dynamic materials and slides. 

## Arranging The Cameras
Move the cameras (via the Parent Object) and feel free to animate or extend the cameras to do even more things like add more scripts and functionality as needed. If the camera is designed to be moved as rigid body, make sure to put the rigid body, and pickup scripts on the parent object to maintain the camera heirarchy. Arrange the cameras around your set by translating the cameras manually, and checking the camera preview object to see how it looks in frame.

## Pro-Tip: 
Because of the way the camera previews work, you should only move the Master Root of each camera. You can add an additional Parent object to the cameras if you like, and animate those for animated camera tracks. The switches use SetGameObjetActive to turn on and off the cameras. I didn't use an array, and instead used conditions and input to swap cams, because of uSharp (VRC SDK constraints) and kept the code as simple as possible. The code can be re-written, and of course extended to do many more things than just switch cameras. i.e. Zoom camera shake, change post porocessing lens.

## Camera Culling / Hiding Objects From Cameras
If you would like to hide / show things in the camera output, you would setup layers and use camera culling with a "SeenByCamera" layer and "GreenScreen" culling layers for teh reflection probe not to reflect the greenscreens.

## Dependencies
This .unitypackage was built on Unity 2018.4.20f1 (with VRChat in mind)
The cameras use some "movement" scritps from the Standarad Assets (https://assetstore.unity.com/packages/essentials/asset-packs/standard-assets-for-unity-2017-3-32351)
VRChat SDK will be needed to use the Template packages (for Multiplayer VR Builds)

The camera control script is very basic to get you started with virtual prodcutions. They were coded in a way to make it easier to port to VRChat / uDon / uSharp. (certain functions and classes are not available inside VRChat SDK3)

VRC SDK2 Complete Project https://drive.google.com/file/d/15jAm3EPSTKnkhMjjMzsJxeEzn09iHol_/view?usp=sharing

## Versions Of This Camera System
There are different versions of this suite. This is the BOILERPLATE version that will run in the Editor and in Play Mode to demonstrate the controls of the camera system and workflow of a virtual studio and designed to be extended. 

## Template VRChat MultiplayerStudio 
We have a template vTuber Studio availible as a drag and drop prefab, that works with VRC SDK2. With this prefab you can make your own production studio inside VRChat by customizing the environment and uploading to VRChat's servers.

## Custom VRChat Multiplayer Studio
Our crew is available for commission to create CUSTOM VR Production studios for podcasts, music videos, films, concerts, events, and other productions. We will curate models based on the budget and design, lighting, and customize your production studio to meet your needs. If you have any custom productions in mind, please feel free to reach out! @godfreymeyer

## Examples
Please check out the examples and tutorials on my youtube page to get familiar on the workflow on virtual prodcutions. These asset can be ported to work in any game engine, and the basic camera control scipts have been written in C# and would have to be ported to work on other platforms tah Unity. Using platforms like VRChat, we have filmed many music videos, podcasts and events in VR using this system as a base. It has sped up production when making rooms or builds for vTubing, vPodcasts, and vFilms, and endless "over the network, real-time collaborative" projects. 

## Web Resources:
http://Unity3d.com/
http://vrchat.com/
https://assetstore.unity.com/packages/essentials/asset-packs/standard-assets-for-unity-2017-3-32351

Special thanks to Jin, the VR Devs, and the Web XR community for helping in various way to make this possible.

Please subscribe to my youtube page http://www.youtube.com/godfreymeyer and check out more on my guthub github.com/gm3 Much love!

## Contact

Please check out some our productions on [Youtube](https://www.youtube.com/results?search_query=godfrey+meyer&page=&utm_source=opensearch) "Godfrey Meyer" or [#boomboxhead](https://www.youtube.com/results?search_query=%23boomboxhead) to find videos. If you have any questions please feel free to reach out to me #boomboxhead on discord `painterpainting#5603`. Have fun and link me to the videos you make, thanks!

If you would like to support this project please donate to http://streamlabs.com/boomboxheads to help cover development costs, if you are a crypto homie my ETH addy is `0x670A6EB62f5146d4B3B40C7b58AA31d175E3d6Fb` much love!
