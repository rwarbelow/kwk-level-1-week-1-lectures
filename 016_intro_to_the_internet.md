# How The Web Works

This lesson will take a step back from more technical descriptions/coding skills and focus more on demystifying 'how the internet works'. Specifically, this lesson addresses the server/client distinction as well as HTML requests/responses.

## SWBATS

+ INTERNET - provide a high-level description of what a server does 
+ INTERNET - provide a high-level description of what a client is
+ HTTP - describe the request/response nature of client/server communication
+ HTTP - identify the purposes of response status codes

## Introduction

How many times a day do you use the internet? How many times do you load a different web page? Think about how many times you do this in a year! 

In order to be a web developer it's incredibly important to understand how the web works. From here on out, you are no longer just a user of the internet. You are a creator of the web.

Let's start with the basics: how does a URL transform into web content that we interact with in the browser? For example, how does this:

```
https://www.youtube.com/user/AdeleVEVO
```

Turn into this:

![](https://s3.amazonaws.com/learn-verified/request-intro.png)

## What is a Server

To understand how providing our browser a URL fetches website data we need to demystify what a 'server' is. The word itself is used to identify a wide variety of technologies, so let's use a broad, catch-all definition:

A **server** does exactly what its name implies: it _serves_ content, files, and data! A server is a computer, sometimes with specialized hardware and sometimes just a laptop like your own.

A computer/server waits patiently, listening for incoming requests from computers elsewhere. When it receives a request, it does its best to return the relevant information/files/assets (think images, movie data, HTML files, etc.). When we type something like the YouTube URL above into the browser and hit enter, a request goes whizzing across many layers of the internet and finds its way to the YouTube servers. 

Let's pick apart the above URL and see how it is used to construct a request. We will see that it is straightforward when you identify its separate components: 

`https://www.youtube.com/user/AdeleVEVO`

- `https`: "I'm written in the HTTP language! Now anyone who gets me will know how to understand and respond to me."
- `www.youtube.com`: "Hey internet routers, I am looking for YouTube's servers. Can you make sure I get delivered there?"
- `/user`: "Now that I'm at the YouTube server, I want to communicate that I am specifically looking for information on a YouTube user."
- `/AdeleVEVO`: "Even more specifically, I am looking for information on this user."

...and BOOM! The YouTube server receives the request and knows exactly what to respond with: files and information on the user AdeleVEVO. Along with that information, the server also sends back the HTML/CSS/JavaScript that tells the requestor (in this case, the Browser), how to display the information. We refer to this requestor/browser as the **client**.

## What is a Client

As was the case with defining what a server is, a **client** can also refer to a wide variety of use cases. In short, a **client** is a computer/program that _accesses_ information on a server. Whenever you go to a website in your browser, you are interfacing with the website via a **client**. 

For example, when we go to the iconic Amazon.com, the first thing Amazon's servers do is send back a whole bunch of files that our browser starts displaying. In this case, the **client** is the combination of the Browser, the bundle of HTML/CSS/JavaScript from Amazon.com, and everything we interact with as users.

#### Clients in the Middle

Consider this: a **client** also acts as a helpful middle layer between us and a server. If we were to go to Amazon.com, it is pretty clear that we don't receive all of the information Amazon servers have to our computers all at once. It wouldn't be practical to send the price, items remaining count, comments, etc. on every single product they offer to every single computer that visits their website (that would be a madhouse!). Instead, we are able to navigate to different areas of the website which load with new information. 

This is because the client is bridging the gap between us and the server. When we click on a new section of Amazon, the client:
- interprets the click
- generates an HTTP requests for its Amazon.com servers
- sends the request off, from our computer, over the internet, to Amazon.com
- waits for the response from the server
- receives and handles the response
- decides where to fill in what information it received, and everything about how this information should be presented to the user (you!)

That is a lot of work that the client is abstracting from us, the users. All we need to do is click on a category, (i.e. "Clothing", "Books", "Movies", etc.) and the client manages everything in between. 

**Query the students:** be prepared to answer those questions yourself, and guide the student discussion:
  - "So what is a client in your words? Are Chrome/IE/Firefox/Safari clients themselves?"
  - "Often times, developers will talk in terms of 'front-end' and 'back-end' of a website. Which term is referring to a client? Which is referring to a server? Do those names make sense?" 

## HTTP

We glossed over **HTTP** earlier when we were talking about servers handling requests. Let's circle back and do a high-level overview of what **HTTP** is and why it's useful. 

Just like any spoken language, Hyper Text Transfer Protocol, or **HTTP**, was created to help different entities communicate. In the case of web programming, the vast majority of request-response communication that we experience is happening using grammar, rules, and expectations that **HTTP** defines. 

When we go to youtube.com, our browser sends an HTTP request off to YouTube's servers. When we receive a response, it is in an HTTP format that our browser knows how to interpret and display to us.

That's it! Sure, the details, explanations, and history get more complicated than that, but the general idea is simple: **HTTP** is a language protocol, extensively used by the internet, to help computers communicate and to help programmers stick to a defined pattern.

In diving deeper into HTTP communication, we can identify two clear distinctions: HTTP requests and HTTP responses. Let's examine both in turn.

#### HTTP-Requests

In general, there are two core flavors of HTTP requests: `GET` and `POST`. 

`GET` requests are used to ask for a specific resource:
  - "Hey google.com, please `GET` me all the images associated with 'cat walks like human'"
  - "Hey weather.com, please `GET` me the temperature/humidity for today."

`POST` requests are used to submit data to a server, for it to then make use of:
  - "Hey google.com, I want to update my profile picture. Here is an image I'm sending with my `POST` request for you to save in your database."
  - "Hey blog website, here is the text that should go in my new blog post. Please check the body of this `POST` request and save it in your database so users on other computers can get it from you!"
  - "Hey Facebook, update my status with this text instead of whatever you had before."
  
`GET` and `POST` are often referred to as **HTTP verbs**, because their names describe the action they should invoke wherever they are received. 

In addition to `GET` and `POST` requests, there are additional types of HTTP requests, or **HTTP verbs**, with most of them describing more specific kinds of `POST` actions. For now, keep in mind:
  - `GET` is for retrieving something the server owns, without changing data the server owns
  - `POST` is for communicating that some data on the server should be changed, be it creation, alteration, deletion, etc.

#### HTTP-Responses

Whenever we make an HTTP-Request, it comes back with an equivalent HTTP-Response. Both `GET` and `POST` requests can be responded to with information. For example: "`GET` me this image" has a response that contains the image file. "`POST` this new information to my profile" may come back with the updated profile information. 

While it all happens very quickly, our computers wait for their HTTP requests to be fulfilled. After we send a request off from a browser, for example, it waits for the response and then updates what we see once it arrives.

###### Status Codes

Status codes are an integral part of HTTP-Responses. They are attached to the Response data and describe, in a general sense, what happened with the request we sent. They can signal anything from: "Hey! The request was successful!" to "Oh my, I think your request blew up the server."

You are likely familiar with two common status codes already: 200 and 404. A response of 200 signifies that the request was successful, and that the response is sound. 404 signifies that the server did not have whatever we were requesting. 

**NOTE:** Show the students now in the browser an example of a 404 response. Try some common URL, (such as `google.com`, but even better if you ask the students to provide one), and then affix some nonsense route to it, (such as `google.com/memes`). We not only get a response with a status of 404 back, but Google is kind enough to send back a custom page for whenever a request is doomed to have a 404 response.

**NOTE:** Ask the students to use google to determine the 5 general types of status codes. Drive home that they are grouped in the hundreds, and that while it's not worthwhile to memorize what each individual status code means right now, it is worthwhile to familiarize yourself with the 5 groups. 
