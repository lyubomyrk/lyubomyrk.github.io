---
layout: post
title: "TIL: Roadmap to ASP.NET"
categories: til
tags: til aps.net c#
---

The .NET framework is confusing as any other framework for beginners. But
because of Microsoft creating multiple project types I believe that ASP.NET
is more confusing than it has to be. This blog is about me understanding where
each project type fits and what it takes to learn ASP.NET (or what are the 
important bits).

# Every project is different

I come from a Python background in web development. Beyond choosing a framework
like Django or Flank or FastAPI, everything afterwards is straightforward.
If you want you can have server-side rendering with Jinja2, the same for all
the frameworks, or client-side rendering with any Javascript framework. It's
easy to wrap your head around once you built a few web apps.

But ASP.NET is a little different. You can do everything with C# for both
client and server side rendering. Or you can choose to use C# for the backend
and have client side rendering. What's confusing is the different project
types. Again, in Python you only choose the framework. What I mean is that the
project type is the same, the framework itself, and you are free to make
whatever decision you want. However, in ASP.NET, the project type determines
the decisions for your web app.

There are 5 project types, let me break it down for you.

# The 5 ASP.NET projects

First I want to explain that ASP.NET == ASP.NET Core. The core at the end is
simply the "latest" version and an artifact of a bygone era. During transion
from .NET Framework to .NET Core is why ASP.NET has Core attached, that simply
states it is open source and cross platform. I will refer to ASP.NET Core as
ASP.NET from now on.

Why are there __FIVE__ projects types? It's not because Microsoft is trying
to stay backwards compatible with Windows XP. The reason is because _every_
project is different, and it makes sense to use the right tool for the job.

Also, keep in mind that ASP.NET allows you to add on to existing project. If
you pick one you are not tied to it, you can add Blazor to a MVC project
if you want.

## ASP.NET Web API

This is self-explanetory. The main purpose behind this project is for 
app-to-app communication, not person-to-app communication. Usually, a web 
application will consume your ASP.NET Web API project.

## ASP.NET Razor Pages

This project type is used for user forms that are __static__. They are quick
with low overhead, but have no moving parts. This is your simple web app like
a comment section or a blog. These are server-side HTML pages. 

## ASP.NET MVC

This is legacy, don't let that scare you, it's just the old kid on the block.
It's client side C# and does everything you need. It allows you to use a GUI
to interact with your website design.

## ASP.NET Blazor Server

This is both server and client side C#. This allows you to have the benefit
of quick downloads and interactivity. Downside it it requires always on
connection, because it achieves client side C# through communication with
server side. What I mean is that when some client side C# is used to update a
record on page, it sends the bytes that change to the server, which renders
only those bytes that change. It's a hybrid, and that requires an always on
connection. This is a good starting point, and when you need more you can 
combine it with other project types.

## ASP.NET Blazor WebAssembly

This is client side only C#. Behaves just like any Javascript framework. It is
downloaded to the browser and the client renders everything. Useful when you
want offline capability and browser persistance. Very powerful when combined
with Blazor Server.

# The power of mix and match

Picking a project doesn't tie you down. You can start with a Razor page, then
realize you want interactivity of Blazor Server, and later add Blazor
WebAssembly because you want you web app to work offline. That is possible.
Altought unless you know your web app will be a simple form, I'd recommend just
starting out directly with Blazor Server.

You _can_ replace this with just using MVC, and I'm personally planning to
learn it before Blazor Server, but it's legacy and while battery-included won't
be moving forward.

# So how do I learn ASP.NET?

First, realize that ASP.NET is just the engine that powers the different
project types I described above. Now, start simple.

## Step 1: Learn Web APIs

I don't want to worry about also learning to create a UI experience. That's why
I start simple and make my web app an API. A movie database or a bookshop that
is only accessible through Postman is okay. Remember what I said about the
power of mix-and-match?

## Step 2: Add Razor forms

Now make that movie database/bookshop into a static web page where you can
interact through forms. Maybe recreate an online marketplace like Craiglist
(the look and feel I mean) with ability to post items, manage items, and email
user's. Maybe have two different project types instead of all in one, hook up
your Web API to a new Razor forms project and learn how to maintain both.

## Step 3: Learn the basics of MVC

Techinically not necessary, but there is a LOT of knowledge on ASP.NET
dedicated to MVC. And a lot of lessons carry over to Blazor. Start fresh and
create an app to maybe stream video or a constantly updating feed. Make an
interactive app.

## Step 4: Add Blazor into your MVC app

Get practice with extending legacy apps! This is where ASP.NET shines with,
again, the ability to mix and match. Add a feature, a comment section on your
video streaming site or feed? But use Blazor.




