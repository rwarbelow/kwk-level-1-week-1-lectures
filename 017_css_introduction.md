# Intro to CSS

## Objectives

Students will learn how CSS makes basic HTML look fantastic and will practice writing basic CSS so they can apply custom styling to their own HTML.

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
  2. CSS rules can also be written separately, but on the same page as HTML.  Using a `<style>` tag inside the `<header>` of an HTML page, we can write something like:
  
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
  
  3. Finally, CSS rules can be written in a separate `.css` file, _linked_ to an HTML page. One benefit of this is that you can link multiple HTML pages to the same CSS file without writing CSS in each HTML page. This keeps you from writing the same thing over and over, but also keeps your HTML pages a bit cleaner and easier to read.
* The first word in CSS, _Cascading_, means that when a rule in CSS is read by your browser, it overrides any previous settings for that particular CSS rule. HTML reads from the top down, so if you've defined the color of text in a `<p>` tag as blue, but then a few lines down, defined the color of text in a `<p>` tag to red, text will appear red, not blue.
  
One thing that is important to note: there are _thousands_ of CSS properties.  We won't be concerned with most of them, and we don't have enough time go too deep into CSS practices, but that is okay.  As we mentioned before, _as long as_ you have an understanding of the syntax for writing CSS rules and understand how to link CSS to HTML, you have all the skills you need to make HTML _look great_.

## Getting Started with CSS
