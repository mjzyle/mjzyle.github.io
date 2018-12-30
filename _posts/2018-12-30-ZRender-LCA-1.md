---
layout: post
title: Lights, Camera, Action! Part 1
---

*This is part of an ongoing blog series following my progress on [ZRender](https://github.com/mjzyle/zrender), a custom OpenGL rendering and development framework.*

![Intro](/images/ZRender/LCA-1/intro.png "Camera Progress")

Welcome back! I'm happy you'll be following along with my progress, and I hope you'll stick around to see some of the exciting ideas I have in mind come to life. 

To get there, I've decided to first focus on writing a relatively simple OpenGL framework that I can use as a base for my future projects (affectionately titled *ZRender*). I've found that a lot of my work in OpenGL involves a lot of time spent doing basic setup work over and over again from project to project - things I may or may not actually remember how to do each time I sit down to program! The typical early workflow then becomes looking through old projects to see how I solved problems, refactoring code, trying to figure out why the refactored code won't work, looking up tutorials online, realizing the tutorials are using different toolsets than I am, downloading new libraries...

I decided I want to be done with that, so I'm taking it slow and starting from the ground up this time. And the more I thought about it, the more I realized that my main objectives for having ZRender are summed up pretty well by a familiar filmmaking phrase:  lights, camera, action!

So, in no particular order, here are my immediate goals for ZRender as I've been approaching the project:
* __Lights__: Simple controls for multiple lights. Shaders connected to each object in the scene.
* __Camera__: Basic translation, zooming, and simple rotation around an object using the mouse and/or keyboard to control multiple camera locations. For the time being I've chosen to exclude tilting the camera as I don't imagine this feature being of much use for the immediate projects I have in mind. However, that could certainly change!
* __Action__: A simple animation framework" for drawing and/or manipulating moving meshes. Since it doesn't really fit well into any category, I'm also throwing in point-and-click interaction with the scene using the mouse as an "action" related feature (though I suppose it would be considered more of a *re*action...)

Obviously there are some other elements that I've either implemented already or plan to implement in order to have a usable framework: reading object meshes, transforming objects, setting up the view window, etc. For the most part these steps are fairly trivial and/or have already been implemented in some of my work before, so unless there are major challenges or design decisions worth mentioning, I likely won't go into too much detail about them other than mentioning that the work was done.

Before we jump in to exploring the work I've accomplished so far, I want to give a brief thank you to one of my professors at Case Western Reserve University. I took Computer Graphics with Prof. Cenk Cavusoglu back in fall 2017, and in addition to applying many of the algorithms and techniques learned in that class, I've used a lot of my projects as references for my own code here. I've referred back to the work I did in that class countless times while working in OpenGL and C++ in general, so when a certain implementation in my project is adapted from some of the provided code, I will credit it properly and point out any design deviaitons I may have made.

Now, without further ado, let's get on with the show!



I did say those goals were in no particular order, right? 

