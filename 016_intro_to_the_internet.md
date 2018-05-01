# Introduction to the Internet

## Objectives

This lesson will take a step back from more technical descriptions/coding skills and focus more on demystifying 'how the internet works'. Specifically, this lesson addresses the server/client distinction as well as HTML requests/responses.

## SWBATS

+ INTERNET - provide a high level description of what a server does 
+ INTERNET - provide a high level description of what a client is
+ INTERNET - describe the request/response nature of client/server communication
+ INTERNET - identify the purposes of response status codes

## Introduction

How many times a day do you use the internet? How many times do you load a different web page? Think about how many times you do this in a year! 

In order to be a web developer it's incredibly important to understand how the web works. From here on out, you are no longer just a user of the internet. You are a creator of the web.

Let's start with the basics: how does a URL turn transform into web content we interact with in the browser? For example, how does this:

```
https://www.youtube.com/user/AdeleVEVO
```

Turn into this:

![](https://s3.amazonaws.com/learn-verified/request-intro.png)

## What is a Server

To understand how providing our browser a url fetches us website data we need to demystify what a 'server' is. The word itself is used to identify a wide variety of technologies, so let's use a broad definition to make it clear what it does:

A **server** does exactly what it's name implies: it _serves_ content, files, and data! A server is a computer, sometimes with specialized hardware and sometimes just a laptop like your own.

A computer/server waits patiently, listening for incoming requests from computers elsewhere. When it receives a request, it does its best to return the relevant information/files/assets (think images, movie data, HTML files, etc.). 

When we type something like the YouTube url above into the browser and hit enter, one of these requests goes whizzing across many layers of the internet and finds its way to the Google YouTube servers. 

Let's pick apart the example request. We will see that it is very simple when you know what to distinguish: 

`https://www.youtube.com/user/AdeleVEVO`

- `https`: "I'm written in the HTTP language! Now anyone who gets me will know how to understand and respond to me."
- `www.youtube.com`: "Hey internet routers, I am looking for YouTube's servers. Can you make sure I get delivered there?"
- `/user`: "Now that I'm at the YouTube server, I want to communicate that I am specifically looking for information on a YouTube user."
- `/AdeleVEVO`: "Even more specifically, I am looking for information on this user."

...and BOOM! The YouTube servers received the request and knew exactly what to respond with: their files and information on the user AdeleVEVO. Along with that information, the servers also sent back the HTML/CSS/JavaScript that told the requestor (in this case, the Browser), how to display the information. 

## What is a Client

## HTTP

#### HTTP-Requests

#### HTTP-Responses

###### Status Codes
