---
permalink: /
title: "Portfolio of Projects"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

<style>
  body {
    text-align: justify;
  }
  .author__bio {
    text-align: left !important;
  }
</style>

Hello! I'm Isaac, a PhD Student in Mechanical Engineering and a passionate roboticist. Welcome to my personal website! This space is a hub for me to gather some of my best engineering projects and to present my [ongoing research](/research/) with the University of Sherbrooke (Canada).
To introduce myself in a few words, I like to invent things, especially if these things do not exist or do not operate as they should! I enjoy solving problems through creative thinking and fast prototyping, and one of my favorite parts of any project is the inital brainstorming/creative phase where all ideas are accepted and explored, before converging towards a solution. 

Although my research in the last years has mostly been focussed on aerial robotics, I've had the chance to play around with a lot of other robotic platforms through my internships and personal projects. These include acrobatic robots ([Disney Research](https://la.disneyresearch.com/)), [flight simulator with virtual reality](#aerostrabe) (senior undergrade project), [robotic grippers](#gripper)  (PhD side project), [4-wheel robots](#csquare) (personal) and C++/Python projects such as [drone simulations](#dronesim_ROS) (ROS + Gazebo), [motion planning algorithms](#rrt) (Matlab), financial websraper (python) and [particle animator](#particleanimation) (C++).  
Below is a quick presentation of some of my past projects, starting with the coolest.

<!--Lets go in coolness order -->

<a id="aerostrabe"></a>
## Aerostrabe -- A fully immersive 4-DOF VR-integrated flight simulator to experience the urban air mobility of the future
For our senior undergrade project, my team and I (6 mechanical engineering students) decided to create a complete multisensorial flight simulator from scratch! The vision: An immersive single-seat multirotor flight simulator that enables inventors and investors alike to fully experience the urban air mobility of the future.

Here is the final product:
<div style="margin-bottom: 20px;">
<iframe 
  width="560" 
  height="315" 
  src="https://www.youtube.com//embed/aee_68XI4RY" 
  frameborder="0" 
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
  allowfullscreen>
</iframe>
</div>

