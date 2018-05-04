# Final Project Guidelines

## Overview

The last stage of KWK is called 'project mode.' Students will be building real
applications, using the Sinatra, HTML and CSS they've learned. The goal of this
period is to expose Scholars to actual problems that arise when building and
teach them how to manage a big project. The goal of the projects is not to
launch a massively popular social network or startup, but rather, just to learn
and have fun!

While we love teaching all the things about programming, in the end, we're
trying to build things, and that isn't something we believe can be taught, but
rather, must be learned by trying and failing and exploring.

*Note:* Refer to KWK Teaching Guide for detailed instructions on setting up and
running project mode, including how to make groups, pick projects, brainstorm,
as well as some general tips for keeping students on track and having fun.

## Setting Up

Setting up groups of 2 may be ideal for encouraging pair programming (switching
off between driver/navigator) and to make sure all students are involved.

To allow focus on applying what we've learn during this course, students should
use the [KWK Sinatra Starter](https://github.com/learn-co-curriculum/kwk-sinatra-starter).

Students each have their own fork of this starter code, which should be noted:
Students _can_ work on different parts of the project at the same time, but will
need to either share the code they've written with the person who has the main,
forked project, or they can use GitHub (truncated instructions below).

This app can be about anything each groups decides to build.  Some things to
keep in mind in terms of what we've learned how to make:

* We can make multipage applications using Sinatra routes
* We can display dynamic content using ERB (including loops and conditionals)
* We can structure a site, and populate it with text, images, animations,
dividers, boxes, even video by just using HTML
* We can style and shape our site in any which way using the power of CSS.

## Ideation

Students should take some time within their groups to decide what they would
like to build as their project.  

*Note:* Beginners have a tendency to choose very hard projects. Pick a project that you
can imagine having a somewhat working version of after a day. Keep it simple and
small.  Ideas should be buildable using the Sinatra/HTML/CSS we've learned (i.g.
avoid interactive games, as they rely mainly on JavaScript).

From the Teaching Guide:

1. Pick out our audience. Who are we making this for? -In the real world we would
do a market study. We’d really get to know who these people are. For our
purposes, let’s pick one person or group of people we know (it could be
ourselves, our friends, parents, teenagers, etc...) and take a moment to think
about them.
* What do they like?
* What makes them happy?
* What do they hate?
* What would make their lives easier?
* What problems do they have? Have students pick a demographic and follow through
these steps.
2. Let’s brainstorm. Act like a beginner. Pretend there are no constraints. For 5
minutes come up with as many ideas as you can. There are no wrong answers. Just
keep adding ideas, don’t think. Add ideas to post-it notes or whiteboard.
3. Let’s figure out our constraints.
* We will need to use X/Y/Z technologies
* Don’t want to uses A/B/C
4. Let’s pick out potential projects that we like/might fit from our list. For each
project explain it to a partner or group. Get their feedback. Listen to their
ideas.
5. Let’s build a mockup/prototype

## Starting the Projects

Students should have fun first, but it may be good to give them some direction
when they are building their application.  After brainstorming and laying out a
rough idea of what their application will look like, students should work with
their groups to decide how to get started. There _are_ a number of steps that
must be done first, just to get something displaying on the page.

*Note:* if students need suggestions on what to do to start, to get off the ground
and start designing web pages, students will need to do the following:

* Set up their Sinatra route(s).  Before adding HTML, have the route
display a string like "Hello World", and make sure it is being displayed when
`shotgun config.ru` is run in the terminal.
* Create a basic HTML page. Save this page as `index.html.erb` inside the views
folder in the project.
* Rewrite the "Hello World" Sinatra route to `erb :'index.html'` to display
the newly created page


### Sharing the Workload

Students should get some experience pair programming in both roles - so one
student is typing (driving) while the other is directing what needs to be typed
(navigating).  Students can, however, work on separate parts of the project at
the same time and share the code they've written. If there are any groups of 3
or more, this may be necessary to make sure all students are engaged and have
something to do.

### Stretch Features

If students have built out their HTML and are not sure what to do next, they
can try to add stretch features, such as:

* Add the same navigation to each page on the app, that links all pages.
* Add video using the HTML `<video>` element
* Add bootstrap (using a link to their CDN in the HTML head) and additional
styling
* Add buttons

### Finishing Up

If students would like to publish their work to show the world, they can do so
for free using [Heroku](heroku.com).  The project is currently on one student's
kwk-sinatra-starter repository. To publish the app, that student will need to:

  * Create a free Heroku account and connect their GitHub account
  * Choose to **New** and create a new app on Heroku's website
  * Name the app (this will be in the URL, so name it something relevant to the app
  you built), and create it
  * You should be directed to the _Deploy_ page. Scroll down and in the 'Deployment
  Method' section, click **GitHub**.
  * Just below Deployment Method, you should be able to search for a repository on
your account.
  * The repository name is the name of the project folder you see on the learn IDE,
starting with 'kwk-sinatra-starter...'
  * Click connect when the repository is found
  * Click **Enable Automatic Deploys**
  * Click **Deploy Branch**

Deploying will open a small terminal on the page that runs through the process.
If all goes well, the terminal will display Done, and a **View** button should
appear linking to your newly deployed site.  If students continue to work on
the project, the updates should show up, though may not be immediate.
