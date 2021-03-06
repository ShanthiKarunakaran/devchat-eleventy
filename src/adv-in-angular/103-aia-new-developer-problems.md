---
layout: layouts/post.njk
title: >
      103 AiA New Developer Problems
date: 2016-07-28 07:00:41
episode_number: 103
duration: 01:00:37
audio_url: https://media.devchat.tv/adventures-in-angular/AiA103NewAngularProbs.mp3
podcast: adv-in-angular
tags: 
  - adv_in_angular
  - podcast
  - new_programmers
---

## [Angular Remote Conf](https://allremoteconfs.com/angular-2016)
&nbsp; **This show is based off the following listener email:** “I know you've discussed a couple of times about how hard it is to set up an Angular 2 project. Whilst most of this has nothing to do with Angular itself, it's still the barrier to entry. There's no point in saying how much easier Angular 2 is than Angular 1 if you can't get it running. Even though I'd heard your previous discussions on this, in reality I was totally unprepared as to how difficult it was when I had to do it myself recently. Even the Angular 2 5 minute quick start took me a day to get my head around!I was delighted to hear the Angular team was coming up with Angular CLI. Get the mechanics out the way and lower the barrier to entry. So I typed 'ng new myapp'. Oh! Looking at the properties of the directory I saw Size: 161MB, Contains: 40,531 files, 7,226 folders.Has the JavaScript world gone completely mad? Is this really acceptable? 40,000+ files before I write my first line of code? OK, so Angular CLI has created all this stuff for me but I still have to understand what it's about, or how will I maintain it and keep it up-to-date. What happens if there's an incompatibility in one of the libraries used?It would be great to hear the members of the podcast discuss what they think needs to happen in order to simplify this. Is Angular CLI actually simplifying things, or is it just shifting the 'getting starting' problem to become a maintenance problem? Is it even possible to have a simple Angular 2 project, do we need to just accept that 161MB of disk space is a minimum? Has Angular 2 become out of reach for hobbyists, or is it the exclusive property of experts and full time client-side developers only?”04:35 - Purpose and Value15:32 - [“Dumpster Fire”](http://www.urbandictionary.com/define.php?term=Dumpster%20Fire)19:01 - Capability and Complexity26:03 - Getting Setup to Develop in Angular; Investing in Skills
- [Angular 2 5 Min Quickstart](https://angular.io/docs/ts/latest/quickstart.html)
- [Tour of Heroes Tutorial](https://angular.io/docs/ts/latest/tutorial/)
- “Has Angular 2 become out of reach for hobbyists, or is it the exclusive property of experts and full time client-side developers only?”
- [Lukas Reubbelke: Angular 2 with Handcrafted Tools, Century-Old Techniques and ES5](http://onehungrymind.com/build-angular-2-app-es5/)
&nbsp;Picks 
- [Chaos Monkeys: Obscene Fortune and Random Failure in Silicon Valley by Antonio Garcia Martinez](https://www.amazon.com/dp/B019MMUAAQ) (Ward)
- [Wink](http://www.wink.com/products/) (Lukas)
- [Badass: Making Users Awesome by Kathy Sierra](https://www.amazon.com/Badass-Making-Awesome-Kathy-Sierra/dp/1491919019) (Lukas)
- Learning (Joe)
- [George W. Bush in Dallas: “Too often we judge other groups by their worst examples, while judging ourselves by our best intentions.”](http://www.vox.com/2016/7/12/12164176/george-bush-dallas-shooting-speech-video) (Joe)
- [VidAngel](https://www.vidangel.com/) (Joe)
- [Opposing protesters meet in Dallas](http://www.cnn.com/videos/us/2016/07/11/one-dallas-protesters-come-together-nccorig.cnn/video/playlists/dallas-police-officer-shot/) (Chuck)
- [iPad Pro](http://www.apple.com/ipad-pro/) (Chuck)
- [Apple Pencil](http://www.apple.com/apple-pencil/) (Chuck)
- [GoodNotes](http://www.goodnotesapp.com/) (Chuck)
- [Adventures in Angular Facebook Page](https://www.facebook.com/adventuresinangular/) (Chuck)


### Transcript

 **LUKAS:** [Singing] Beautiful, immutable, what you do to my heart.

**_[This episode is sponsored by Hired.com. Every week on Hired, they run an auction where over a thousand tech companies in San Francisco, New York, and L.A. bid on JavaScript developers, providing them with salary and equity upfront. The average JavaScript developer gets an average of 5 to 15 introductory offers and an average salary offer of $130,000 a year. Users can either accept an offer and go right into interviewing with the company or deny them without any continuing obligations. It’s totally free for users, and when you’re hired, they also give you a $1,000 bonus as a thank you for using them. But if you use the JavaScript Jabber link, you’ll get a $2,000 bonus instead. Finally, if you’re not looking for a job but know someone who is, you can refer them to Hired and get a $1,337 bonus if they accept a job. Go sign up at Hired.com/AdventuresInAngular.]_**

**_[Ready to master Angular? Oasis Digital offers Angular Boot Camp, a three-day, in-person workshop class for individuals or teams. Bring us to your site or send developers to ours classes in St. Louis or San Francisco – AngularBootCamp.com.]_**

**_[This episode is sponsored by Telerik, the makers of Kendo UI. Kendo UI integrates seamlessly with both AngularJS 1.x and 2.0. It provides everything you need to integrate with AngularJS out-of-the-box bindings, component configuration, directives, template directives, form validation, event handlers and much more and yet Kendo UI tooling does not depend on AngularJS. So, if you want to use it with Angular or not that’s totally up to you. You can check it out at KendoUI.com]_**

**CHUCK:&nbsp;** Hey, everybody and welcome to Episode 103 of the Adventures in Angular show. This week on a panel we have Joe Eames.

**JOE:&nbsp;** Yo! Yo! Yo, everybody!

**CHUCK:&nbsp;** Lukas Reubbelke.

**LUKAS:&nbsp;** [Inaudible]

**CHUCK:&nbsp;** Ward Bell.

**WARD:&nbsp;** I hope you all feeling it today because I am ready for Freddie.

**CHUCK:&nbsp;** I'm Charles Max Wood from DevChat.tv. Angular Remote Conf is coming up in September so go check it out. This week we are going to go over a topic that was submitted through our topic suggestions form. If you go to AdventuresInAngular.com, and you click on the suggested topic, you can put your own in here. But I wanted to get reactions from the panel and just discuss this because I think it's interesting and Luke has reacted to it over email so I know that we've got something here.

But anyway, let me just start reading this. It's about five paragraphs and it says, "I know you've discussed a couple of times about how hard it is to set up Angular 2 Project. Whilst most of this has nothing to do with Angular itself, it's still the barrier to entry. There's no point in saying, how much easier Angular 2 is as Angular 1 if you can't get it running. Even though, I've heard your previous discussions on this, in reality I was totally unprepared as to how difficult it was when I had to do it myself recently. Even the Angular 2 five-minute quick start took me a day to get my head around."

Then he says, "I'm delighted to hear that Angular team was coming up with Angular CLI, yet, the mechanics out of the way and lower the barrier to entry. So I typed 'ng new myapp'. Oh! Looking at the properties of the directory, I saw the size was 161 megabytes, contains 40,531 files, 7,226 folders. Has the JavaScript world gone completely mad? Is this really acceptable? Forty thousand plus files before I write my first line of code? Okay --"

**WARD:&nbsp;** Where that 40,000 come from? All right. We're not going to answering this yet. Okay, good. Good.

**CHUCK:&nbsp;** Okay, so, yeah, "-- so Angular CLI has created all this stuff for me but I still have to understand what it's about, or how will I maintain it and keep it up to date. What happens if there's an incompatibility in one of the libraries used?" There's a little more here, but let's just start there.

**WARD:&nbsp;** Wow, so there's a lot of interesting bullet points in there, and truths and myth.

**CHUCK:&nbsp;** Here we go, okay so truth or myth.

**LUKAS:&nbsp;** Well, first and foremost, let me just start by saying that, if I say anything sarcastic, well, of course of this episode, I definitely want to --

**WARD:&nbsp;** Do you know what sarcasm is, Lukas?

**LUKAS:&nbsp;** No! But I just want to apologize, like beforehand is like, I think that this is coming from- I appreciate the email and I definitely have opinions about it. But, definitely, I want to be sensitive to developers who are in this kind of this situation, and not be flippant or cavalier about it. Because I definitely think there is a group of people, that kind of where we are now is very kind of new and alarming and frustrating, and I get that.

With that said, I think the first thing we have to attack is what is kind of the general point here or rather when he says he runs 'ng starter' or 'ng create', and there like 45,000 files, what where is that actually coming from? So the majority of that is like, let's say 45,950 of those are in the Node Modules --

**WARD:&nbsp;** That's what I'm thinking.

**LUKAS:&nbsp;** Yeah, as well as the majority of that is also in the Node Modules. So actually outside of that, there's very little, you know, that the CLI is doing that you actually would directly work with. So the next question really for me is, well, what do we get for 45,000 plus files, and I think, this is really kind of the crux of the discussion is, well, you know first and foremost, you get generators so now, just from a command line, you can generate or scaffold out your application. You get a test runner so Karma; and to a test runner, you get a server with library load; the ability to produce a production build to run let say, a linter on your code, and the ability to compile your type scripts; and deploy to GitHub for free.

So, in that senses, it's really, really easy. Now, basically for free to do all of these really important things that produce high quality apps that are going to behave reliably and kind of stand the test of time. So really the question, I think, for me when I read this, is what is the solution to this. Are they saying that they do not want a test runner that they don't want to run a linter against their code? Or have deployment options, etcetera. I think, that's really kind of the core of the matters in what scenario are test not important.

Is code quality not important? Being able to do production build is not important, etcetera. I think, that's where- you know, three to five years ago, these things were not really that important. I think, a lot of, you know, like JavaScript developers were not doing those kind of things for now, because a JavaScript is evolving like code quality, deployment builds, testing these different things. They have to be front and center if we're building well that for patients. So, my question is like when are these things not important when would you not want to have these test runners and the servers and these different options.

**CHUCK:&nbsp;** So, Lukas I got to respond to what you said, which is I hate everything you said.

[Laughter]

**LUKAS:&nbsp;** And I love you.

**CHUCK:&nbsp;** So you're obviously taking the position that you go completely defending this whole entire point, or you're taking the opposite approach, like this guy is up in the night, this is necessary, we need all this. We need those 40,000 files, and we need 161 megabytes. We are starting an Angular 2 project. We need it all. Look at all the features. Look at all the gloss we get. We've got wax undercoating on our car. You can't go drive up a lot without that. I've got the low profile tires. Which feature do I not want? That's what I hear you saying.

[Cross-talk]

[Laughter]

**LUKAS:&nbsp;** -- That's what I was saying, but it also I will put this out here just to be fair in a word like to say, I think, intellectually honest or intellectual integrity that I did go and write in Angular 2 application in ES5 without any of these bells and whistles and I hope that we actually get an opportunity to talk about that as well so --

**CHUCK:&nbsp;** I want to know how many times you have to take like some kind of antidepressant while doing that in order to keep yourself like alive.

**WARD:&nbsp;** That's going to be a great show but --

[Laughter]

**WARD:&nbsp;** -- I want to step back a little bit. Again, I'm trying to get what you did ahead of the person who's writing this because I think that person represents something that valuable - a perspective that's valuable to us.

So everything that Lukas said, I think is true. The problem is maybe that Lukas knows that those are the values that are there, that those are the things that are there. But if you reel your mind back to your first encounter with client side programming and if you knew almost nothing about it, you wouldn't know that what any of that stuff was that you had. You wouldn't know what purpose it served. It would just be 45,000 files that you had no idea what they were for.

As far as I know, the CLI doesn't actually have any documentation yet that would guide you to understanding what it is that you just got when you ran that command. You just sort of followed some instructions, and out this came. I remember that experience with a Yeoman generator once where I got some 70,000 files and I just said, "I got to walk away from this. This is madness."

It's only after you have some sense of what this CLI is trying to accomplish, and which part you have to pay attention to and which you don't that you begin to feel more relaxed about having all those files.

**JOE:&nbsp;** Well, you're talking about like the nitty gritties of how many files there are, and how big it is, right? But that's not really the point of this whole post, really. We're going into- I mean, I was even saying, "I'm taking this opposite approach. We don't need this. We don't need every little feature." I like every little feature. I want the wax undercoating, and I want leather seats. I want a low profile tires. I like my tests. I like my builds. I like all of that.

But I think, the real point of this post is something we've seen well repeated for the last year and a half, two years, which is front-end development is a dumpster fire. That's the point of the post.

[Cross-talk]

**CHUCK:&nbsp;** He’s saying that but really, where it comes from is he has absolutely no idea what to expect, and it's completely forgotten about the environment from which he came. Now --

[Cross-talk]

**JOE:&nbsp;** -- A lot of heat and a horrible smell, then he'd be happy?

**CHUCK:&nbsp;** Oh, no, no --

[Cross-talk]

**JOE:&nbsp;** -- That's what we have. We have a ton of heat. We have a horrible- It's a dumpster fire. We can't package up the dumpster fire, and say, "It's fine."

[Cross-talk]

**WARD:&nbsp;** One of Lukas's key point there is that in enormous percentage of the files that he's talking about are in Node Modules. Now, all of us know that to be true and all of us pay almost zero attention to the Node. We see Node\_Modules and we don't even open it. I mean, we look into it we need to, but for the most part, we say, "Okay, yeah, yeah, yeah," because what do we know that this person and most people don't know.

We know that most Node Modules will never show up in your application. We know that most of Node\_Modules you never have to look at. You're just going to, you know, something is going to reference something in there, but it's just there, and it's not going to hurt you and it's part of what we expect with client-side development.

Now, we can say well, why should we expect that. Last time I was in any of the other environments, let's take .Net for example, and I opened up. Do I go in there and look at the references? Do I see how many DLLs are in there? Do I see how deep they are and what they contain or do I know what they do? No, I don't.

But I've got used to the idea that I don't have to know because I know that references don't matter from my day to day activity. They're just there. I guess, my point is that until you're conditioned to know what's important and what's not, it all looks scary that we're not doing- adequately is preparing people for experience of client side development and until there are enough people who can hold each other's hands and get us through it, we're going to have this reaction.

**CHUCK:&nbsp;** So, one thing that I'm looking at here, because what I'm hearing is if it's in Node Modules, you can basically ignore it because that's kind of a side product of the process and everybody kind of gets that and so that's kind of the way it is. But my thing is like, "Okay, so how do I know which parts I need to care about," because ultimately what I want is I want a system that is relatively easy to use that will get my application up or somebody else can use it.

So if the Node Modules are all kind of incidental to that because I'm going to put some build process on this and then I'm going to magically know which files to actually copy up to the web, there's still some disconnect here. Even if you say, "Okay, well, don't worry about Node Modules and don't worry about some of these other things because those are just going to make it nice for you to be able to do it the way you should do it. It's okay." Well, then what parts do I care about and how do I make that get me what I want.

**WARD:&nbsp;** Absolutely, somehow, either that we're not telling that story, or what we are seeing, which I do see is people don't really pay attention in documentation. They just take the first couple lines, they see what comes out, they throw up their hands and walk away. You know, that's a reaction if you don't want to make any investment in client-side development or any kind of development. You can have that reaction. Or you can try and get a little guidance about what's going on.

I'm not going to, by the way, justify everything that's in the Node Modules. I mean, I have my critique with the CLI. But I stand by my position which is that not that you will ever look at what Node Module is, but that's not the first place to look.

**JOE:&nbsp;** Okay, but you’re picking one specific piece and this idea that you learned that Node Modules are something you can see if they ignore, that's a fallacy. That's not --

**WARD:&nbsp;** I said that's not in the first place you look. You just know it's going to be a grab bag of stuff that you're going to need, and most of which is, by the way, is stuff that something that you need is going to need. We are all usually only interested in the top-level libraries that are sitting in Node Modules, not all of the things that they're built on.

You know, at certain point, we all learn that Node Module is all these details, source code, and all that stuff that runs deep, deep, deep, deep, deep and we're barely ever touching anything but the surface of it.

**JOE:&nbsp;** Right. It's the part of the dumpster fire that is way in the back. It also happens to be well-stacked. But it's a part of the dumpster fire that is farthest away from what you're going to be dealing with.

**LUKAS:&nbsp;** When you say dumpster fire, just so we're clear, because in my inclination, I don't agree with you, but what do you mean when you say dumpster fire?

**JOE:&nbsp;** You know... Google 'dumpster fire'. A dumpster that's on fire. That's what it is. It's a hot mess. It's just an absolute, horrid --

[Cross-talk]

[Laughter]

**JOE:&nbsp;** -- Absolute hot, horrible mess and you cannot deal with it without getting stinky and burned.

[Cross-talk]

**JOE:&nbsp;** -- Covered with crap.

**WARD:&nbsp;** The only thing that's worse is writing in ASP.NET or writing in Java or writing in Ruby or writing -- It wasn't the only things that are worse.

**JOE:&nbsp;** Oh, definitely not true.

**WARD:&nbsp;** Yeah, definitely not true.

**JOE:&nbsp;**.NET is --

[Cross-talk]

**WARD:&nbsp;** Did I gore somebody [inaudible] when I said Ruby, maybe? I don't know.

[Laughter]

**JOE:&nbsp;** Ruby is super slick those are so different and there's a huge reason for that. I'm not saying that where we're at with web development is because there's a whole bunch of idiot, lazy people. In fact, some of the tools that we've got for framework and web development are some of the most awesome and amazing innovative tools that we've seen in a long time. But .Net was able to be built up from the ground up all together. Ruby was, you know, it's this one big consistent piece and there's somebody in there thinking, "How do I put this all together and make this nice."

Frame and web development is monkey patches all the way down. This is Atlas. This is the story of Atlas but it's not turtles. It's monkey patches all the way down to this crazy browser that was not meant for anything other than somebody to just publish research documents and somebody else to be able to read them. That's what this is, and we're trying to build an application framework on top of it, and it is a hot mess. It's a dumpster fire. We are increasing the complexity necessarily so.

It is by far the most successful platform out there. It is becoming the only platform for, I don't know, the only platform, maybe that stuff there, but it is becoming the de facto platform to write applications on and mobile courses just becoming the new can of gasoline being thrown into dumpster fire.

[Laughter]

**CHUCK:&nbsp;** Joe, I had to applaud your rhetorical flourishes today.

**JOE:&nbsp;** Oh, I'm keeping with this motif, the whole show. Keeping this with you. And I'll be honest, I'm surprised of all people, you're not on my side of this fence. It's horrid. It's absolutely horrid.

Now, that being said, all the work that have been done by all these people that do any given piece has been amazing and they are better people than I am. Absolutely, better, smarter people than me. Angular 2 is an amazing piece, Angular 1 is an amazing piece, but I got to tell you, just Node, I don't know how many times I've had to 'rm -rf' my Node Modules, and re-install because it couldn't uninstall one stupid thing and re-install the updated version of it. I just uninstall one thing.

**WARD:&nbsp;** I hear you. I can't tell you how often I have to reboot my machine, and that has nothing to do with this development. There's all kinds of parts of technology that just drive me that. There's plenty that you'll annoy.

**JOE:&nbsp;** -- Except for updates. In fact, my Windows PC, I haven't rebooted except for updates in a long time.

**WARD:&nbsp;** Yeah, well, I rebooted mine three times today.

**JOE:&nbsp;** Consider the source. What are you putting in on there?

[Laughter]

**WARD:&nbsp;** All right. So one thing that I am in this podcast. That's what. That's what.

[Laughter]

**WARD:&nbsp;** I mean, one thing I am seeing here that Joe is saying is definitely true for me is that as I get into this, and I try and figure out what is going on, there are a ton of places to get stuck. There are so many more things, at least, it feels like going on. Then, when I use some of these other systems that are more cohesive and sort of better laid out. The tools have gotten better, and more complex.

But the thing that's interesting is that when I started doing web development about 10, 11 years ago, we were nowhere near the capability that we have now. But at the flip side is that because now we have all these extra capabilities, well, we need more tools to make it more simpler, and that doesn't always seem to happen. Or at least they need to handle more cases and so they get more complicated, too. So, I see where you're coming from, Joe.

**JOE:&nbsp;** I really get with these guys saying because even though this is the whole front-end development, this is an Angular 2's fault, by any means, this whole front-end development. But when you look at the difference between Angular 1 and Angular 2, the complexity is- of just getting your head around all the different pieces, they have to be in place, the number of moving parts is at least in order of magnitude, if not a couple of orders of magnitude. Maybe even three orders of magnitude and complexity.

Angular 1 was much fewer moving pieces, and Angular 2 and all the things that have to do with it, are so many more. I mean, I've had to become an expert in SystemJS. I don't even know what SystemJS was 18 months ago. Never even heard of it. I had to become an expert in SystemJS in order to do Angular 2. It's just there are so many pieces. Webpack - you have to become an expert in Webpack. You can't just throw in a little bit of Webpack. You've got to know Webpack. You got to understand. You've got to be able to diagnose it and debug it.

All these pieces, I would say, the one piece that I think is actually fairly well built, not necessarily- Sorry, let me take that back. They're all really well built. The one piece that I think actually has really nice boundaries, you don't have to dig in quite so much is Karma. Karma is great, but everything else that I deal with when it comes to an Angular 2 project, you've got to dig in. You can't just take the abstraction at its face value today. You just can't do that. I think that's the nature of this complaint and I resonate with that.

**JOE:&nbsp;** At the same time, I think that when you look at what we were doing, let's say, six, seven years ago, and your level of complexity in which JavaScript existed, the majority of it was a lot of no small very specific things in the browser using jQuery. That was certainly my introduction really to the JavaScript world. I think it's unfair to take that as a context and then we look at what we're doing now. So, with JavaScript on the server side, with doing hybrid mobile apps with JavaScript, with doing full on desktop applications in Electron, to insanely complex or non-trivial line of business web applications in JavaScript to not expect the power and the capabilities of what we're doing in JavaScript, to increase and not have a proportional increase of complexity in the tools that we're using.

In fact, I would say it's actually it's not proportionate, but rather it's fractional in the sense of I think we've have gotten thousand times more power in JavaScript in terms of what we can do, and the platforms we can target with a fraction of complexity increase. Yes, it's more complex. You have more moving pieces. But at the same time, we can do so much more and to not expect that to increase by some level of complexity, I just think is not fair.

**WARD:&nbsp;** Well, I agree with your point, but I disagree with your subjective evaluation as to how much the complexity has gone up versus how much our capabilities has gone up.

**JOE:&nbsp;** Yeah, if you're comparing it to when all I did was do some validation on the client side, yeah, now my capabilities have gone up hundred fold.&nbsp; Although, again, to be honest, let's go back to just ASP.NET Version 1 with its server side rendering on every page, and let the creator of Rails, ummm, what's his name?

**LUKAS:&nbsp;** David Heinemeier Hansson.

**JOE:&nbsp;** DHH, there you go. DHH. His point which I completely disagree with him, and I think, he's the Trump of the front-end world --

[Laughter]

**JOE:&nbsp;** -- In some cases --

[Chuck's hysterical laughter]

**JOE:&nbsp;** -- I'm not even sure -- that's has a compliment or criticism.

[Cross-talk]

**CHUCK:&nbsp;** I might be able to get it on the show with that one.

[Laughter]

**JOE:&nbsp;** -- Is dead and him pushing that server side rendering is the way to go. I think it’s just really is Trump lines. That's what that is. Either Trump stole from him because he was first or he stole from future Trump. He travel into the future and came back to say those things, right?

But server-side rendering could produce apps as complex as we're building now. But, it's just, the user experience sucks so we've refined our user experience. So, I want to go back to your point about jQuery. Back long ago, we just did these little bits of jQuery, then somebody tried to write an app and the only front-end technology the user has jQuery which actually is the most common front-end right now. Right now, the most common front-end is just a whole bunch of jQuery.

The first time somebody did that, it was the first time that a dumpster was lit on fire, right? That was a horrid mess, trying to maintain a lot of code in jQuery. And then, tools like Knockout came along and Angular 1, and these are things, and they wrapped up all the garbage into a nice neat framework. Then, we were able to build these really powerful apps with a minimum increase in complexity.

I think that's the point where I agree with you, Lukas. It was a modern inclination in complexity. You had to understand a little bit more about Angular and about the way that the web worked in order to do Angular instead of just jQuery, and you had a ton more capability to build a ton faster. But I think if you take those from Angular 1 to the whole React, Angular 2 cycle or whatever, Ember world, that - I don't know about Ember. Maybe, I might be wrong about that. But, the increase in complexity as many fold and yet the increase in capability is marginal.

**CHUCK:&nbsp;** Okay, so, I want to just hit this really quickly, then. Are we going to see something nice come along and wrap up some of the garbage that makes this unpleasantness pleasant?

**WARD:&nbsp;** I think that's already- Here's what I don't like. I mean, let me try and recast it again. The premise was that it is difficult to get set up to develop in Angular. That doesn't have to be true. Take the 5-minute quick start which is not five minutes if you read every little word, and try and understand every aspect of what got delivered but --

**LUKAS:&nbsp;** He said that it was getting his head around it took a day.

**WARD:&nbsp;** Exactly. What if you don't- But that isn't what the question is? The question is, "How do I get set up to start doing things," and that can be well under five minutes especially if you just sort of download the repo, go in PM Star and go because we have a quick start repo. So if you decide you need to know every moving part from day one, this is going to be a hard slog. But if your goal is to say, "Wow, yeah. I realized that there are a lot of artifacts produced by the CLI. There are many fewer, but still an awful lot of artifacts produced by following the quick start."

So if you need to know what every artifact is, right from the beginning when you know nothing about front-end development, you're in trouble. But if you instead, take the position of, "I really would like to start doing something and be productive and build things," then I think that you can do that very quickly in Angular 2, if you just accept some of the artifacts you get from either of those two paths. That's my real point.

**CHUCK:&nbsp;** So let me chime in on this because I started a project a couple weeks ago, and I've kind of been talking to people about Angular 2. I looked at the docs, but I hadn't really dove in that deep because it was still in beta and I did a few things for the podcast. But that was way before CLI.

So I went through the quick start a couple weeks ago, and I was just like, "You know what? Let me just build something," because I just felt like building something, and I thought, "Okay, well, I'll do it in Angular 2." So when I started it, I went along and I followed the tutorial. The quick start got me part the way to where I want to go. Then, I just kind of scan through the Tour of Heroes tutorial until I found the bits that I wanted, and I just ran the CLI code and then, I started writing Angular 2. I got the ways down the road to where I wanted to be.

The thing that I found was that, yes, there was a lot going on that I really didn't understand. I just wanted to make craft work so I wasn't interested in figuring out how it worked. All I cared about was that when I ran npm start, it fired up the web server, and when I changed the file, it updated my page and it did all that perfectly well.

So there's a question in here that says, basically, "Has it become out of reach for hobbyists or is it the exclusive property of experts and full time client-side developers only?" and I have to say no.

I mean, if you really wanted to dig in on this, and say, "Okay, well, how is it building, and how is it launching, and how is it putting us in the browser and how is it doing all the TypeScript stuff?" Then yeah. I mean, there are definitely things there that you have to understand. But for me, just having something up where it reloads the index study HTML, and I was writing purely from in-code, and I just wanted something to work. I mean, Angular was pretty darn easy once I got that far and --

**WARD:&nbsp;** Are you talking about Angular 1 or 2?

**CHUCK:&nbsp;** Angular 2.

**LUKAS:&nbsp;** And let me jump in here, if you don't mind, Chuck.

**CHUCK:&nbsp;** Yeah.

**LUKAS:&nbsp;** Just to be fair, and this was really the point, that really kind of stop- It really made me think about where is this individual coming from is that very thing of, "Has Angular 2 become out of the reach for hobbyists or is it exclusive property of experts and full time client-side developers only?"

So what I did is I said, "Let's just strip away all the bells and whistles," and I'm going to do an Angular 2 application in just ES5. Now, because I've got Angular 1 for so long, I have a solid grasp of Angular 2, I think, that the context is a little bit skewed slightly --

**CHUCK:&nbsp;** I don't think so, Lukas, because I'm getting the impression from this and the way that the question was framed what has to happen before Angular 2 apps or as easy as Angular 1 apps or at least, easy to start as Angular 1 apps. I think the person asking the question is familiar with Angular 1.

**LUKAS:&nbsp;** Right, so with that said, is I went and I wrote in Angular 2 app and ES5, and I found it to actually be really comparable to writing in Angular 1 app in ES5, as well. You know, you still have manage your imports manually with doing this index study HTML. But it was a lot of the same wiring up to the point where I'm almost like, "This is actually almost easier than writing just in Angular 1 app in ES5."

So, to be honest I think, it's about the same. You can read about it on my blog, OneHungryMind.com, and I kind of basically converted a TypeScript app in ES5 and it's really truly was not that bad.

**JOE:&nbsp;** I want to say something here. First off, Lukas's blog posts are always top notch. So if you have any free time at all, you should absolutely go and read this.

**LUKAS:&nbsp;** I'm waiting for 'but.'

**JOE:&nbsp;** No. Okay, well, all right. There is a 'but' here. But unless you're --

[Cross-talk]

**JOE:&nbsp;** -- Into the dumpster fire, there's no reason for anybody to learn how to do Angular 2 in ES5 because it doesn't translate like it doesn't help you --

[Cross-talk]

**JOE:&nbsp;** Yeah, you're not going to be doing it any in ES5.

[Cross-talk]

**WARD:&nbsp;** I love the post too, but I love that post as an aficionado who is kind of curious about how to do it that way. So, it succeeds on like that's how do I want to brew my own beer with cardboard tubing. I'm kind of curious about that but I think I'd rather just drink it. But I mean, it was really crisp and clear. Lukas and I applaud you for it. I just don't think that's- I don't think you would say, and so, the conclusion of this post is you should go out and write your app in ES5. You weren’t' suggesting that, we're you?

**LUKAS:&nbsp;** And let's be clear, I wouldn't even write my Angular 1 apps in ES5 so all the Angular 1 development that I do is in ES6 in an Angular 2 style because there are so many advantages to doing that. But you don't want the complexity - the mental overhead - of having to deal with somebody's tools, so in ES6, a lot of advantages. But you have to have a transpiler and a package manager and a modulator. It is because the --

**WARD:&nbsp;** You know what's the dead simplest way to get a feel for what really Angular 2 is about is to use one of the Angular 2 plunkers.

**LUKAS:&nbsp;** Yeah, absolutely.

**WARD:&nbsp;** Because it just reaches out onto the web. You don't have to think about build, test, or any kind of support tools, or anything like that. You just want to get as close to what's really Angular 2 as you want to, and see what's really involved as opposed to all the peripheral stuff. Go into the docs, fire up one of the plunkers from there.

[Cross-talk]

**JOE:&nbsp;** -- That isn't broken as well.

**WARD:&nbsp;** Not a single one of the doc --

**JOE:&nbsp;** Not the one on the Angular.io. I'm talking about this like on a bigger scale. It's just plunker is just one more moving piece.

**WARD:&nbsp;** Yeah, I'm talking about somebody who was curious about what it means to develop an Angular 2 without all of the distractions of what it would take to build, tests, maintain, worry about performance, all that other stuff. Let's face it, when you're trying to learn a new framework, that is peripheral stuff.

**CHUCK:&nbsp;** So two things that I'm want to just chime in here with. The first one is that I basically heard Lukas say, "You can build the [inaudible] in ES5 but I prefer to walk, at least, part way into just dumpster fire," because he's using ES6.

[Cross-talk]

**LUKAS:&nbsp;** -- In a dumpster fire. Let's be honest, the reason why we're in the state we're in right now, the majority of it is because browsers are so --

**CHUCK:&nbsp;** Right, we're in transition.

**LUKAS:&nbsp;** I mean, that's it. We have to- I can't tell you, how many large line of business apps is basically compromised because we've had to support of Legacy Browser.

**JOE:&nbsp;** Yep.

**CHUCK:&nbsp;** Yeah.

[Cross-talk]

**JOE:&nbsp;** You're saying legacy, that's totally not the litmus test here. Any browser, it doesn't have to be a Legacy Browser --

**WARD:&nbsp;** Ninety-nine percent of all browsers are Legacy.

[Laughter]

[Cross-talk]

**JOE:&nbsp;** I would say, a hundred percent of all browsers are Legacy, but --

**CHUCK:&nbsp;** -- Any browser today is Chrome. The Chrome that is up today is a dumpster fire, and it's not Chrome's fault. It's the underlying technology. It's the fact that it's --

[Cross-talk]

**WARD:&nbsp;** -- Supposed to do with your thesis.

**CHUCK:&nbsp;** Oh, nothing. I'm just bitching.

**LUKAS:&nbsp;** Oh, man.

[Laughter]

[Cross-talk]

**JOE:&nbsp;** -- Understanding to be had here and that is I disagree that this is the domain of a hobbyist. Yes, you can do Angular 2 as a hobbyist, as a full-stack developer. But if you're going to do anything over a few thousand lines of code, maybe, 15,000 lines of code, you'd better have an expert on your team or have easy access to expert or be willing to dig in and become an expert in all these ancillary technologies because --

[Cross-talk]

**JOE:&nbsp;** -- Long gone is the day.

**WARD:&nbsp;** -- Every language, every platform. I don't believe that --

[Cross-talk]

**WARD:&nbsp;** -- Application development environment that are suitable for hobbyists.

[Cross-talk]

**JOE:&nbsp;** I'm not talking hobbyist like this is my day job. I mean, like I have a full set of developer and what I really do is Ruby, but I have to do some front-end stuff, right? We're on the front-end, too. I just want to have a nice, gentle introduction, and over time I want to learn more, and get more into it. But that is not true today. If I'm a Ruby dev, then I'm going to put an Angular 2 front-end, I'm going to have to spend a month coming up to date and become an expert in Angular.

[Cross-talk]

**WARD:&nbsp;** -- Point to contradiction you, but that's okay.

**CHUCK:&nbsp;** All right. So, I think this is really the heart of the issue, though is that a lot of the setup is set up, so that you can write an Angular 2 app in TypeScript with all of the nice bells and whistles, and have it run in the current browser situation that we're in now. I think that's really what it boils down to.

You know, the plunkers, that's all nice. But the question was about getting a new Angular 2 apps started. So you have to do all of this set up in order to make Angular 2 run in the current browser system, and I –

**JOE:&nbsp;** No, no, no. We don't even touch on getting it out to production.

[Cross-talk]

**LUKAS:&nbsp;** This is where I have to draw the line, is the Angular CLI does that all for free? Like, you don't have to do any of that. But now, it's like I don't want to actually have to do anything to get up and running. Okay, here's the Angular CLI, and it's like, "Oh, wait a second. You're going to do this all for me?" But I'm sorry, that this is what you had to do to give me all these free things, and that's where I think, one is going to be like, we're going to write any code, but we're not going to do anything, and we're not going to have to make any investment.

I think, it completely marginalizes what it is that we do when write code, and I think you have to understand that programming is hard. You know, it is a learned skill, but in order to be effective, especially in the context of browsers aka dumpster fires, you're going to have to pay a price to do that reliably. This is not like .Net or Java where they have the luxury of controlling their runtime.

When you write Java, you're targeting a jvm that they can control and that's why you have a more consistent experience. We are building something or targeting something that was never even intended to do this. I think, when you accept that, like we're building something that really was never intended to be and we're doing a pretty amazing job building a lot of really incredible things, I think, you have to accept that there's going to be compromises, there's going to be complexity, and you're going to have to invest in paid of toll, to get to that end point.

**JOE:&nbsp;** Absolutely. There's a term that. It's called Stockholm Syndrome.

[Laughter]

**WARD:&nbsp;** Let me ask this other question, okay? Because I think, at this point, we just have different points of view on the situation. But what I'm curious about then is as browsers continue to implement more ES6 or ES2015, 2016, 2017 features, and we start moving away from the ES5 build target, and we have more of these capabilities in the browser, does this get better? Or are we --?

[Cross-talk]

**WARD:&nbsp;** -- For multiple environments is what I'm --

[Cross-talk]

**JOE:&nbsp;** It doesn't matter --

[Cross-talk]

**JOE:&nbsp;** -- We have to have a build now.

**WARD:&nbsp;** Even if we're targeting only one browser, and it was a perfect ES6 browser, most of what this person is complaining about would still exist.

[Cross-talk]

**JOE:&nbsp;** I want to address Lukas's point about programming is hard. Programming absolutely is hard. Writing code that does the actual business purpose of what you're trying to do is super hard. The logic, it's incredibly difficult. It just sucks that on top of having to do that already difficult task, we have to throw on another extremely difficult task, and that is understand all of the wrappers and pieces that need to be in place in order to put this thing together, right?

**WARD:&nbsp;** That's what I want to push back on, Joe. Why do I need to understand? Do I really need- I don't have to really know SystemJS until I'm thinking about production --

[Cross-talk]

**WARD:&nbsp;** I don't. I write hundreds of apps and I don't have to mess with SystemJS until I start thinking about production.

**JOE:&nbsp;** The only time you don't have to think about it is if you were to use the CLI, and let me put this in context. The CLI, what it does, it hands out to you a dumpster --

[Laughter]

**WARD:&nbsp;** Who cares, Joe?

[Cross-talk]

**WARD:&nbsp;** -- Netizen dumpster.

**JOE:&nbsp;** Eighty year old TNT boxes that are bleeding nitroglycerin and hands it to you and says, "It's perfect, just don't shake it."

**CHUCK:&nbsp;**"NG new dumpster," I love it. So here's the question then. Because I think, I generally agree with both of you to a certain degree, I don't completely agree with either of you. But --

[Laughter]

**CHUCK:&nbsp;** -- So to one point though, the thing is that, I don't have to understand SystemJS, as long as I play inside the safe lines.

[Cross-talk]

**CHUCK:&nbsp;** So here's the deal. If I use Angular CLI, or if I follow some directions and copy and paste some code off the internet, as long as my use case matches up with what I have there, I don't have to understand what SystemJS is doing to me. All I have to understand is that if I follow these steps, it's going to work.

But the second I move out of those lines, then I have to understand what SystemJS is doing, and if I don't understand why those boundaries are there, and I step over them, then I'm in for pain. So I think there's a place here where, yeah, to some degree, I don't really have to care about what SystemJS is doing. But also, there are probably going to be some use cases for me that are different from the person who's telling me how to use SystemJS, and so I'm going to have to understand to some degree what's going on there when I start moving beyond those boundaries.

**WARD:&nbsp;** I just found out to be true in every platform I've ever worked in, and the question is how big are the initial line, how long can I color inside the lines, and be successful? But, as soon as you cross those things, you're into mystery land. That's been true in every platform I've ever been.

**JOE:&nbsp;** Yeah, but this mystery land is so much bigger. That's the problem. It's just much bigger, there's --

[Cross-talk]

**JOE:&nbsp;** -- I want to do something different, spend half an hour of learning something new, and then get into it. It's not --

**WARD:&nbsp;** I have been so lost --

[Cross-talk]

**JOE:&nbsp;** -- Weeks and months.

**WARD:&nbsp;** -- You spend weeks and months trying to configure IIS, and I'm not picking on Microsoft. It just happens to be the other technology --

[Cross-talk]

**JOE:&nbsp;** You can go and pick technology X, and make that same statement.

**WARD:&nbsp;** MySQL, you know, databases, you color outside the lines, you're getting into lock, you don't know what you're doing --

**JOE:&nbsp;** The lines you're talking about --

[Cross-talk]

**CHUCK:&nbsp;** All right, hang-on. Lukas what are you trying to say?

**LUKAS:&nbsp;** What I want to make is, you do not have to understand a tool at the atomic level to use it. For instance, the Angular quests Webpack starter. I pull that down and it spun up, it worked, and I was able to start writing Angular 2 within that starter project without understanding Webpack.

The interesting thing, which I think is super rich here, is once I started to want to do something in a Webpack, so I'd already been effective, I didn't understand Webpack, it was just there and it was supporting me, and I said, what's going on here. I would like to learn a little bit more about Webpack. You know what I did? I got on Pluralsight, and I watched a Webpack course by none other than Joe Eames - the irony.

[Laughter]

[Cross-talk]

**CHUCK:&nbsp;** Yes, I mean, the dumpster man himself is like that's how I learned Webpack is by watching a Pluralsight course on Webpack from Joe. But I'd already been using it for months. It's only when I got outside of this high-level course grained activities, and I want to get into very specific things, and I said, "Okay, I need to invest into this skill or this tool so I can have a high-resolution, a better picture of what's going on," and I went and did that.

[Cross-talk]

**WARD:&nbsp;** Can I buy one of them, Lukas, because you're making a great point, and the thing that I would add to that is that you had already felt value from the platform before you got to that point, and so you knew that the investment in learning what you needed to know was going to pay off because you had had so much value before. The challenge for a guy who was writing that email is that he's trying to understand everything before he's gotten value from anything. That's going to be painful, no matter what technology you pick.

**JOE:&nbsp;** I think, you're a bad example, Lukas, because you already understand so much stuff, just like Webpack and modules. It's just horrid, and when you get in there, I'll bet, when you go in, instead of fiddling around with Webpack, it made a lot more sense to you than it will to most people because you are already such an expert in front-end dev. I will say that you're picking one of the better tools. Webpack is one of the better tools. They're all really good tools, but Webpack is actually a bit more intuitive. Especially, look at the configuration versus a SystemJS configuration which is merely gobbledygook.

**CHUCK:&nbsp;** All right, I'm going to have to push us into Picks but --

**JOE:&nbsp;** What? No, no, no, no, no. We're not even have started on this.

**LUKAS:&nbsp;** Chuck, you can take off. We're going to finish this in about two hours.

**CHUCK:&nbsp;** I know, right?

[Laughter]

**CHUCK:&nbsp;** I have an anecdote, but our poor listeners, I mean, I'm just sitting here and go, "Man, we could do this for another hour." They already are hang up on us. They already know we're --

**WARD:&nbsp;** We can go another at least five more minutes.

**CHUCK:&nbsp;** That's fine.

**WARD:&nbsp;** And we're going to do like a summary and wrap up stuff here.

**CHUCK:&nbsp;** I'm not in any hurry. I just don't want this to be an hour and a half show.

**LUKAS:&nbsp;** Joe, I think you made a really good point of highlighting the frustration in the tool set. Again, I want to be sensitive to that. It exists, and I totally get it. At the same time as I think it's a small price to pay, or just the universe that is opened up to us when we learn to you know, leverage these tools. Even just a little bit. I think, it's worth it. I think, it's absolutely worth it to get into that dumpster, and head first --

**WARD:&nbsp;** For the banana peels.

[Laughter]

**LUKAS:&nbsp;** The stuff that is being built, with this dumpster fire is just incredible. The fact that you [inaudible] two app, wrap in Electron, and now you have a good desktop app in five minutes, like that's just ridiculous.

**WARD:&nbsp;** You know, if you want to be a hobbyist, and you don't like this, leave. But if you're going to be expected do professional development and deliver applications to clients, this is the world you're going to have to get to. So the question really has to become what's the most effective way to get good in this environment in my view. Before we go too far, I want to go back to the guy - this mythical person who wrote this thing - I want to say, I am totally sympathetic.

My point would not be to say that you're wrong. My point is to say that the perspective of the email writer, your expectation is not going to serve you well. I'm not saying it's wrong, I'm just saying it's not going to serve you well because your perspective says, "I have to understand everything before I can do anything," and you're going to fail. You're going to fail on client-side development because it just isn't that way.

But if you're willing to suspend understanding about things that I can tell you don't have to know just yet, and follow along, you can have a successful growth path and learn how to program in this environment. You can learn these other things when you need to know them, and you'll be successful.

**JOE:&nbsp;** All right. So I want to do my little summary here, and that is that I agree with both of you guys, at least, to the theme of what you're saying. My whole point is I still think it sucks. On the other hand, I really do like the complexity of front-end development because it pays my freaking bills - do plural say.

[Laughter]

**JOE:&nbsp;** Anybody out there who wants to get to web development, thank you from the bottom of my heart. If you want to do Angular 2, thank you because you're going to have to watch ten of my courses --

[Laughter]

**JOE:&nbsp;** -- So that you can actually understand what's going on, and I'm going to go --

[Cross-talk]

**JOE:&nbsp;** The current modern day front-end web development is going to buy me a boat.

[Laughter]

**WARD:&nbsp;** So, the gist of that is, "Joe needs a new pool, learn Angular 2."

**LUKAS:&nbsp;** Learn Angular 2.

[Cross-talk]

**CHUCK:&nbsp;** I know where he lives so I'll invite myself over.

**WARD:&nbsp;** His kids need shoes. Learn Angular 2.

**JOE:&nbsp;** I do want to say that the tools that have been put out are amazing, and done by amazing people and there's a couple of times before. But there could not be enough props given to the people that are spending their time on Webpack and Angular 2 and SystemJS and TypeScript, especially the people that are doing it without getting paid. This is one of the most amazing things that people that produce these tools.

There's all these sharp corners and they're going around and patting these sharp corners for us, and we owe them all a huge debt of gratitude. It just sucks that we had so many sharp corners to start off with. It's a ton

Don't be afraid to get in there and learn because you're just going to have to. We're past the days when you could do a little bit of dabbling and get a lot of stuff done. You're just going to have to get in there and learn stuff or have somebody on your team that does and lament that, but it is the reality of where we are at.

**WARD:&nbsp;** Well, I don't think, any of us can disagree with that.

**CHUCK:&nbsp;** Wow, we had a fight in a dumpster fire and I'm feeling pretty good about all this.

[Laughter]

**JOE:&nbsp;** Nobody goes out about looking good or smelling good. We all stink.

**CHUCK:&nbsp;** It is so interesting just to dig into this and really have a conversation about it because people are in different places with it. All right, well, yeah, let's go ahead and do some Picks. Ward, do you want to start us with Picks?

**WARD:&nbsp;** Sure, there's a book that people are talking about a lot. It's called Chaos Monkey by a guy who had his startup, sold it, joined Facebook before it went IPO, live through it, got fired by Facebook. It is quite the ride, and it gives you quite a bit of insight into how startups work, how the game is played, how products get developed, the kinds of tensions that exist between competitors within companies and across companies. It may put you off ever doing anything with a startup. It's just a fascinating ride and I recommend it so it's called Chaos Monkey: Obscene Fortune and Random Failure in Silicon Valley. Check it out.

**CHUCK:&nbsp;** All right, Lukas, what are your Picks?

**LUKAS:&nbsp;** I have two picks. The first one is I've been hooking kind of smart devices into my house and I bought this thing called the Wink Relay Station, and what it does is it replaces your light switch, and then it allows you to actually hook into a lot of your other devices. So I have an Amazon Echo, a Nest Camera. I have a garage door opener that's connected and some different things. Then, I actually just hooked up the Ecobee Thermostat, and I can actually control all of that from the Wink relay switch. So it's been a really cool and I'm kind of basically hooking my house up and having this thing is kind of like the central station to do that. I've got like an LCD display, it's voice activated, pretty neat.

My second one, in a bit of a quandary about how to do this, in the sense that, it's a person conviction. I never use profanity but I love this book so much. So the compromise I'm going to make is it's by Kathy Sierra, and it's about making users awesome, and it's just amazing. So Google that. I actually put the link in. It's a great book. I just bought two copies that I'm just going to give away because I love it so much. I actually got it from Joel Hooks as a gift. It's been probably one of the best books I've read this year.

**CHUCK:&nbsp;** Awesome. Joe, what are your Picks?

**JOE:&nbsp;** All right. So this is very topical. I think, I'm going to pick learning because you're going to have to do a lot of it.

[Cross-talk]

**JOE:&nbsp;** Specifically not being afraid. So I want to give encouragement out there. Anybody that's out there that's feeling a little bit of trepidation about the large mass of stuff that I'm selling that you need to understand in order to do modern front-end web development. Not be afraid of it, just get in, and over time, it just all starts to make more and more sense. So I want to pick that.

I also want to pick a statement made by- It was at the funeral for the Dallas police officers or it was a statement made shortly after. I think that was Clinton. Either Clinton or Bush who said it, but he said something that, I can't remember exactly who it was, but struck me in it. Basically is, "We often judge other groups by their worst members, yet judge ourselves by our best intentions." That really struck me as something that's definitely important in this day and age is to not judge other groups by their worst members. Also, be a little bit more reasonable about ourselves as well.

My final pick is going to be VidAngel which is a service speaking of not using profanity. I love the ability to watch really great shows like I've just been watching John Wick. Awesome show, and I could turn off all the F words because I personally don't like to hear. I like to hear that as little as possible so --

**WARD:&nbsp;** So what does it do? It intercepts the words and bleeps them out?

**JOE:&nbsp;** Yeah. It actually has a gazillion different filters. You can filter anything from- if you don't want to watch it with- well, you would probably want to watch John Wick with your kids, but if you don't want the women in bikinis, it'll skip past those. You can pick anything remotely objectionable. They have all these different filters. You will just say, "I don't want this. I don't want that."

**WARD:&nbsp;** If I listen to Chris Rock you'll be beep-beep-beep-beep-beep-beep-beep --

**JOE:&nbsp;** Yeah.

[Laughter]

**JOE:&nbsp;** And it's just for movies. There are a lot of shows like The Wolf of Wall Street, if you took out the F words, the show gets shorter, right? It's like six minutes long.

[Laughter]

**JOE:&nbsp;** I don't know, there are some guys, there is some money, and then all of the sudden it was over. I'm not really sure what happened? But VidAngel, I love it. I think, it's an amazing service and I've heard that they're having some potential legal problems which is really too bad because the guys that put all the F words are really upset that people are trying to take them out. So they like to see what's that sort of stuff.

**WARD:&nbsp;** Yeah, they got 'VidDevil' which are just only --

[Cross-talk]

[Laughter]

**JOE:&nbsp;** That was actually an April Fool’s joke by VidAngel. You can watch just the smut was taken out. They actually did that as an April Fool’s joke - VidDevil. Anyway, I really like their service and watched a lot of shows that I wouldn't normally watched. Their stuff is my last pick.

**CHUCK:&nbsp;** Awesome. Just on that same note of the Dallas shooting. One of the things that I found very inspiring was that there were protesters basically on both sides of the street. I'll put a link to this off of CNN. But there were protesters from both sides of the street. One side was Black Lives Matter, and the other was basically the counter group to that, and they were all there in like cowboy hats and big belt buckles and stuff. What went up happening was the leader of the one group and the leader of the other group met in the middle of the road, and started chat for a minute. Then they hugged it out, and then a whole bunch of people cross the street and they were all just hugging and talking and they invited the police officer who was there to keep the peace to join them in a prayer.

You know, to your point that don't let the worst of any group define what the group's about. I mean, this just shows that for all of the differences that several of these groups have and for all of the things that are being shouted from both sides, we all want, at least to some degree, some of the same things, and we're all people. It was just really cool to see it all come together and see people really just talk about it. Instead of having these horrible exchanges between people who are legitimately worried about things on both sides. I'm going to make that a pick.

Then, I've got a couple of other picks. I went to Chicago last week for Podcast Movement which is a big podcasting conference, as you can imagine. I got a lot of great ideas. I'm probably going to be changing some things here over the next few weeks. But while I was there, one of the things that I did is I had to run down to the Apple Store like three times because my iPhone broke so I had to drop it off and pick it up. When I picked it up, I actually bought an iPad Pro, and I just love the thing. I got an Apple Pencil so I was taking notes by hand during some of the sessions. I was using an app called GoodNotes, and it actually does OCR on your handwriting and you can do a full text search on your written handwritten notes on your iPad Pro which is really cool.

I also got the Smart Keyboard, and I really like that as well. I got the 9.7 inch iPad Pro, and when I was on the airplane and stuff, it just worked really well, and it didn't overload the tray table in front of me which my laptop did on the way out. So that was also nice.

One of the thing I figured out with it was that when I'm at the cafe, and I have really bad internet access, when I try and send an email or reply on the Gmail web app, it sits there and says loading when I click the button. But because, and I don't know if it's a hybrid app or if it's a native app, but the Gmail app on my iPad Pro, I can just type the email because all of that interfaces local, so it just loads it up, I type it, I hit send, and then, it just has a spinner there until it finally get it sent. So, I could actually move through my inbox and send those emails and make it all go without a whole lot of trouble with the web interface not loading because it had to talk to the server over a really crappy connection. Anyway, iPad Pro, really love it, and I'll put links to all those things that I mentioned there in the show notes.

All right, so one last thing that I want to bring up is the show has a Facebook page, and I really want to get people to support it. It currently has nine likes. I'd like to get that a little bit higher. It's at Facebook.com/AdventuresInAngular, and Adventures In Angular is all one word. Check that out.

The automation I had that was posting the episodes there cracked out. I was using Zappy. I don't know the problem is but I'm working with their support. But I'd also like to start some other conversations and post some other stuff there. So please go like the page, and help us get the word out about the show. And with that, I guess we'll go ahead and wrap up the show. Thank you all for coming. We'll catch everyone next week.

**_[Bandwidth for this segment is provided by CacheFly, the world’s fastest CDN. Deliver your content fast with CacheFly. Visit CacheFly.com to learn more.]_**

**_[Do you want to have conversations with the Adventures in Angular crew and their guests? Do you want to support the show? Now you can. Go to AdventuresInAngular.com/forum and sign up today!]_**