**How does it work?** A 4-DOFs motion system moves the platform to create realistic sensations of accelerations, while a VR headset immerses the pilot (the simulator's user) in a virtual city made with Unreal Engine. The pilot uses ATV-style intuitive tactile commands to control the flying vehicle and uses its own weight to move from side to side, through load-cells placed under the seat and feet. Finally, based on the pilot commands, a semi-realistic dynamic model of the vehicle (in Python) is used to compute flight behavior, which is synchronized with the virtual world and simulator motion, while fans in the front are used to simulate wind and increase realism.

**Team members:** Alexis Bédard-Meunier, Julien Labbé, Julien Charbonneau, Charles-Étienne Gauthier, Benoit Beaupré and Isaac Tunney  
**Main sponsors:** Imaginactive, BRP, Epic Games (Epic MegaGrants)  
**Other sponsors:** CSTM, Chair in Design for Aluminium, Gosselin, D-BOX, Exp., Shellex, WCB, Royal Lepage  

<a id="gripper"></a>
## High-Impact-Load Quick-release Novel Gripper for Acrobatic Robots
Embedded youtube video

<a id="csquare"></a>
## Omnidirectional Robot to Interact and Play with your Pets
My dog Charlie, as any good Covid-19 dog, has some issues with the idea of staying home alone. He also has a true passion for fetching tennis balls, although he struggles with the part where he has to give it back. This gave me the idea to create a small omnidirectional 4-wheel robot that can move around in the house, launch a tennis ball and give a treat when my dog brings the ball back to the robot. This way, Charlie can play and fetch a ball while I'm working!

Here is a little demo of the robot in action with Charlie:
(Video link here)

**How does it work?**  
The mobile platform uses 80-mm mecanum wheels to move in any direction (holonomic system), and a Teensy 4.1 for the low-level control of the platform. 
The main (higher level) control system runs on a Raspberry Pi 4B and is connected to the Internet. A Pi Camera is used to detect objects such as the tennis ball and to do SLAM for navigation in the house/appartment. The mechanisms for the ball launcher and treat dispenser are all custom parts 3D printed on a Markforged Onyx One. 

<a id="dronesim_ROS"></a>
## Drone Simulations with ROS and Gazebo
Here, I decided to have fun with multi-drones ROS & Gazebo simulations! This was based off of X's work and tutorials --> XX.

<a id="dronesim_python"></a>
## Drone Simulations in Python

<a id="rrt"></a>
## RRT motion planning for UAV in full 2D state space
There is an algorithm called [Rapidly-Exploring Random Trees](https://journals.sagepub.com/doi/10.1177/02783640122067453) (RRT), which is often used for path planning, but also sometimes for motion planning. It works by randomly exploring a predefine space and connecting new points to their nearest neighbors to promote rapid exploration of the map. 

<div style="display: flex; justify-content: center; margin: 10px 0;">
  <img src="/images/basicRRT.gif" alt="RRT Animation" style="max-width: 100%; height: auto; border: 1px solid #888; border-radius: 4px;">
</div>
<div style="text-align: center; font-size: 0.9em; color: #555">
  (Source: <a href="https://lavalle.pl/rrtpubs.html" target="_blank">https://lavalle.pl/rrtpubs.html</a>)
</div>  
<br>
I decided to explore how I could use it and modify it to actually explore the full state space of a 2D drone to generate full body motions. My algorithm works as follows:
It explores the 2D state space of the drone (positions, velocities, pitch angle and pitch rate) and generates trees in the 6 dimensions until it reaches its goal while keeping track of force/torque inputs. Once the goal is reached, its plays back the force/torque sequence to bring the drone to its goal.

Here is an example flying from point A to B:
<div style="display: flex; justify-content: center; margin: 10px 0;">
  <img src="/images/droneAnimationRRT.gif" alt="RRT Drone Animation" style="max-width: 100%; height: auto; border: 1px solid #888; border-radius: 4px;">
</div>

I have only tested it on basic use cases such as moving from point A to B, but long term this could potentially be used to explore more complex drone maneuvers.

<!-- https://lavalle.pl/papers/LavKuf01b.pdf
 https://lavalle.pl/rrtpubs.html)

## The Perfectly-Clear-Ice Maker
Lately, I've been exploring the idea of making perfect cristal clear ice at home. Some companies already specialize in making clear ice for sculpting competitions or for fancy restaurants, but the commercial small-scale solutions currently out there are quite large. This is due to the fact that the typical solution to make clear ice is to ensure directional freezing, often done with good insulation on the ice tray sides and top or bottom, to have either top-to-bottom freezing or vice versa. However, all the retailer products are quite large and/or expansive. That got me thinking: Could I make my own custom clear-ice maker using inexpensive existing products and a bit of creativity?
The answer is yes! ... -->

<a id="particleanimation"></a>
## Particle Explosion Animation in C++
During my undergrade in mechanical engineering, I also wanted to learn how to code (more than just Matlab), so I took online C++ and Python courses on Udemy. Here is a particle animation I made in C++ through one of the courses!

<!-- <div style="display: flex; justify-content: center; margin: 20px 0;">
  <video controls autoplay muted loop style="max-width: 100%; border: 1px solid #888; border-radius: 4px;">
    <source src="/images/particleAnimationCut.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</div> -->

<div style="display: flex; justify-content: center; margin: 20px 0;">
  <video controls autoplay muted loop
    style="width: 860px; height: 450px; object-fit: cover; border: 1px solid #888; border-radius: 4px;">
    <source src="/images/particleAnimationCut.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</div>


<!-- This is the front page of a website that is powered by the [Academic Pages template](https://github.com/academicpages/academicpages.github.io) and hosted on GitHub pages. [GitHub pages](https://pages.github.com) is a free service in which websites are built and hosted from code and data stored in a GitHub repository, automatically updating when a new commit is made to the repository. This template was forked from the [Minimal Mistakes Jekyll Theme](https://mmistakes.github.io/minimal-mistakes/) created by Michael Rose, and then extended to support the kinds of content that academics have: publications, talks, teaching, a portfolio, blog posts, and a dynamically-generated CV. You can fork [this template](https://github.com/academicpages/academicpages.github.io) right now, modify the configuration and markdown files, add your own PDFs and other content, and have your own site for free, with no ads!

A data-driven personal website
======
Like many other Jekyll-based GitHub Pages templates, Academic Pages makes you separate the website's content from its form. The content & metadata of your website are in structured markdown files, while various other files constitute the theme, specifying how to transform that content & metadata into HTML pages. You keep these various markdown (.md), YAML (.yml), HTML, and CSS files in a public GitHub repository. Each time you commit and push an update to the repository, the [GitHub pages](https://pages.github.com/) service creates static HTML pages based on these files, which are hosted on GitHub's servers free of charge.

Many of the features of dynamic content management systems (like Wordpress) can be achieved in this fashion, using a fraction of the computational resources and with far less vulnerability to hacking and DDoSing. You can also modify the theme to your heart's content without touching the content of your site. If you get to a point where you've broken something in Jekyll/HTML/CSS beyond repair, your markdown files describing your talks, publications, etc. are safe. You can rollback the changes or even delete the repository and start over - just be sure to save the markdown files! Finally, you can also write scripts that process the structured data on the site, such as [this one](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.ipynb) that analyzes metadata in pages about talks to display [a map of every location you've given a talk](https://academicpages.github.io/talkmap.html).

Getting started
======
1. Register a GitHub account if you don't have one and confirm your e-mail (required!)
1. Fork [this template](https://github.com/academicpages/academicpages.github.io) by clicking the "Use this template" button in the top right. 
1. Go to the repository's settings (rightmost item in the tabs that start with "Code", should be below "Unwatch"). Rename the repository "[your GitHub username].github.io", which will also be your website's URL.
1. Set site-wide configuration and create content & metadata (see below -- also see [this set of diffs](http://archive.is/3TPas) showing what files were changed to set up [an example site](https://getorg-testacct.github.io) for a user with the username "getorg-testacct")
1. Upload any files (like PDFs, .zip files, etc.) to the files/ directory. They will appear at https://[your GitHub username].github.io/files/example.pdf.  
1. Check status by going to the repository settings, in the "GitHub pages" section

Site-wide configuration
------
The main configuration file for the site is in the base directory in [_config.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_config.yml), which defines the content in the sidebars and other site-wide features. You will need to replace the default variables with ones about yourself and your site's github repository. The configuration file for the top menu is in [_data/navigation.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_data/navigation.yml). For example, if you don't have a portfolio or blog posts, you can remove those items from that navigation.yml file to remove them from the header. 

Create content & metadata
------
For site content, there is one markdown file for each type of content, which are stored in directories like _publications, _talks, _posts, _teaching, or _pages. For example, each talk is a markdown file in the [_talks directory](https://github.com/academicpages/academicpages.github.io/tree/master/_talks). At the top of each markdown file is structured data in YAML about the talk, which the theme will parse to do lots of cool stuff. The same structured data about a talk is used to generate the list of talks on the [Talks page](https://academicpages.github.io/talks), each [individual page](https://academicpages.github.io/talks/2012-03-01-talk-1) for specific talks, the talks section for the [CV page](https://academicpages.github.io/cv), and the [map of places you've given a talk](https://academicpages.github.io/talkmap.html) (if you run this [python file](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.py) or [Jupyter notebook](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.ipynb), which creates the HTML for the map based on the contents of the _talks directory).

**Markdown generator**

The repository includes [a set of Jupyter notebooks](https://github.com/academicpages/academicpages.github.io/tree/master/markdown_generator
) that converts a CSV containing structured data about talks or presentations into individual markdown files that will be properly formatted for the Academic Pages template. The sample CSVs in that directory are the ones I used to create my own personal website at stuartgeiger.com. My usual workflow is that I keep a spreadsheet of my publications and talks, then run the code in these notebooks to generate the markdown files, then commit and push them to the GitHub repository.

How to edit your site's GitHub repository
------
Many people use a git client to create files on their local computer and then push them to GitHub's servers. If you are not familiar with git, you can directly edit these configuration and markdown files directly in the github.com interface. Navigate to a file (like [this one](https://github.com/academicpages/academicpages.github.io/blob/master/_talks/2012-03-01-talk-1.md) and click the pencil icon in the top right of the content preview (to the right of the "Raw | Blame | History" buttons). You can delete a file by clicking the trashcan icon to the right of the pencil icon. You can also create new files or upload files by navigating to a directory and clicking the "Create new file" or "Upload files" buttons. 

Example: editing a markdown file for a talk
![Editing a markdown file for a talk](/images/editing-talk.png)

For more info
------
More info about configuring Academic Pages can be found in [the guide](https://academicpages.github.io/markdown/), the [growing wiki](https://github.com/academicpages/academicpages.github.io/wiki), and you can always [ask a question on GitHub](https://github.com/academicpages/academicpages.github.io/discussions). The [guides for the Minimal Mistakes theme](https://mmistakes.github.io/minimal-mistakes/docs/configuration/) (which this theme was forked from) might also be helpful. -->