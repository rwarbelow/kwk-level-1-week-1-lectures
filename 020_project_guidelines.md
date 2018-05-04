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
when they are building their application.  As a suggestion, after brainstorming
and laying out a rough idea of what their application will look like, students
should do the following to get started:

* First, set up their Sinatra route(s).  Before adding HTML, have the route
display a string like "Hello World", and make sure it is being displayed when
`shotgun config.ru` is run in the terminal.
* Create a basic HTML page. Save this page as `index.html.erb` inside the views
folder in the project.
* Rewrite the "Hello World" Sinatra route to `erb :'index.html'` to display
the newly created page
* Add in ERB and CSS 


### Sharing the Workload

Students should get some experience pair programming in both roles - so one
student is typing (driving) while the other is directing what needs to be typed
(navigating).  Students can, however, work on separate parts of the project at
the same time. If there are any groups of 3 or more, this may be necessary to
make sure all students are engaged and have something to do.

One example of working on separate parts would be having students work to
create different pages of their app


## Requirements

1. Build an MVC Sinatra Application.
2. Use ActiveRecord with Sinatra.
3. Use Multiple Models.
4. Use at least one `has_many` relationship on a User model and one `belongs_to` relationship on another model
5. Must have user accounts. The user that created a given piece of content should be the only person who can modify that content
6. Must have the abilty to create, read, update and destroy any instance of the resource that belongs to a user.
7. Ensure that any instance of the resource that belongs to a user can be edited or deleted only by that user.
8. You should also have validations for user input to ensure that bad data isn't added to the database. The fields in your signup form should be required and the user attribute that is used to login a user should be a unique value in the DB before creating the user.

### Example Domains

 - [Golf Club Organizer](https://github.com/learn-co-curriculum/example-sinatra-assessment)
 - [Todo List](http://todomvc.com). Each task is part of a list
 - Collection of useful Ruby resources

If you are unsure about a domain or can't come up with an idea, feel free to reach out to fullstack@learn.co for some advice.

### Domains To Avoid

 As we spent a lot of time working with domains similiar to these during the Sinatra curriculum we do not accept these domain designs.
  - Twitter Clone
  - Blog Application

### Recomendations

 You do not have to make your routes any more complicated than `http://yourapp.com/posts/1`. We want to see you build a great CRUD application but we are not requiring you to build the next AirBnB.

## Instructions

1. Create a new repository on GitHub for your Sinatra Application.
2. When you create the Sinatra app for your assessment, add the spec.md file from this repo to the root directory of the project, commit it to Git and push it up to GitHub.
3. Build your application. Make sure to commit early and commit often. Commit messages should be meaningful (clearly describe what you're doing in the commit) and accurate (there should be nothing in the commit that doesn't match the description in the commit message). Good rule of thumb is to commit every 3-7 mins of actual coding time. Most of your commits should have under 15 lines of code and a 2 line commit is perfectly acceptable. **This is important and you'll be graded on this**.
4. While you're working on it, record a 30 min coding session with your favorite screen capture tool. During the session, either think out loud or not. It's up to you. You don't need to submit the video, but we may ask for it at a later time.
5. Make sure to create a good README.md with a short description, install instructions, a contributors guide and a link to the license for your code.
6. Make sure to check each box in your spec.md (replace the space between the square braces with an x) and explain next to each one how you've met the requirement *before* you submit your project.
7. [Fill out this checklist.](https://docs.google.com/forms/d/e/1FAIpQLSdIrS7g6y_B4dAY7HGS4yAndg9bfHuw7GmsiwA6MQXXqNrDjA/viewform?entry.237262577&entry.835010005&entry.301147721)
8. Prepare a short video demo (narration helps!) describing how a user would interact with your working application.
9. Write a blog post about the project and process.
10. When done, submit your GitHub repo's url, a link to your video demo, and a link to your blog post in the corresponding text boxes in the right rail. Hit "I'm done" to wrap it up.

Unlike the rest of the curriculum, if you have any questions about your assessment or need help with it, please *don’t* use the Ask New Question feature. Rather than working with Learn Experts, please reach out to your Learn Instructor responsible for this section instead

## If you're a Learn-Verified Premium student:

We'll send an email to you soon to schedule a pairing process. If you don't hear from us in 48 hours after submission, get in touch!

### Be Prepared to:

1. Confirm your application meets the requirements above. We'll go through your app and ask you to show us how it meets the requirements above. 5-10 mins.
2. Explain your code from execution point to exit point. We're making sure you wrote it and understand how it works. 10-15 mins.
3. Live coding, doing a refactoring exercise to make sure you're comfortable working with your code. 10-15 mins.

### What to expect from the pairing session

Project reviews are focused on preparing you for technical interviews. Treat project reviews as if they were technical interviews, in both attitude and technical presentation.

#### Be scrappy.
- If you make a mistake, correct yourself.
- Think on your feet. We will expect you to be able to explain development concepts to us, as well as expanding on concepts that you have already implemented, but you’ll also have the opportunity to look things up while you're live coding.

#### Make no little plans.
- You're going to learn a ton. We will give pointers and show you ways to improve your code. This isn't telling you that your code is wrong, it's simply us teaching.
- Approach live coding with a constructive attitude. You might feel nervous or uncertain, but as long as you are familiar with the section material you should be able to reason your way to a solution.
- Be proud of your project and your code, and show confidence in it.

#### Radiate positivity.
- Present yourself and your project in the best way possible.
- Be open to feedback, both positive and constructive.
- If the instructor asks you to complete additional features, or you missed a project requirement, treat this as a learning experience. Becoming  a developer is complex and challenging, and it’s our job to find the holes in your knowledge and help you fill them. This is to help you become a better developer, not to delay your progress in the program.

#### Work Together.
- Trust yourself.
- Trust us  - our goal is to help you be successful in achieving your goals.
- We understand that this process can be stressful. We’re here to help you through.

#### Pursue mastery.
- Use the best technical vocabulary you can.
- Explain the details - this is your application, you'll be expected to have a solid understand of how it works"
- Ask questions! Curiosity and willingness to learn are hugely valued in our industry.  If you haven’t heard of something, that’s okay - use this opportunity to learn about it!


### What won't happen:

- You won't be told you're ever wrong
- You won't be yelled at, belittled, or scolded
- You won't be put on the spot without support
- There's nothing you can do to instantly fail or blow it.

<p class='util--hide'>View <a href='https://learn.co/lessons/sinatra-cms-app-assessment'>Sinatra Assessment</a> on Learn.co and start learning to code for free.</p>

<p class='util--hide'>View <a href='https://learn.co/lessons/sinatra-cms-app-assessment'>Sinatra Portfolio Project</a> on Learn.co and start learning to code for free.</p>
