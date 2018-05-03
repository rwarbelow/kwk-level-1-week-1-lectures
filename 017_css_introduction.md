# Intro to CSS

## Objectives

Students will learn how CSS makes HTML _look fantastic_ and will practice writing basic CSS so they can apply their own custom styling to HTML.

## SWBATS

+ CSS - Write simple sets of style rules to change the look of HTML
+ CSS - Be able to link CSS in multiple ways

## Introduction to CSS, A.K.A Cascading Style Sheets

Back in the early days of the internet, web pages were built out of _only_ HTML.  It worked fine - we could use `<h1>` tags for header sections, `<p>` tags to hold our text content, `<img>` tags to display images, etc... and with a lot of trial and error, could get to a functioning website.  However, it was all _very plain_. Text styling was limited to things like **bold** and _italic_.. not very exciting, but it's all we had! On the modern internet, HTML is still necessary, but it is mostly used
for setting up the structure of a web page. In order to make modern web pages look as good as they do, CSS was introduced to work side by side with HTML.  CSS has the ability to totally change the design, and therefore the experience, a user has when visiting a website.

[Here is an example of some plain old HTML and what just a little bit of CSS can do!](https://ironboard-learn.s3.amazonaws.com/klossy_basic_html_example.html)

CSS, or Cascading Style Sheets, is its own language that defines how HTML is displayed on a page. It has its own rules for syntax that we will learn, but once you know the basics, you'll have the ability to style HTML in limitless ways. Before we start practicing, CSS has a few basic rules that we should discuss:

* CSS can interact with HTML in **three** ways:
  1. CSS rules can be written directly inside HTML tags.  So, for example, we can make the text in the following `<p>` tag blue by writing the following:

  ```html
    <p style="color: blue;">This text will show up blue.</p>
  ```
  2. CSS rules can also be written separately, but on the same page as HTML.  Using a `<style>` tag inside the `<head>` of an HTML page, we can write something like:

  ```html
    <head>
      <style>
        p {
          color: blue;
        }
      </style>
    </head>
  ```

  The above example will turn all text inside _all_ `<p>` tags blue.
  * CSS rules can be written in a separate `.css` file, _linked_ to an HTML page. This is the most common way websites utilize CSS. One benefit of this is that people can write one CSS file, and link multiple HTML pages to that one file. This keeps you from writing the same thing over and over, but also keeps your HTML pages a bit cleaner and easier to read.  We will be mainly focused on this method of writing CSS rules.
* The first word in CSS, _Cascading_, means that when a rule in CSS is read by your browser, it overrides any previous settings for that particular CSS rule. HTML reads from the top down, so if you've defined the color of text in a `<p>` tag as blue, but then a few lines down, defined the color of text in a `<p>` tag to red, text will appear red, not blue.

One thing that is important to note: There are _thousands_ of CSS properties.  We won't be concerned with most of them, and we don't have enough time go too deep into CSS practices, but that is okay.  As we mentioned before, _as long as_ you have an understanding the syntax for writing CSS rules and understand how to link CSS to HTML, you have all the skills you need to make HTML _look great_.

## Getting Started with CSS

Learning CSS is definitely a hands-on process, so the codealong linked below
should be used by each student as we go through some of the CSS basics.

[The Ultimate CSS Walkthrough](https://github.com/learn-co-curriculum/kwk-l1-css-walkthrough-code-along)

*Note:* The teacher should also clone the above repository so students can follow along
as a group. The text on `index.html` can be read aloud and provides a good guide
to teach with.  Additional challenges are listed as well as suggestions.

## Building Our Own Websites

HTML and CSS are all you need to build a great looking website.  Building a website
is also a great way to get better at HTML and CSS!  This site can be about anything, and should
use all of the concepts we've learned today.  Use a variety of HTML tags and CSS classes to create different sections on the page.

[Building My Own HTML Website](https://github.com/learn-co-curriculum/kwk-l1-my-own-html-website)

During this project, you can use any HTML elements

*Note:* students should first plan out their site, spend some time thinking about what should be on the site, what HTML elements they'll need and in what order.  Students may forget to link to the separate CSS file in their HTML.

CSS Examples for getting off the ground:
```css
.navigation {
  /* creates bar across screen if class is assigned to HTML */
  width: 100%;
  height: 50px;
  background-color: lightblue;
}

h1 {
  /* centered, very large header */
  text-align: center;
  font-size: 400%;
}

body {
  /* sets background image. Can also play animated gifs */
  background: url(an_image_OR_animated_gif_from_the_internet);
  background-size: contain;
}
```

### References:

* [CSS Full Reference Sheet](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/d7fb67af-5180-463d-b58a-bfd4a220d5d0/css3-cheat-sheet.pdf)
* [CSS Reference](https://www.w3schools.com/cssref/default.asp)

### Additional CSS Labs:

* [CSS Selectors](https://github.com/learn-co-curriculum/upperline-hs-intro-software-engineering-css-selectors)
* [Empire State Mock Site](https://github.com/learn-co-curriculum/upperline-hs-empire-state-css-challenge)
* [Zetsy](https://github.com/learn-co-curriculum/kwk-l1-zetsy)
