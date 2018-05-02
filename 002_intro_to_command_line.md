# Intro to Command Line

## Objective

***Students will be able to navigate their system's file structure using the command line in terminal.***

## SWABTS

+ CLI ‐ Understand and explain what terminal is and why we use it
+ CLI ‐ Navigate through directories using relative and absolute paths
+ CLI ‐ Use the `cd` command to move up and down directories
+ CLI ‐ Use the `ls` keyword to list items in a directory
+ CLI ‐ Remove a file and a directory by using `rm` and `rm ‐rf` keywords
+ CLI ‐ Move files and directories using the `mv` command

## Motivation

Back in the day ('80s) computers only had a terminal to control them. (Show a picture). No mouse, no icons, no desktop. Just a blinking green cursor. You had to control your entire computer like that.

Later on, Graphical User Interfaces (GUIs) were created to make computers more accessible.

Developers continue to use the terminal instead of the GUI because it makes you faster, more in control, and you understand what's happening under the hood. If you're a developer, time is money (and your time is expensive).

Understanding the terminal is like being Neo from the matrix- you can see the secret hidden files on your computer. This is industry practice.

## Lesson Plan 

### Opening Your Sandbox

Learn gives all students a Sandbox Developer Environment so that they can play with code and experiment outside of the context of a lab. You can open the Sandbox by clicking the Sandbox button, located under the Account menu on the top right or on READMEs.

![Sandbox Sample](https://cl.ly/r3jq/Image%202018-04-21%20at%205.52.31%20PM.png)

Have the students all open their Sandbox.

Identify the parts of the IDE, the File Tree, which lists Folders and Files, the Text Editor, where they right code, and the Terminal, where they execute Command Line instructions. Have them focus on the terminal by clicking on it.

![IDE](https://cl.ly/r3tL/Image%202018-04-21%20at%205.55.12%20PM.png)

### `pwd`

We're going to learn about the command line by planning for a trip. In IDE Sandbox, your terminal is located at the bottom of the screen. In your terminal, type `pwd`. (stop and have all students do this) `pwd` stands for print working directory. It will tell you where you are currently "standing" in terms of directories. A directory is just a fancy shmancy word for a folder.

A directory can contain one of two things - files or other directories. The directories on your computer are nested inside of each other, like a Russian doll or a tree structure. (draw the tree structure out as you build it)

### `ls`

Let's check what directories are within the directory where you are standing by using `ls`, which stands for list (have students do this).

### `mkdir`

Create a new directory called "development", using `mkdir`. This stands for make directory. (have students do this) `mkdir development`

### `cd`

Change directories using `cd` command. `cd` into development. (stop and have all students do this) `cd development`

To get some practice, we're going to make a new directory on for a trip. make a new directory called `trip` by using `mkdir trip`. Check and see that the directory was made by using ls. (stop and have all students do this)

Create directories for countries within the trip directory

```
mkdir egypt
cd egypt
```

Create directories for cities within the countries (stop and have all students create countries and cities)

```
mkdir cairo
cd cairo
```

### `touch`

Create text files for places you want to visit in the cities directories by using touch:

```
touch pyramids.txt
```

### Edit a File

Open the file using the file browser on the left navigation bar. (pause and have students create files with text.)

### `rm`

Remove a file that you no longer want using rm (I don't want to see eiffel_tower.txt anymore) `rm eiffel_tower.txt`

Remove an entire directory using `rm -rf` (remove paris directory) `rm -rf paris`

### `mv`

Accidentally place a file in the wrong directory so we need to move it. (`washington_monument.txt` in `new_york` directory needs to be moved to `washington`)

```
mkdir new_york
cd new_york
touch washington_monument.txt
cd ..
mkdir washington_dc
mv new_york/washington_monument.txt washington_dc/washinton_monument.txt
```

`cd ..` moves us up a directory.

`mv` takes two arguments, the first is what you want to move, the second is where you want to move it to.

`mv` is also used to rename files.

```
touch statue_of_library.txt
mv statue_of_library.txt statue_of_liberty.txt
```

Practice moving up the tree using .. (`cd ..` moves up a level into the parent directory)

### Absolute vs Relative Paths

Directories only know what's directly inside of them. If I'm in Paris, the only things I know are the sights in Paris, I don't know that I'm in France, and I don't know that Rome even exists. You need to move up the tree with `cd ..` to access items outside of the directory you're in. 

Write out the absolute path of different files and directories. An Absolute path is a path that starts from the root, `/`. An absolute path to the pyramids file would be: `/home/aviflombaum/development/trip/egypt/pyramids.txt`.

Write out the relative path to the cities from the trip directory. A relative path changes based on what directory you're in. If you're inside your `development` directory, and you're trying to get to your `pyramids.txt` file, the relative path would be `trip/egypt/pyramids.txt`.

It helps to draw out the file structure tree on the board, and use that as a visual to draw out the path.

## Conclusion 

The Command Line is an incredibly valuable tool that lets you manipulate configuration files of your computer. It also lets you navigate your computer much faster than using the Finder. We will also use the command line to run our code, so familiarity with it is very important.

## Hints and Hurdles

+ The [Pets Organizer]<!-- (https://github.com/learn-co-curriculum/kwk-l1-find-missing-pet) --> lab really hammers home paths. This is an important concept for students as they begin to create HTML/CSS projects and then their sinatra apps at the end of the course. Paths are a complicated concept- let students know its ok if it doesn't make sense right away.

+ Bonus Labs are the [Terminus Game](https://github.com/learn-co-curriculum/kwk-l1-cli-stayfresh) and the [Command Line Challenge]<!-- (https://github.com/learn-co-curriculum/kwk-l1-advanced-cli) -->

+ Helps to have students write out the instructions if they were moving one step at a time `cd code`, `cd labs` and then show them how they can shorten that `cd code/labs`.
