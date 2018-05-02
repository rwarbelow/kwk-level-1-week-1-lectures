# Using Learn

## Objective

Teach students how to start lab work on Learn.co, run tests with the
`learn` command, and submit a lab with `learn submit`. Additionally, 
teach students how to use the Sandbox environment.

## SWABTS

+ USING LEARN - Open a lab with the "Open" or "Open IDE" button
+ USING LEARN - Use the in-browser IDE or the Desktop IDE
+ USING LEARN - Run a labs tests with `learn`
+ USING LEARN - Submit a lab with `learn submit`

## Introductions

Welcome! We are thrilled that you joined our community of learners and
are using learn.co! The Learn.co platform is used to deliver lesson content to
students, and includes its own development environment, the In-Browser IDE,
where you will be able to write and test code, solve problems, and most
importantly, _learn!_

Before students are able to fully use learn, they must sign up for an account on
GitHub.  Steps for connecting a GitHub account to a to Learn.co account are [available here](http://help.learn.co/your-learn-account/github-account/connecting-github-with-learn).

Once all students are signed up and able to log in to their learn.co accounts,
continue on and dive right in with opening a lab.

## Opening a Lab

The instructions and video provided in the lab 'First IDE Lab', along with the
video will give students a better understanding of how to use Learn, though it
may be good to walk through some steps with them.

From the learn.co home page, students should click on to the lab called 'First
IDE Lab' found in the _Curriculum_ tab at the top left of the screen. This will
redirect to their first lab.

<!-- [https://github.com/learn-co-curriculum/kwk-l1-first-ide-lab](https://github.com/learn-co-curriculum/kwk-l1-first-ide-lab)  -->

Once students have opened this lesson, they have two options for how to interact
with and use learn: the In-Browser IDE and the Desktop IDE.  

*Note:* there are two version of this lab on the same page, including two separate
videos! The first half is for desktop IDE users, and the second half is for
in-browser IDE users.

Students can choose either, but the in-browser IDE requires less configuration
to get started, and will open immediately instead of requiring students to
download and install.

Students can toggle between these IDEs by clicking on the user button in the
upper right corner of learn.co, choosing 'Manage Account' from the dropdown,
then going to 'Learn Environment'. Here, they should select the environment they
have chosen to use, in-browser or desktop.  If this is not set correctly, the
'Open IDE' button may not function properly.

When students are ready and have opened the 'First IDE Lab', they should read
through the readme and follow the instructions for opening a lab, making changes
to a file, running tests and submitted the completed lab.

### In-Browser IDE

The In-Browser IDE includes Learn's built in text editor and terminal.  Using
the in-browser IDE, clicking Open in IDE will cause a text editor to appear on
the page, shrinking the text content of the lesson.

For more information check out this [Help Center Article](http://help.learn.co/the-learn-ide/ide-in-browser).

Some useful features that come with the in-browser IDE:

* Autosaving - no need to remember to save your work
* Integration with GitHub - if a student has already worked on a lab, they will be
able to go back to their previous work automatically
* Built in terminal features - Some commands like `httpserver`, useful for opening
HTML files, are already built in and can be run at any time in the terminal

Things to be aware of:

* In the in-browser IDE, you won't be able to right click files and open them on
separately the computer.
* Made for use on learn.co delivered lessons, may not be ideal for student
projects that are not already a GitHub repository linked to Learn.co.

Students can choose to make the in-browser IDE full screen for easier use, and
can also close the IDE while reading a lesson.

### Desktop IDE

The IDE Download is a downloadable integrated development environment. To open a
lab in the IDE Download, make sure you have downloaded the software, logged in,
and have toggled your environment to IDE Download. For more information on
setting up the desktop IDE check out this [Help Center
article](http://help.learn.co/the-learn-ide/how-to-download-and-use-learn-ide-3).

The workflow for passing labs and working through lessons is very similar for
both the in-browser and desktop IDEs, but some steps will change, such as saving
files.

Useful features of the desktop IDE:

* Can be used for building personal projects separate from learn.co lessons
* Has right-click menu functionality

Things to be aware of:

* Students using the desktop IDE will need to manually save files.
* Students using the desktop IDE will be modifying files on their computer when
working on lessons, while in-browser IDE students will be working on the cloud.  

## Running Tests

The lesson related buttons on the right side of Learn.co will change depending
on the type of lesson. If students see a 'Run Local Tests' box, this means that
they must use their terminal to run tests on the lesson. This indicator will
change color once a student runs a local test, but will not turn green until the
student has passed all the tests in the lesson.

Students can run tests as much as they like, and should be encouraged to test
often.  To run tests, type `learn` in the terminal.

In this first lab, all students need to do to pass the test is make an edit to
`edit-me.txt`, save the file and then run `learn`.

A student will know they've passed all the tests by looking at the output
messages on the terminal output as well as the learn.co lesson side bar.

### Tests Gotchas

These are some important _gotchas_ that students should be aware of as they work
through lessons on learn.co:

- Syntax Errors: one common obstacle for students when getting into code is that
typos in one place can cause unexpected errors in others.  Students should make
sure to check spelling and syntax when testing.  It may be that their solution
is right, but the a rogue typing mistake is causing the tests to fail.
- Infinite Loops: when we get into more complex labs, it is possible for tests to
get stuck in loops. The terminal may look like it has stopped responding if it
is in a loop, but it is actually just executing the code over and over forever.
To get out of a loop, try pressing `ctrl + c` a couple of times.  If that
doesn't work, it may be necessary to close the IDE and opening it again.
- User Input: tests are often particular about what they want in order to pass.
For instance, it may be the case that a test is looking for the word "true", all
lowercase, but _not_ "True".  To us humans, we see the two words and know they
are the same, but to a computer, these are two different answers.
- Reading Tests: failing tests can be frustrating, but it is part of the process
of learning how to code. Students should make sure to read the failure messages
that are produced, as they will often have hints and information about what went
wrong. Test failures that result in long lists of files erroring (a 'stack
trace') are usually an indication that there is a syntax error causing the test
to crash.

## Submitting a Lab

Once a student has passed the tests for a lab, they must submit their work in
order for learn.co to register that they've completed the lesson.

To do this, students should run `learn submit` in their terminal. If a lab is
submitted correctly, the 'Submit Pull Request' box on the lesson side bar will
turn green and students will be able to continue to the next lab.

## The Sandbox IDE

Another feature of the in-browser IDE is the _Sandbox_.  If a lesson is not a
lab or code along, students will have access to an empty version of the IDE. In
here, they can create files and folders, practice writing code and use the built
in terminal.  Think of it as a scratch pad to test code and follow along.

*Important:* Any work done within the Sandbox will not be preserved.  If a student refreshes
the lesson page or navigates away from it, any files and code will be erased. It
is possible to use the terminal and GitHub to save work done in the Sandbox to a
repository, but students should mainly be using Sandbox to practice.  All work
done on labs and code alongs in Learn.co _will_ be preserved in each student's
fork of the lesson repository.

## Hints

* Students should only need to edit the one file `edit-me.txt`, and can type
anything they want in order to pass the test.
* If, at any time, a student deletes or breaks a necessary file, it is always
possible to revert their work back to the last git commit by typing `git reset
--hard` in their terminal.  Any coding progress will be erased, so copy out any
work the student did and paste it in a notepad before resetting.  Typically, on
these labs, students will not be committing work, so reseting should bring the
lab back to its original state.

## Support

[IDE In Browser](http://help.learn.co/the-learn-ide/ide-in-browser)
[How to Download and Use Learn IDE 3](http://help.learn.co/the-learn-ide/how-to-download-and-use-learn-ide-3)
[Changing Your Learn IDE Environment](http://help.learn.co/the-learn-ide/changing-your-learning-environment)
[All Learn IDE Resources](http://help.learn.co/the-learn-ide)
