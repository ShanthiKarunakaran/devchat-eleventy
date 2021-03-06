---
layout: layouts/post.njk
title: >
      218 JSJ Ember.js with Yehuda Katz
date: 2016-06-29 07:00:42
episode_number: 218
duration: 42:47
audio_url: https://media.devchat.tv/js-jabber/JSJ218YehudaKatz.mp3
podcast: js-jabber
tags: 
  - js_jabber
  - podcast
---

## Check out [Newbie Remote Conf](https://allremoteconfs.com/newbie-2016)!
&nbsp;02:38 - Yehuda Katz Introduction
- [Twitter](https://twitter.com/wycats)
- [GitHub](https://github.com/wycats)
- [Blog](http://yehudakatz.com/)
- [Tilde](http://www.tilde.io/)
- [Peter Solnic: My time with Rails is up](http://solnic.eu/2016/05/22/my-time-with-rails-is-up.html)
- [Peter Solnic: Abstractions and the role of a framework](http://solnic.eu/2016/05/30/abstractions-and-the-role-of-a-framework.html) (Follow-up)
- [Ember.js](http://emberjs.com/)
- [The Skylight Blog: Inside Skylight](http://blog.skylight.io/)
05:37 - Batching Updates10:04 - Naming
- [Fastboot](http://emberjs.com/blog/2014/12/22/inside-fastboot-the-road-to-server-side-rendering.html)
- [Services](https://guides.emberjs.com/v2.1.0/applications/services/)
- [glimmer](https://github.com/tildeio/glimmer)
14:19 - Communication 
- [Skylight](https://www.skylight.io/)
16:21 - Decorators19:46 - “Junior Developer” and Knowledge Bias
- [CodeNewbie Ep. 90: Creating EmberJS - Part I with Yehuda Katz](http://www.codenewbie.org/podcast/creating-emberjs-part-i)
- [CodeNewbie Ep. 91: Creating EmberJS - Part II with Yehuda Katz](http://www.codenewbie.org/podcast/creating-emberjs-part-ii)
28:25 - Termanology in Tech29:23 - Diversity 
- [Women Helping Women](http://emberconf.com/women-helping-women.html)
&nbsp;Picks
- [Event Driven: How to Run Memorable Tech Conferences by Leah Silber](https://leanpub.com/eventdriven) (Yehuda)
- [TypeScript](http://www.typescriptlang.org/) (Yehuda)
- [emberjs/rfcs](https://github.com/emberjs/rfcs) (Yehuda)
- [rust-lang/rfcs](https://github.com/rust-lang/rfcs) (Yehuda)
- [Pretty Pull Requests](https://chrome.google.com/webstore/detail/pretty-pull-requests-gith/ljnjpkadhhcdniohpfilddnhahoigdec?hl=en) (Aimee)
- [Full-Stack Redux Tutorial by Tero Parviainen](http://teropa.info/blog/2015/09/10/full-stack-redux-tutorial.html) (Aimee)
- The mountains (AJ)
- The quadruple click in [iTerm2](https://www.iterm2.com/) (Dave)
- [2016 UtahJS Conference](https://conf.utahjs.com/) (Dave)
- [Start With Why by Simon Sinek](https://www.startwithwhy.com/) (Chuck)


### Transcript

 **DAVE:&nbsp; &nbsp;** Yesterday, I made a camp fire in my backyard.

**_[This episode is sponsored by Frontend Masters. They have a terrific lineup of live courses you can attend either online or in person. They also have a terrific backlog of courses you can watch including JavaScript the Good Parts, Build Web Applications with Node.js, AngularJS In-Depth, and Advanced JavaScript. You can go check them out at FrontEndMasters.com.]_**

**_[This episode is sponsored by Hired.com. Every week on Hired, they run an auction where over a thousand tech companies in San Francisco, New York, and L.A. bid on JavaScript developers, providing them with salary and equity upfront. The average JavaScript developer gets an average of 5 to 15 introductory offers and an average salary offer of $130,000 a year. Users can either accept an offer and go right into interviewing with the company or deny them without any continuing obligations. It’s totally free for users. And when you’re hired, they also give you a $1,000 bonus as a thank you for using them. But if you use the JavaScript Jabber link, you’ll get a $2,000 bonus instead. Finally, if you’re not looking for a job but know someone who is, you can refer them to Hired and get a $1,337 bonus if they accept the job. Go sign up at Hired.com/JavaScriptJabber.]_**

**_[Let's face it. Bookkeeping is hard and it's not really what you're good at anyway. Bench.co is the online bookkeeping service that pairs you with a team of dedicated bookkeepers who use simple, elegant software to do your bookkeeping for you. Check it out at Bench.co/JavaScriptJabber for 20% off today. They focus on what matters most and that's why they're there. Once again that's Bench.co/JavaScriptJabber.]_**

**_[This episode is sponsored by Rangle.io. Rangle have been working with Angular 2 for a long time, and they are now putting together an 8-hour, 2-day course designed to help Angular developers, learn how to write apps in Angular 2. If you're looking to level-up your JavaScript and Angular 2 skills, then go to Rangle.io/Training and click on the link for Angular 2 training. If you're looking for other training in React or JavaScript, they also have that in Rangle.io/Training.]_**

**CHUCK:&nbsp;** Hey, everybody, and welcome to Episode 218 of the JavaScript Jabber show. This week on our panel, we have Aimee Knight.

**AIMEE:&nbsp;** Hello.

**CHUCK:&nbsp;** AJ O'Neal.

**AJ:&nbsp;** I think, I'm here. Coming at you live from Pleasant Grove.

**CHUCK:&nbsp;** Dave Smith.

**DAVE:&nbsp;** Yoo-hoo!

**CHUCK:&nbsp;** Jamison Dance.

**JAMISON:&nbsp;** Hey, friends.

**CHUCK:&nbsp;** I'm Charles Max Wood, from DevChat.TV. Quick shout out about Newbie Remote Conf which should be held in July. We also have a special guest this week, and that is Yehuda Katz.

**YEHUDA:&nbsp;** Hello!

**CHUCK:&nbsp;** Now, Yehuda, you were one of the original panelists on the show, but we haven't had you on for a while. Do you want to just remind everybody who you are and what you do?

**YEHUDA:&nbsp;** Sure. A lot of things, but mostly open source stuff, open standard stuff. I would say the big picture is I want programming to be a better, more hospitable place for more people, and I do a lot of things and try to make that happen. I also run a company called Tilde, which has a product called Skylight which has been an enjoyable thing for me to be doing for the past five years or so. Yeah, bunch of stuff. I'm sure we'll get into it.

**CHUCK:** I remember, I think the first time I met you was at a Ruby Conference and you were talking about Rails. You're pretty instrumental in Rails 3. And then a while later, you and Tom Dale got together and did Ember.

**YEHUDA:&nbsp;** Yeah, that's true. So there has been a -- I guess, you guys put things in the show notes but there was this thing by Peter Solnic recently about why I'm leaving Rails and there was a recent follow up about the purpose of abstractions and frameworks or something like that, that I thought was actually a pretty good capstone of the last, however, eight years of my personal life. Because a big part of what I did with Merb and then Rails and then Ember, has been trying to figure out how to make frameworks that don't have all the drawbacks that people normally associate with frameworks.

**CHUCK:&nbsp;** Have you made a lot of headway there because it seems like a lot of the problems are pretty common?

**YEHUDA:&nbsp;** I would say, I have made a lot of headway but a lot of the difficulty, not me personally, of course, there's a lot of people working on various attacks. But a lot of the problems have to do with the fact that frameworks by their very nature are trying to make it so that people who don't already know the problem are able to solve it. So by definition, if you use a framework like Rails or Ember or something like that, there's a whole bunch of problems in the problem space that you don't already know what the answers are, and you want to use a framework so that you don't have to think about them.

Whether or not you should, like people say morally, you should learn it. It's a good thing, and I don't think anybody's going to dispute whether or not it's a good thing to learn things. But as a practical matter, people have [inaudible], people are building things or building products for the most part, and it's not super trivial for people to just stop the universe and learn all of the things. By their very nature, frameworks are trying to make it so that people can be productive building applications so that they know all the things. What that means is that there's going to be some design decisions in the framework that don't necessarily match exactly what you would have expected because of the fact that they are hiding parts of the problem space that you haven't learned yet.

So, I was saying, most people once they've learned the whole problem space are usually able to look at these sort of weird edges and say, "Of course, I see why that works that way," but people who haven't learned the problem yet often look at frameworks and say, "This is too [inaudible]."

I guess, my feeling in general is that the most recent blog post that Peter Solnic wrote which is basically saying, "The right answer is to build opinionated layer on top that's built on top of composed nice little primitives underneath it." I think, that's roughly the right way to do it and just a project to do it right.

**JAMISON:&nbsp;** I think that sounds good what you say, the weird edge cases kind of make sense as you learn more, but I'm having trouble thinking of a specific case and I'm not putting you on the spot, but you have an example of something like that?

**YEHUDA:&nbsp;** I can give a really concrete example but every framework that still exists today is popular [inaudible] but was controversial in the past and that is batching dump updates. The simplest way to build a framework is do roughly the thing [inaudible] it, which is anytime you want to update anything, you just ask the component that is attached to a particular part of the screen to update itself, and it will just do that synchronously.

One of the nice things about that model is that if something goes wrong, the debugger will be stopped right at the point where something went wrong. So you always know when I call this component that render, I'm doing that manually and immediately upon calling it, it will render and I'll see the update and it'll happen synchronously and I'll get exceptions and all that.

The problem with that is that, first of all, it's possible to have contained componency over component that contains other components, and in all modern frameworks that's largely how it works. In background people try to do it but it was a project sometimes.

But second of all, you may have one component that gets updated multiple times because maybe it has inputs from multiple different sources. So, you would really like it, as you would really like for any given user interaction, when a user clicks on a button, you would really like it so that every piece of DOM is only touched at most once and zero times, if that is correct. For example, if I remove a component from the screen and at the same time, the input of some child component gets updated, I would like that child component to get updated touch zero times because it was removed.

In order to do all that, again, every single framework - Ember, React, Angular, Aurelia, all the frameworks that are came out since 2011 or 2012, all do that today. In Angular, the thing that does is called the Digest loop. In Ember, the thing that does it is called the run loop. Angular too has this thing called zones, et cetera. There's a whole bunch of techniques for doing it. But at the end of the day, everybody agrees now that the correct thing is to make sure that you aren't updating the DOM a lot of times per user attraction.

The way to accomplish that is to make users go through in the abstraction layer for [inaudible], or better, you can just touch the DOM willy-nilly whenever you want. There are specific points in time where you're supposed to touch the DOM, there are specific ways in which it's supposed to interact with it. In Ember, Angular and React, the way they're supposed to interact with the DOM by and large is to declare it, so using a templating engine that is designed to work together with your framework.

In case you want to say React is not a templating engine, that's not interesting, but that's interestingly related to what I'm saying. I just mean, the way that you write the markup is not just a bunch of jQuery and it is tightly integrated with the framework, and the benefit of that is that you get the framework guarantees you that the piece of DOM has only touched one time per user interaction.

So, that's an example of something that [inaudible] with me, but the backbone strategy is a lot simpler and it's simpler in one sense and in a sense that's easy to understand. But in terms of what guarantees you get when you write a bigger program, it's actually much more complex.

**JAMISON:&nbsp;** You're saying there's all these things that if you were just writing code from scratch yourself with a naive understanding of the problem, you wouldn't do it and then it would bite you later and these frameworks help avoid it ahead of time, right?

**YEHUDA:&nbsp;** Right, and it's a combination of things like security, performance where maybe if you knew the space very well, you'd be able to do the right thing, and things where it's almost impossible to do it correctly without a God's eye view of the whole program. So, Ember, Angular, and React, all manage the DOM for you because without God's eye view of the whole program, there's actually no way to guarantee the thing that I just said.

It's also the case that I said, I used Ember, Angular, and React in this example because since everyone agrees to it, you cannot really debate whether it's a good idea or not at the same level as other things, but Ember's general philosophy is to take that idea and to apply to more cases like how startup works, where your state is supposed to go, sort of like the way Redux guarantees that your state wasn't into a place. Ember guarantees that your state goes into a particular place, has a storage for add-ons, for the build system.

So, for example, if you have an Emoji add-on, you actually really need to be the case that the images for the Emoji add-on end up in your production payload, and that's something also that Ember place there. So, there's all these things that just by using Ember, you get the right behavior and all of the reasons for that are just trying to solve problems that are very common in a way that composes. So, if you write a big program, you don't have to necessarily know all the details because if you were required to know all of them, you would have messed up somewhere along the way, and the whole program wouldn't have done the right thing.

**JAMISON:&nbsp;** I have a question that's vaguely related to that. One of the things that I've noticed about Ember is that it seems like you place a lot of emphasis on creating these kind of like atomic chunks of stuff and giving them names and then talking about like that. You talk about Glimmer and Fastboot and there's another one that I can't --

**YEHUDA:&nbsp;** Services is another really good example of this where we took a lot of energy to make a name for something that is pretty humdrum concept to begin with.

**JAMISON:&nbsp;** Yeah, what do you see the role of - and that almost seems like, I mean, there's a ton of technical work that goes into implementing all that stuff. But then, there's also this kind of layer of marketing on top of it. Can you talk about how those two things interact in Ember?

**YEHUDA:&nbsp;** Sure. I think, I wouldn't call it marketing --

**JAMISON:&nbsp;** Yeah, marketing kind of sounds like a dirty word. But there's efforts to give good names to --

**YEHUDA:&nbsp;** Yeah, I mean, I don't dislike the term marketing. I think, people shouldn't dislike marketing. I think, people who do marketing work do good work and we should respect them for that. But I'm actually thinking a different point than that which is part of the reason why we have names like Fastboot and Services and Glimmer is to make it easy for the entire ecosystem to always be talking about the same thing. A lot of other frameworks have concepts that everyone talks about all the time. One good example of this will be in React context, is a thing that almost every other framework built on top of React, or every collection of things built on top of React has to think about. But React itself doesn't really try to make it a concept that a lot of users understand or know about or has a coherence foundation. That means it's very difficult for like Redux and React rather to talk to each other about what's happening. Even though, conceptually, they're not necessarily particularly overlapping or solving different problems. It's just that the core foundation doesn't have a good set of terminology around it.

React actually does a really good job. React did a better job than Ember did forever at talking about state in this way. It has state management and [inaudible] and things like that. I think, they did a great job at naming a bunch of things. Ember, of course, like a lot of the stuff that React didn't try to reuse some of the naming or come up with their own, or made sense. An example of this would be "data down, actions up". I think, React has a concept when they give a name too, but I think Ember in general really wants the ecosystem to know how to talk about things so we want people to - when people say Fastboot, they mean a particular thing. They don't just mean Service are rendering, but they mean Service are rendering where you put up the application once and you run things concurrently, and it's part of a larger initiative to improve the boot type performance of Ember and things like that.

I think that's valuable in terms of getting the ecosystem on the same page and making sure that all the add-ons in the world. We have a few thousand add-ons, to make sure all the add-ons are also talking about roughly the same thing.

**JAMISON:&nbsp;** Sure. That makes sense. It's just fascinating to me because it's again, like you said, it's so different from the model and React works are kind of like, there's hive of people, all kind of yelling at each other, and then eventually some name kind of bubbles up and people start using it. And with Ember, it seems like there's just a lot of deliberate effort to give people a handle to talk about and think about.

**YEHUDA:&nbsp;** Yeah, and certainly I think, it's should be clear and this is also true about the Rust Project which I'm a part of. It doesn't make any sense for the core team to just come up with a bunch of names and put our stamp on it. We have pretty involved RC process which now has a section called, "How should we teach it," which gets a lot of community input like hundreds or thousands of responses sometimes to some of these RCs.

A lot of that has to do with the fact that there's a lot of people using these tools and they have their own perspective on what the right name is. Somebody may say, "Well, that's a cool name but dot net already uses that exact name for something else, so you should consider not using it." That may not necessarily be something that I come up with on my own. I think, it's still, I would say somewhat of - I think, deliberate is the right word. It's a deliberative process. It's not a top down process really, but it's a very deliberative process and part of the reason for that is that tools like Ember are around for a long time, and part of the way that we avoid them getting stale and crusty is by making sure we write down our deliberations so that we could come back in a year or two and say, "Hmmm, I wonder why we did that." What was the reason why we came up with that idea, and if we have done a good job of writing down what we did, it's easier to go back in a year or two, and say, "Oh, well, the reason we did that was that IE did this or that thing," and IE we don't care about anymore, so we can't revisit that question.

**CHUCK:&nbsp;** So, would you say that this is a function of making it easier for the community and teams to communicate? Let me frame it in a different way. It seems like it's something that would then affect the way that the community talks to each other. Is that one of the goals? Or is that kind of a secondary effect?

**YEHUDA:&nbsp;** I would say that's probably the main goal. Programming in general is - I mean, this is a cliché, but it's a tool for humans to communicate with each other. It's not really about communicating with a machine. Communicating with machine is easy. Since, it's a tool for humans to communicate with each other, and I've personally lived through a bunch of pretty bad experiences around the primitives that work just fine, but didn't allow humans to communicate well enough, I sort of got from Rails the idea that we could create name concepts.

So, some people think that it's not a good thing that Rails make these name concepts because what if your program doesn't fit into one of the buckets. I think, Rails could have a few more. Certainly, that's why we have services. But I think, by and large, we have to understand that people are spending most of their day every day writing applications, making products. Like for example, I don't spend most of my time working on Ember. I spend most of my time working on Skylight.

When I'm working on Skylight, I have to spend time thinking about when a user clicks on sign up, and they actually already signed up, what is the right answer for that? That is itself a pretty hard question. That's one of a million questions I've asked. I just don't have time for that much primitive thinking. I really do need - there already are high level concepts that say the right answer is this component, the right answer is this Service, the right answer for this is a route.

And obviously, I'm not saying that because I personally don't know how to do that. Since, you can observe that I make the frameworks so obviously I could have done that myself. But when I'm working on Skylight, I really prefer to be thinking about the product. I don't know, I guess it seems like a lot of people really enjoy working on products, and also thinking a lot about functional programming at the same time. Maybe my brain is not big enough for that.

**CHUCK:** &nbsp; Makes sense to me.

**YEHUDA:** &nbsp; It also seems like a lot of people want to me to say things about decorators on Twitter.

**CHUCK:&nbsp;** Do you have feelings about decorators, Yehuda?

**YEHUDA:&nbsp;** I do. I can give you a status update, basically. So, decorators are now it's like the oldest not yet fixed feature in the sense that I submitted the first proposal a very long time ago, a couple of years ago now. It's a big feature. The reason that decorators exist is because in ES5, classes were just [inaudible] that had expressions in them. So, if you wanted to do things that are like decorators, you could just have written a function that takes a function and have a nice day.

That worked out okay. Ember does a lot of that. In addition to Ember doing a lot of that, pretty much everyone does a lot of that, in some form or another. Maybe Ember does aggressive in that but every framework did make something in ES5 class systems that are not easily expressible in ES6.

The reason for that is that ES6 is what was called the max and min class system which basically means that it's just a minimal - it's enough to get consensus, but we really do need to iterate more at it. One of the things that you cannot easily do in ES5 but it's like a nice thing to be able to do, is to be able to say this property is renewable or not renewable, this property is configurable or not configurable, this property is writable or not writable. Those things are quite difficult to do because those things are talking about the proper descriptor, not the value. You can't wrap a function in a value that becomes a non-renewable property. It's a mismatch [inaudible]. So, that's sort of a table setting.

The idea behind decorators is instead of trying to figure out a solution for every combination like, "Oh, we could have a non-renewable keyword. We could have a non-configurable key word. We could have writable keyword. We can try to do combos to these things." Why can't we just make a single system that allows you to say something about the properties and classes that you're creating? That was the decorative proposal. It's gone through a bunch of variations over the last couple of years. Babel and TypeScript implemented the first version as probably listeners know, the feature is used in Angular 2. The first class thing is used in Aurelia, and the React and Ember community use it quite a lot.

It's a feature that's sort of been around as a way of closing a big gap and what the ES6 class system was able to express, ES2015 I should say. But it is also a feature that is controversial because it's basically adding back imperative semantics and [inaudible] semantics, whether you talk about properties into the middle of the highly declarative structure - the structure that was extremely static, and now becomes highly [inaudible]. So, it's just been a controversial thing.

The most recent version of the proposal tries to make the actual structure of it a lot very similar to the object that define property API, and I'm pretty happy with it. I should actually, just close the slides. Actually I could just post them, and then you guys can put them on the show notes. The slides with the new version of the proposal, but I submitted SpecText in [inaudible] in Munich and the committee asked me for more SpecText so I will have more SpecText in [inaudible] and I'm hopeful that at that point, we can discuss it.

There's definitely some debate on the committee about the feature itself, but I think by and large, TypeScript or Babel, and the tremendous amount of usage in the ecosystem has proven the feature as a valuable feature. I mean, it's like anything else, we have to work through on the committee. We have to work for some disagreements on the committee but I think that's fine. I think the committee works well. So, should be a-OK.

**AIMEE:&nbsp;** So, I wanted to back up and ask some questions about the community more because I just recently listened to your first interview on the CodeNewbie Podcast and you said a lot of really great things that I would love other people to hear [inaudible]. So, my question is kind of two part. On the show, you talked about why you're not crazy about the term "Junior Developer" and then you also talked about this curse of knowledge bias. I think, it also goes along with what we're talking about, technically, with how you approach building Ember. I really just kind of wanted you to expand on those things a little bit.

**YEHUDA:&nbsp;** I would definitely recommend that people listen to that podcast because I probably would not be able to go into much detail here as I did there, and I thought I did a reasonable job of explaining my opinion, at least there. Saron was a great interviewer. I'll try to give the high-order bits here.

The reason I'm not in love with the term "junior" is because it implies that there's a set of skills that everybody should think about as being the skills that you need to be a programmer, and then you can rank them in rank order so you can look at a programmer and say, "This programmer is a Junior Programmer, or a Senior Programmer," based on how much skill they have in a particular set of skills that we've decided are the important ones. But in fact almost everybody, like if you're not working at like Google's Search Team or something like that, like working on their algorithm, almost everybody is working on a product and products have a lot of requirements.

Even just from the implementation perspective, there are people who work on like how to [inaudible] things, and I think, even if I said this also in the other podcast, I think, in practice the [inaudible] end up being relatively rare even for people like me who work on that kind of stuff a lot. But if you hit a problem that is best solved using computer science and you choose not to over and over and over again, my experience is that your code base ends up being harder to maintain.

Again, we were talking about 1% of the time. We're talking about a very tiny percentage of the time but if you don't do it thoughtfully, I think, that ends up producing that code base. That's one aspect is computer science but of course there's all these other things like - one thing I noticed when I was a designer in college, not a web designer, but a print designer, is that a lot of people would make college newspapers and they take the text and the text is not actually - there was no padding between the line, the border and the text. I would look at them and I said, "How is it possible that you have put that on a piece of paper and you didn't notice that that was happening by the time it got to the piece of paper."

There's just some people who are good at that. There's some people who can look at a circle and a text and say, "That is vertically aligned. Or there's enough padding between this box and this text and there's some people who visually are good at that, and there's nothing wrong with that either.

There's also people who are really good at writing, people who are really good at expressing what's good about products, people who are really good at talking to their friends about why the product is good, people who are good at Twitter. These are all things that actually go into making an awesome product. It's not that the implementation aspects are the main thing and then being good at Twitter is like a secondary thing. It's actually just a combination of all these skills that make a product good. Typically, there's not one person on the team who was good at all of them. Typically, when you hire - and this is what I was talking about, you want to try to find a mix of people who have the necessary skills.

So, if the way you approach hiring is step one, monotonically rank every single person who enters in terms of "programming skill" and then step two, try to pick the top person on that list, what's going to happen is you're going to end up producing a very homogenous group of people. It is true about homogenous from the diversity perspective, but it's also true from the functional perspective and these things probably overlap. So you end up producing homogenous group of people with homogenous skills and then unsurprisingly, a lot of products end up looking a lot like the implementation. It's quite common that you look at it and you say, "I don't understand why it looks like this," and in your program you say, "Oh, that's because the database tables just sitting right here." That's because they just didn't happen to hire somebody who was good at thinking about that, or they hired that one person out of 10, and that person can't ever make headway convincing anybody else.

So, that's why I don't like Junior. I think there is maybe a sense in which Junior is a thing, but it's so much used to describe this, "What is your programming skill?" And for some definition of programming skill, that I find, I just think it's counterproductive to use it as a concept. I will admit that even I, when I find myself using that terminology, I think a lot of that stuff when I hire, and when I find myself using terminology, I find myself getting sucked into the same mistake. I just think the terminology leads people down at that path. So, that was part one was, junior.

Part two is curse of knowledge. The thing about curse of knowledge is this is like a well-known bias. I'm not making it up. It's just like a thing. What it means is that, people who have a lot of experience on something, don't have a lot of empathy for people who don't have it. I don't mean that in like a fuzzy way, I mean empathy in the definitional sense and ability to put yourself in someone else's shoes.

If somebody files a bug on your project or submits an [inaudible] issue against your product, this is a thing they teach you when you're a customer service rep. I worked in a movie theater for like a couple years in college and it did very little money. But one of the things they taught us was how to be a customer service rep. When someone comes over to you, they gave us a stack of drink coupons and said, "Before anything happens, first try to give them a drink coupon and see if that makes them happy."

When you're a customer service rep, you learn this stuff. You learn what are the rules for dealing with upset people and part of that is a bunch of [inaudible], trying to get to a point of empathy or at least be able to pretend. The curse of knowledge is basically just a bias that causes people to not be able to empathize with people who are new and it causes them to say things like, "You know, I am an open source contributor doing this on my volunteer time, if you don't like it, go use somebody else's product."

Or it causes people to say, "Sorry, this product is not for you." Or, "This product is not for you." That may be true. There are cases where that's true. For example, if somebody is trying to use Ember to build something that was a single component inside an existing Rails application, I would say Ember is probably not for them. But it's usually not the case that Ember is not for you because you happen to not already know JavaScript or HTML or CSS or you happen to [inaudible] or something like that.

I think what ends up happening is that the curse of knowledge causes people to sit, instead of trying to empathize and say, "A person who is submitting this bug or this [inaudible] report is a human being who already uses my product by definition or they would not be filing a bug and if they're having a problem, that probably comes from a real place and they're confused. I should probably try to understand where that's coming from." The curse of knowledge causes us to say, "Well, if they're not going to put in the effort, sorry."

I can give an example from Rust. In Rust, I was the champion of a lifetime allegiant proposal which people should check out Rust for sure. Basically, Rust is awesome because it has its [inaudible] ownership which is the idea that instead of a single object being owned by many other objects, it's always owned by one object at a time. The way that that's represented in Rust is using these special annotations called lifetimes and I wrote a proposal a while back that passed to say, "Let's eliminate like 90%of all those. We can [inaudible]."

There was a bunch of people who said, "Oh, that's good. It was pushed back. When you have to learn it and if you're not willing to learn it, you probably shouldn't be using Rust in the first place."

And I said, "No, people want to use Rust because they're Ruby programmers who are trying to learn systems programming or something like that and we should enable them and we shouldn't necessarily tell people, "Just because you're a Ruby programmer instead of a C++ programmer, you don't belong here."

I think curse of knowledge is an important thing. I think people should always - it's not like, try to identify when you're having it, you're just always having it. The things you should try to identify is the effects. If you can slow down and say, "If a person is filing a bug the person's confused. If a person's upset, person's angry, it's probably coming from a place of being frustrated about already liking your product or using your product," I think that's good. Did that answer your question, Aimee?

**AIMEE:&nbsp;** Yes, thank you. That's awesome.

**YEHUDA:&nbsp;** I gave a much longer enumeration of this in the other podcast. People should definitely check it out.

**AIMEE:&nbsp;** Yep. We'll add a link.

**YEHUDA:&nbsp;** Cool. After that podcast, by the way, I was thinking a lot about it and I was thinking a lot about the fact that a lot of the things I said on the podcast seemed pretty obvious to me but the terminology that we use in tech causes us to think about things the wrong way. I don't know, I don't have anything new on the topic except to say, I think it's probably - it's silly, I think, often to try to insist on a particular terminology in order to control how people think about things. Whether or not it's a good idea, I don't think it works generally. But I think if people really want to think about something in a particular way and the terminology is pretty dumb, I think it's good to try to find, as a group.

I guess this ironically goes back to the earlier question that either AJ or Jamison asked me, "Finding terminology as a community that we can use to talk about --" Not to tell people that they're not allowed to think a certain way, but to tell people who do want to speak a certain way, how to talk about it, actually seems good. And I think we do enough of that in this area.

**AIMEE:&nbsp;** One other thing that I thought was like absolutely awesome, and we talked about it on the Ember show but how many female speakers were at EmberConf? I didn't know if you wanted to speak on that a little bit, I know, I think Jamison mentioned that your wife also helps with that a lot. So, I was just kind of curious what you did to make that so and so.

**YEHUDA:&nbsp;** Sure. I can't take any credit for that at all but I think it's worth talking about it. So yeah, Leah's on the Ember Core team. She is also the CEO of Tilde. Basically, Leah is sort of where - the tweet that I have pinned to my account right now is basically saying people should respect other people's jobs other than programmers, and Leah is sort of the reason I feel that strongly about it. I think, there's a lot of kinds of jobs that people do that are really important that get unheralded and I think a lot of that affects diversity also.

Basically, if you are required to already have a program for 20 years in order to be considered a top tier Ember person, which is not the case, then of course, it's going to be, by definition impossible to fix the problem. I actually sort of realized this a while ago. Imagine if I told you that there is a criteria that has a one-to-one correlation with already being a member of a group and what you're trying to do is you're trying to increase the diversity of that group. You probably want to not want to use that criteria in hiring or any kind of recruitment because that criteria will make it almost impossible to grow the size of the diversity of the group.

However, we do have that criteria, it's called experience and we use it all the time. Basically, if we say you must have 10 years of experience and we have already observed that there's a problem with not being enough people already in the group. Just to be clear, this is not a trivial problem. It is, of course, important to make sure that they're getting a good quality employees but this is also related to the other point I was making about other skills being important.

The point that I'm making here is that experience, as a criteria, whether or not it's a good or bad criteria, it is obviously going to have the result of putting a drag on diversity efforts. If there's a way to make the experience criteria softer, or realize that it's not doing the thing you think it's doing, that's my personal hypothesis - that people place more value on strict experience of a particular kind of skill than they should, but I think that is a problem.

I was a bit rambling but it was basically to say, Ember places the high value on a lot of things that are not specifically about our core programming. Leah is on the core team. She does our events, our marketing, stuff like that. I think those things are highly important.

She did a program called Women Helping Women this year. She wrote a really awesome write up about it on her blog, a medium, I guess. The long and short of it was that she started a year before the conference, and got a bunch of awesome women in the community to agree to do a mentorship program. Then, she did weekly calls with any woman who wanted to call in, to talk about things like what does it feel like to submit a proposal, what kind of feedback are you going to expect, what kinds of proposals are likely to get accepted, or not accepted, why you shouldn't be so nervous about doing it in the first place.

Basically, when the call for papers happened, she just had a bunch of people already ready to go, who felt confident about so many proposals. She also did a call with the core team at some point which was open to everybody but she made sure that the women's program understood that it was happening. It was basically just for people to pitch proposals that the core team people could say, whether they thought were a good idea or not. That call had a pretty big impact in people's ability to submit proposals that would eventually get accepted.

So, I honestly think that people spend a lot of time thinking about this problem, and it's just the [inaudible]. Basically, the things Leah did here are work. They're hard but they're not - I don't want to say they're not interesting. They're interesting. But they're not - you can arrive with that. You can think about them.

I think people want quick fixes, and quick fixes are hard but if you identify what everybody knows what the problems are, the problems are things like there's just a ready systemic sexism. There's already lack of confidence, like there is a bunch of things that we know about. We also, of course, we do first round [inaudible] review although, having done in a bunch of times, I would continue doing it because I think it's a good idea. Women submit better proposals on average. I think, probably because of - I think people feel like if I do them, I should do it right. I basically never had an experience where I'm looking at a batch of proposals, and I'm like, "This proposal is terrible." Basically, I don't think the [inaudible] process, I don't think [inaudible].

Anyway, I'm saying a lot of things here. Some of it will probably get me in trouble but not for any good reason. The long and short of this is just having a program that makes sure that it understands that the problem exists, and tries to make sure that people have a good opportunities, and tries to do the hard work of recruiting people of giving people confidence in the fact that they're good and that their proposals will be good.

It's basically like a numbers thing. And if basically like half of all women who could submit don't because they feel lack of confidence and like 100% of men submit, that you're going to get the expected results. I don't know if any of that was useful.

**AIMEE:&nbsp;** I think it was.

**YEHUDA:&nbsp;** I mean, I think the results speak for themselves as you pointed out earlier. I guess the thing that I feel about all this is I don't feel very confident about anything and I think there's a lot of complexity involved. But I think the problem should be approached as a logistical problem. This problem exists in the world and there are a set of things that we can try to do to address it. And too often, a lot of the conversation is - I'm not saying there's anything wrong with philosophical view, I think it's good to have a philosophical conversation. But too often, the conversation is so much in the philosophical perspective that more efforts like Leah's efforts which are real efforts in the world that have results, aren't really part of the conversation because they're just too tactical. I thought of tactical matters.

**CHUCK:&nbsp;** All right, well, I know that you said that you had some time constraint so we'll go ahead and do some picks.

**YEHUDA:&nbsp;** Yes, sir.

**CHUCK:&nbsp;** Do you want to start us off with picks? That way you can drop off whenever you need to.

**YEHUDA:&nbsp;** I'm happy to do so. So first of all, Leah's book - it's called Event Driven. It's on Leanpub, and it's a book about how to do tactical events. One of these things that has so many details that people - they don't know that they exist. But if you read the book, you'll be probably very surprised. If you're doing any kind of events, like conferences or meet ups or whatever, I think you'll learn a lot out of it, and Leah also updates it at the end of every conference. She basically goes back and does a pretty significant update of things that worked and things that didn't and things like that. I think she would certainly appreciate it if people read it, like pinging her to talk about anything that they're doing and things like that. So, that's a thing.

TypeScript is another thing. I think people shouldn't necessarily fear TypeScript. TypeScript is one of these things where you don't really have to type all the way in to use it. But using it, even a little bit, has a lot of value. Like if you think JSLint gives you value, TypeScript is like JSLint on steroids. If you start using it, even using any of the type system features, but then you can sort of ease your way in slowly and I think people should definitely check it out.

Last pick is there's Rust and Ember RFC process basically. I think people should check out how that works. If you're writing an open source project or involved in an open source project, the way the Rust and Ember RFC process works and I can get into that, they're basically the same thing, and they are really good ways to get communities involved in decisions before they're too late. I think that's good.

**CHUCK:&nbsp;** All right. Aimee, what are your picks?

**AIMEE:&nbsp;** I have two. The first one is something I found - I've been trying to make my pull request. Main process a little bit better, now that I'm using GitHub. So, the first one is just called Pretty Pull Request. Pretty much I'm assuming, just adding some CSS to GitHub UIs so that you can click around and collapse things when you're done looking at them, and things like that.

The other one is a tutorial that I've been going through. It's called Full-Stack Redux and it is by Tero. And he does a lot in the Angular community but this one that goes into React and Redux. It's also test driven so I thought that was really, really, really good, and something a little bit different than the usual people that are putting out content free [inaudible]. That is it for me.

**CHUCK:&nbsp;** All right. AJ, what are your picks?

**AJ:&nbsp;** I'm going to pick The Mountains. I spent some time this weekend out in Bryce Canyon in Utah. It's just nice to be out in the sun and the mountains. See all the red and the blue, maybe a little bit of green here and there. So, if you haven't gotten out of the city, and into the mountains, go do it. Makes your life better.

**CHUCK:&nbsp;** All right. Dave, what are your picks?

**DAVE:&nbsp;** I have two picks for you today. The first one is a feature of my favorite terminal which is a Mac OS X Terminal called iTerm2, and the feature is the quadruple click. Not one, not two, not three, but four clicks, and it starts doing magical text selection which makes it really easy to highlight text on your terminal, like email addresses and host names and things that you traditionally have click, drag, release. You just quadruple click, and you get really cool stuff. That's my first one.

My second pick is the local UtahJS Conference for 2016, which is going to be held this September. We have a really awesome speaker line up this year. We have a new venue. It's bigger and better than before, and we have people coming in from all over the country to speak about all kinds of awesome topics so that will be February 16th. By the time this airs, tickets will probably be on sale. You won't want to miss it because last year we sold out during the early bird, and this year, I expect we will also sell out pretty quickly. In my opinion, this is the best kept secret in the Utah JavaScript Community - The UtahJS Conference. That's all my picks.

**CHUCK:&nbsp;** All right. I just have one pick this week. I've been reading a book. I'm almost done with it, and it was recommended to me by somebody I met a few months ago. The book is called Start With Why, and it is by Simon Sinek. It talks about companies and people who are able to make a difference and sort of create movements among people.

The examples he keeps coming back to are Martin Luther King Jr, Apple Computers and there's one more and I just can't think of it at the moment but anyway -- So the idea is that the companies that really make a difference - the people that really make a difference are people that start with "why", and work from that place of, "This is what I want to create or accomplish," Or, "This is what we're about." Then from there, that drives what they do and how they do it.

It's really making me think about what we're doing with the podcasts and with the conferences and with all the other things that I have going on. I've really been enjoying it. So, I'm looking forward to finishing it probably tonight or tomorrow. But anyway, it's an amazing book.

**YEHUDA:&nbsp;** I agree, by the way. That's one of my favorite books.

**CHUCK:&nbsp;** All right, Yehuda. So, if people want to know what you're up to, follow you on Twitter or anything like that, what do they do?

**YEHUDA:&nbsp;** wycats on Twitter and also anywhere else. And Twitter is basically my primary venue. I very occasionally read blog post but I will always tweet about if I'm going to do that.

**CHUCK:&nbsp;** All right. Sounds good.

**YEHUDA:&nbsp;** Of course, The Skylight Blog. The Skylight Blog is a place to check out what we're doing and it's pretty directly connected to what I'm doing.

**CHUCK:&nbsp;** Awesome. Well, thank you for coming, Yehuda.

**YEHUDA:&nbsp;** No problem.

**CHUCK:&nbsp;** We'll go ahead and wrap this one up, and we'll catch you all next week.

**_[Bandwidth for this segment is provided by CacheFly, the world’s fastest CDN. Deliver your content fast with CacheFly. Visit CacheFly.com to learn more.]_**

**_[Do you wish you could be part of the discussion on JavaScript Jabber? Do you have a burning question for one of our guests? Now you can join the action at our membership forum. You can sign up at JavaScriptJabber.com/Jabber and there you can join discussions with the regular panelists and our guests.]_**


