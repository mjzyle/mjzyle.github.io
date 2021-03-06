---
layout: post
title: Lights, Camera, Action! Part 1
---

*This post is part of an ongoing series following my progress on [ZRender](https://github.com/mjzyle/zrender), a custom OpenGL rendering and development framework.*

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

## Cameras

I did say those goals were in no particular order, right? 

Since I've worked with manipulating OpenGL viewing space in the past, setting up a camera object seemed like the easiest starting point. Of course, a camera's useless without something to look at, so the *real* starting point (after initializing OpenGL and GLUT) was implementing a mesh reader. My Computer Graphics course provided a useful mesh reader for standard .obj files which uses mass allocation for storing vertex and face data, so I implemented that procedure with minor variations (namely the ability to store object data into an array of objects rather than a single list since I want my framework to handle scenes with multiple meshes). 

Once I had a way of reading a single mesh, I extended this procedure to read a custom filetype which simple lists all of the objects in the scene in a way similar to a .obj file (the file for the early test scene I used can be found [here](https://github.com/mjzyle/zrender/blob/master/zrender/scene.txt)). Objects are marked with an 'o' followed by the name of the mesh to be loaded and the translational coordinates for defining the object's initial position (rotation is not currently taken into account).

With a scene reader in place, I simply implemented a render loop to draw each object as a wireframe and got a scene much like this:

![Scene](/images/ZRender/LCA-1/scenereader.png "Basic Scene")

At this point I started working on the camera controls. 

------

In my next post I'll be covering some of my progress on implementing lighting and shading. Until then, here's a sneak peek at some of the fun stuff I'll be showing off - hairy spheres and teapots!

![Sneak Peek](/images/ZRender/LCA-1/sneakpeek.png "Sneak Peek at Lighting")

*Check back here for a link to Part 2 once it's posted!*
