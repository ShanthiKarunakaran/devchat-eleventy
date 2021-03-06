---
layout: layouts/post.njk
title: >
      215 JSJ ChakraCode with Guarav Seth Live from Microsoft Build 2016
date: 2016-06-08 07:00:54
episode_number: 215
duration: 30:33
audio_url: https://media.devchat.tv/js-jabber/JSJ215BUILDGauravSeth.mp3?rss=true
podcast: js-jabber
tags: 
  - js_jabber
  - podcast
---

This episode was recorded live from The [Microsoft Build Conference](https://build.microsoft.com/) 2016. In this episode we chatted with Gaurav Seth of Microsoft about [ChakraCore](https://github.com/Microsoft/ChakraCore). You can follow him on [Twitter](https://twitter.com/gauravseth), or check out what he’s done over on [GitHub](https://github.com/sethgaurav).&nbsp;Picks
- [TypeScript](https://www.typescriptlang.org/) (Gaurav)
- [Richard Campbell](https://twitter.com/richcampbell) and [Carl Franklin](https://twitter.com/carlfranklin) from [.NETRocks](https://www.dotnetrocks.com/)


### Transcript

**_[This episode is sponsored by Frontend Masters. They have a terrific lineup of live courses you can attend either online or in person. They also have a terrific backlog of courses you can watch including JavaScript the Good Parts, Build Web Applications with Node.js, AngularJS In-Depth, and Advanced JavaScript. You can go check them out at FrontEndMasters.com.]_**

**_[This episode is sponsored by Hired.com. Every week on Hired, they run an auction where over a thousand tech companies in San Francisco, New York, and L.A. bid on JavaScript developers, providing them with salary and equity upfront. The average JavaScript developer gets an average of 5 to 15 introductory offers and an average salary offer of $130,000 a year. Users can either accept an offer and go right into interviewing with the company or deny them without any continuing obligations. It’s totally free for users. And when you’re hired, they also give you a $1,000 bonus as a thank you for using them. But if you use the JavaScript Jabber link, you’ll get a $2,000 bonus instead. Finally, if you’re not looking for a job and know someone who is, you can refer them to Hired and get a $1,337 bonus if they accept a job. Go sign up at Hired.com/JavaScriptJabber.]_**

**_[Let's face it. Bookkeeping is hard and it's not really what you're good at anyway. Bench.co is the online bookkeeping service that pairs you with a team of dedicated bookkeepers who use simple, elegant software to do your bookkeeping for you. Check it out and get your free trial today at Bench.co/JavaScriptJabber for 20% off today. They focus on what matters most and that's why they're there. Once again that's Bench.co/JavaScriptJabber.]_**

**_[This episode is sponsored by Rangle.io. Rangle's been working with Angular 2 for a long time and they are now putting together an eight-hour, 2-day course designed to help Angular developers learn how to write apps in Angular 2. If you're looking to level up your JavaScript and Angular 2 skills then go to Rangle.io/training and click on the link for Angular 2 training. If you're looking for other training in React or JavaScript, they also have that available at Rangle.io/training.]_**

**CHUCK:&nbsp;** Hey everybody, we are back. We're doing another interview here at Build. AJ is here.

**AJ:&nbsp;** Yo, yo, yo, coming at you live from Microsoft Build.

**CHUCK:&nbsp;** Yeah, I know, right? We're also here with Gaurav Seth. He's a Microsoft engineer on Chakra. Is there anything else you want to say [inaudible] introduction?

**GAURAV:&nbsp;** Yeah, I love to be on your show. Thanks. Hello everyone. I work on both Chakra as well as TypeScript projects. So, happy to talk to you guys today.

**CHUCK:&nbsp;** Awesome. Yeah, and I know that we've had a few people come on both Adventures in Angular and JavaScript Jabber to talk about TypeScript.

**GAURAV:&nbsp;** Sure.

**CHUCK:&nbsp;** And I think we're going to be talking to Anders later on about TypeScript. So, I think we're going to…

**GAURAV:&nbsp;** [Inaudible] is on the list.

**CHUCK:&nbsp;** Yeah.

**GAURAV:&nbsp;** Fantastic.

**CHUCK:** &nbsp; We're just going to focus on Chakra.

**GAURAV:&nbsp;** Yeah, that would be awesome, yes.

**CHUCK:&nbsp;** Yeah. So, it's really interesting as we've been paying attention to JavaScript appearing on different platforms. For example, you have JavaScriptCore basically enabled on iOS. And so, you can write native or native-ish apps in JavaScript.

**GAURAV:&nbsp;** Yup, yup.

**CHUCK:&nbsp;** V8 is becoming much more of a thing with Node.js.

**GAURAV:&nbsp;** Right.

**CHUCK:&nbsp;** And so, when we see Microsoft backing Node.js…

**GAURAV:&nbsp;** Right.

**CHUCK:&nbsp;** So, where does Chakra fit in with all this? We see it in IE and Edge.

**GAURAV:&nbsp;** Right.

**CHUCK:&nbsp;** But are there other…

**GAURAV:&nbsp;** So, there are… yes. You know, let me start giving you a brief intro. So, we started Chakra a few years back. And Chakra was the JavaScript engine that we initially started, I think it was the IE 9 time frame that we started working on this new JavaScript engine. Since then we really evolved Chakra over a period of time. Now, today Chakra not only supports Microsoft Edge but starting Windows 8 whenever we went to the Store-based applications and now you know we're [still doing] those applications, Chakra's been powering all hosted web applications and JavaScript-based web applications that you can get from the store. So, that part, Chakra was already there. It's just the same web platform that you're using.

But over and beyond that there are a lot of services now that are also actually using Chakra. For example, Azure's document DB uses Chakra to provide the JavaScript programmability for their procs and stuff. There's Outlook.com that uses Chakra. There's Cortana that is using Chakra. And very recently, I think this was in January, we announced in December but in January we actually open source the core of the Chakra engine which we are calling ChakraCore. And one of the big things [amongst others] [inaudible] on why we did this is we really want to take Chakra cross-platform, not restrict it to Windows only. And that also opens up the door of having another runtime or another JavaScript engine being available in Node.js. So, one of the things we are trying to work with the Node folks along with folks from Google is to see how we can actually abstract out a neutral VM API surface for Node such that multiple engines can start plugging into Node.

**CHUCK:&nbsp;** Oh, that would be cool.

**GAURAV:&nbsp;** So, if you look at it even though a lot of people know about Chakra only thinking it's only Edge or IE, it is actually a lot more spread out than just being used in those two scenarios.

**CHUCK:&nbsp;** Gotcha. So, I want to just clarify a couple of things. One is that you're saying that some of these apps are actually written in Chakra. So, you can write Windows apps in JavaScript?

**GAURAV:&nbsp;** Yes. You can write Windows apps in JavaScript.

**CHUCK:&nbsp;** And we're not talking like Electron and Node. We're talking Chakra?

**GAURAV:&nbsp;** Yes.

**CHUCK:&nbsp;** And can you write… so, now I'm going to throw a whole bunch of platforms at you and you can say yes or now. Windows Phone?

**GAURAV:&nbsp;** Yes.

**CHUCK:&nbsp;** Xbox.

**GAURAV:&nbsp;** Yes.

**CHUCK:&nbsp;** No kidding.

**GAURAV:&nbsp;** Yes.

**CHUCK:&nbsp;** That's awesome.

**GAURAV:&nbsp;** Yes. So basically, it's the whole motto of universal Windows platform, is you can write apps in any language that you want and they are supported across the entire device family that is supported by Windows, right?

**CHUCK:&nbsp;** Right.

**GAURAV:&nbsp;** I mean, as a device family. So wherever Windows runs, you can write your application, your Store-based applications using those universal Windows platform APIs and JavaScript is an option there. And all of that uses Chakra.

**CHUCK:&nbsp;** Right. So…

**AJ:&nbsp;** So, well two things. One, Mozilla had a project where they tried to abstract Node and that just fell by the wayside.

**GAURAV:&nbsp;** Yes.

**AJ:&nbsp;** So, are you guys committed to seeing this through and helping that funding, like it's going to happen? We will have Node?

**GAURAV:&nbsp;** Yes, we are a hundred percent committed to make that happen.

**AJ:&nbsp;** Okay.

**GAURAV:&nbsp;** And we've been talking to a lot of people. I think everybody has a different point of view. I think when Mozilla started doing this that was way early when Node was really, really young. And I think at some point in time they lost a couple of people who were actually working on that effort. And they didn't support it beyond that point.

**AJ:&nbsp;** Well, and before Microsoft got involved in Node it probably wasn't abstracted enough…

**GAURAV:&nbsp;** Yes.

**AJ:&nbsp;** To really take that on.

**GAURAV:&nbsp;** Yes, exactly.

**AJ:&nbsp;** And it's been Microsoft's massaging of getting those critical pieces separated that's…

**GAURAV:&nbsp;** That is so true. And then that's… I mean, one of the things for us is we are a hundred percent committed to help Node succeed. The biggest thing we see here why Chakra would help Node is because having more than one engine being available in the Node ecosystem is really going to help the Node ecosystem growth. It is going to help take Node to different, newer platforms or different platforms or different places. Different people can actually optimize the developer experiences, the tools that are available, based on multiple engines that are being available today. Everything is just constricted or restrained to, “Hey, here's the stack and you can only work against that stack” and it's all about opening that thing up. So…

**AJ:&nbsp;** So, it kind of makes Node almost like a browser in the sense that you have a common standard API set but different backends…

**GAURAV:&nbsp;** That is [correct].

**AJ:&nbsp;** And different specific features.

**GAURAV:&nbsp;** Yeah, that is correct. When you say different specific features, I think this is one of the misconceptions that a lot of people carry. In terms of JavaScript engines today, when you talk about the language functionality that is supported in most of the JavaScript engines, we are almost on par. A lot of developers worry that just like the browser of the 90s, late 90s, where there were so many browser-specific code that you have to write if you're targeting one browser versus the other browser. I think a big thing to clarify in that scope is a lot of those browser-specific features were not really in the JavaScript engines but they were mostly in for example the rendering engines, the layout engines, et cetera which developers had to work through. Over the last five to six years we've actually been working with the ECMAScript committee, TC39 committee, and ECMAScript to create the standardized test suite for JavaScript called test262.

And today if you look at it, almost all browsers… just let me take an example. ES 5 support, everybody passes 99.9% of that test suite, which basically tells you that JavaScript implementations from a language perspective are fairly [inaudible] today. So, developers would not run into those issues. Now that said, if there's a cutting edge new feature that is actually going to [light] up in say one of the future versions of JavaScript, right? Let's talk about ES 2017. Let’s assume async functions or some people call it async/await is going to light up. One engine is going to do it before the other engine. But it's very hard to imagine that developers would be taking dependencies on such cutting edge features. And again, it goes…

**AJ:&nbsp;** Except that they do right now.

**GAURAV:&nbsp;** No, and again…

**CHUCK:&nbsp;** Yeah, some do.

**GAURAV:&nbsp;** Yeah, some do. And again, the thing is even in those features it's not that the VM implementers are very far behind. One VM has implemented it but the other virtual machine is going to implement it years later. It's just a matter of months that we are looking at. And all of those, like I think with evergreen browsers becoming a reality, everybody first puts things out in experimental mode and then brings it in.

**AJ:** And that's what I meant by specific features.

**GAURAV:&nbsp;** Yes.

**AJ:&nbsp;** I didn't mean necessarily that you're trying to diverge but rather like right now Node has command line flags.

**GAURAV:&nbsp;** Yup.

**AJ:&nbsp;** That if you pass it you'll get experimental features that may or may not…

**GAURAV:&nbsp;** Yes.

**AJ:&nbsp;** Make it into a future version of stable [inaudible].

**GAURAV:&nbsp;** Yes, exactly. And I think from Chakra's perspective what we have been trying to do is we created a shim which makes Node think that it's talking to the V8 engine itself. But that shim actually talks to Chakra instead of V8. And our goal has been to light up the exact same experience that devs have today when they're using Node which is working with the V8 engine. One of the things I can take as an example here is one of the things our team has been working on is providing the same amount of debugging support that Node developers are used to. So today, if you go open Visual Studio Code you can actually start debugging Node. We've been hearing from developers it's a great experience debugging Node in VS Code.

And over the last three months since we took Chakra open source, one of the things we announced was we're going to be working on these modern debugging APIs that are going to be… we can make them inter-operable with other implementations and take them across tool chains. And we now have made such progress that now we have such APIs where you take Node running with V8, you can debug it with VS Code. You replace it, you have Node running with Chakra, it just works. And that's the thing that we are trying to work towards is, “Hey, what is that neutral API surface that we got to look at so that from a Node development perspective it remains very easy for Node developers while others in the ecosystem can come and differentiate?”

Our goal here is not at all… I mean I want to be very clear, our goal here is not at all to try and replace V8 in Node because I think having more than one engine is going to be great for Node. And our plan is to just help Node grow its ecosystem.

**CHUCK:&nbsp;** So, you've said two things that kind of make me wonder a little bit. So, the first one is you basically said that it would be a good thing for Node to be able to run V8 or Chakra or maybe something else.

**GAURAV:&nbsp;** Yes.

**CHUCK:&nbsp;** The flip side of that is that you also talked about how both V8 and Chakra are mostly interchangeable. So, I'm wondering what would be the advantage then of having Chakra on Node?

**GAURAV:&nbsp;** Right.

**CHUCK:&nbsp;** Other than maybe being able to debug something on a system side runtime instead of having to fire up a browser. I'm trying to figure out, okay, so what circumstances would lead me to say, “Okay, I want my Node to be running Chakra instead of V8.”

**GAURAV:&nbsp;** Great question. And I think there are multiple things here. Let me start listing a few of those examples so that you can think about those advantages. Each JavaScript engine that exists today, you talk about V8, Chakra, SpiderMonkey, JS Core, they optimize things for specific scenarios. When I say optimize…

**CHUCK:&nbsp;** Oh yeah, that makes sense.

**GAURAV:** &nbsp; [Inaudible] performance, right? And as a developer when you're writing a particular application in the browser you end up testing, where is my application actually running fast or running slow? So, we have different performance characteristics. V8 has different performance characteristics. And for specific scenarios, a specific engine might do better. So, that's one way where developers, having choice for developers is great.

**CHUCK:&nbsp;** That makes sense.

**GAURAV:&nbsp;** Another such example is in terms of the architectures of the engine, that itself is different. For example, Chakra has always supported an interpreter from the get go. We have a multi-phased pipeline where we start with the interpreter and then we compile code and start executing code. That's really useful for very early, very, very quick startups. V8 today does not have that. And having an interpreter basically implies that you can actually port an interpreter to any other platform very, very quickly because you don't have to rewrite the JIT compiler which is all written. Of course, both of them are in native code. But it takes a lot more time to take a JIT compiler and make it portable or make it work on another platform. Whereas if you have an interpreter it can go to another platform very, very quickly.

I'm kind of hypothesizing here, but let's assume that you had to take Chakra to PowerPC. So, the amount of work that is needed to take just the interpreter piece to the PowerPC is much, much smaller. It is much easier to go there. However, taking the full JIT to that point is a much more involved effort. So, that's how we are imagining that this ecosystem will grow.

**AJ:&nbsp;** So, if I wanted Node on a MIPS router that will probably never happen with V8 Node. But with Chakra Node it might be more possible?

**GAURAV:&nbsp;** Possibly. An interpreter is a very easy thing to port.

**CHUCK:&nbsp;** Gotcha. So…

**GAURAV:&nbsp;** That said, I should also say I think the V8 team is also working on an interpreter. So, once that becomes a reality probably in perspective that is doable. These are just some examples. And I would also call out, sorry I'm cutting you but…

**CHUCK:&nbsp;** No, go ahead.

**GAURAV:&nbsp;** One third thing that I love for developers is as the JavaScript language has been evolving from a standardization perspective and we work with ECMA when we work in TC39.

**CHUCK:&nbsp;** Right.

**GAURAV:&nbsp;** Most of the standardization typically happens from a web [inaudible] perspective, like the web browser perspective. And as TC39 has progress, ECMA has progress, now we've defined stages of, “Hey, we would want…” like there's stage zero, stage one, stage two, stage three, and stage four for different proposals that we have. And to get any feature, to get to stage four which means that it is going to come into the specification you need more than one VM implementation to be there. So, Node today has only one VM which is running there. At least having two VMs, there are two implementers who can also think about features from a server-side perspective instead of just thinking about them.

**AJ:&nbsp;** And that would be so nice because I've wondered so many times why Node seems to get ignored. It's almost like it's the red-headed stepchild of the community sometimes because the community should be together but it seems they fight.

**GAURAV:&nbsp;** I completely [inaudible]

**AJ:&nbsp;** They want to ignore each other. Node wants to specifically sometimes do things not the browser way just to be incompatible and vice versa. Browser implementers, I can't remember what it was but I remember during the standardization process Node has already solved many problems and some of the standards that are written for HTML5 that came well after Node like buffers…

**GAURAV:&nbsp;** Yes, yes.

**AJ:** Completely incompatible implementations. Like, why?

**GAURAV:&nbsp;** Yup. And I think that's one of the big things that I am looking at when I think about it as a big advantage for developers. Because then you're thinking about it from both the perspectives across more than one virtual machine, or one JavaScript engine.

**AJ:&nbsp;** That's good.

**CHUCK:&nbsp;** Yeah, that makes sense. I can also see that some people may dismiss Node by basically categorizing it as V8 and then saying, “Well, if it works in Chrome” but in reality that's not the way that it actually works.

**GAURAV:&nbsp;** Yes.

**CHUCK:&nbsp;** So yeah, it's really, really interesting. I'm curious as you talked about the standards. And so, we've got the ES 5 standard and now we have the ES 2015 standard. So, where is Chakra with implementing that? And maybe ES 2016, 2017, some of the standards that are now coming down the line, where are you at with implementing those features and how do you decide and how do you make that all work?

**GAURAV:&nbsp;** Yeah. Great question. So, I think ever since… when it was released it was still ES 6 before it became ES 2015. So, Chakra has been actually leading in the implementation of ES 6 or ES 2015. ES 2015, I always get confused in the year…

**CHUCK:&nbsp;** Yeah, [laughs]

**GAURAV:&nbsp;** That you connect. So, we've been leading. And today I think one of the things we will be doing soon in the previews to come is we are actually now, we've already implemented almost all of the ES 7 or ES 2016 feature set. So for example, the array includes is there, the exponentiation operator is there. And we already are also supporting some of the more future stuff. For example with have experimental support for [Assembly] JS. We already have experimental support for async functions which we would like to enable by default. So we are, being ahead in the whole standardization process is like a two-pronged thing. It has its pros and cons. When you do things early from an engineering perspective at times the spec changes and you have to throw away that work, right?

**CHUCK:&nbsp;** Yeah.

**GAURAV:&nbsp;** But the thing that it actually really enables and the reason we want to be at the forefront of picking up those features and implementing it is that it actually gets implementers feedback back into the standardization process. So, as part of the whole ES 6 evolution or ES 2015 evolution there were so many instances where we implemented that feature set, ran it across the web, got some data back to the committee and say, “Hey, this particular functionality or capability, if we do it this way is going to break the web in this way.”

**CHUCK:&nbsp;** Right.

**GAURAV:&nbsp;** And there was, I don't remember the exact specific API but it was like an old version of one of the mobile frameworks, one of the popular mobile JavaScript frameworks had the same name of that API being available. There was a clashing functionality difference. So, anybody who had taken a dependency on that old version was broken, even though the new version had updated but the web does not move ahead.

**CHUCK:&nbsp;** [Laughs] That's the truth.

**GAURAV:&nbsp;** That's the thing I would say. So, it comes with its own pros and cons. But I always look at it and we feel that the pros really over-weigh the cons. Being ahead, being early helps get that implementation feedback back into the standardization process to help evolve the spec in a better way.

**CHUCK:&nbsp;** So, what's coming down the line with Chakra now?

**GAURAV:&nbsp;** So, I think one of the biggest things as I said, we went open source in January. It's called ChakraCore. ChakraCore is similar… it's the same exact core that Chakra shares with a couple of differences.

**CHUCK:&nbsp;** That makes me want to cheer.

**GAURAV:&nbsp;** Yes.

**CHUCK:&nbsp;** I love it when these projects that people are using are out there that can make a difference, make a statement.

**GAURAV:&nbsp;** Right.

**CHUCK:&nbsp;** They go open source and say “Hey look. We appreciate the community and we want the community to be involved.”

**GAURAV:&nbsp;** Yes. And for ChakraCore one of the biggest things on our agenda, our road map is published publicly on our GitHub repo but one of the biggest things we are tracking is taking ChakraCore cross-platform. We are actually going to start with Ubuntu. We've actually started making very good progress on that. And we now have our GC actually running on Ubuntu which is great. In the last three months we've made such good progress. So, that's number one. Taking Chakra cross-platform is number one on our [inaudible] map.

Number two is working with the Node Foundation and along with Google and V8 team, to see how we can actually advance Node to have more than one VM or one JavaScript engine to work with Node. How do we actually evolve that architecture? That's one of the next things that is, it's the second thing on our agenda.

Of course with JavaScript engines the one thing that is always there is keep improving from a performance perspective. Keep improving from a security perspective. Keep improving from a language support perspective. So, that will always be there. That's number three. I will [club] that in one bucket.

And number four I would say is one of the big things we did was between Chakra and ChakraCore our takeaway was we took back the debugging APIs which Chakra supported because they were Windows specific. And given that cross-platform was our goal, we wanted to have these new modern APIs. So, we've actually now made a lot of substantial progress in those modern APIs, modern debugging APIs that I was telling you. That you can now take VS Code and just run Node with Chakra there. And the goal is to bring them to mainline and ship them out. So, those are the four big pillars I would say that we are working on.

**CHUCK:&nbsp;** Nice.

**AJ:&nbsp;** So, one you said people concurrently use Chakra in applications. And so, when I think Chakra versus Chakra Node, V8 versus V8 Node, the difference between V8 Node, I can run a V8 shell but I don't get any I/O. I only get the JavaScript engine. Is that what we're talking about with Chakra? It's just the JavaScript engine. You don't get any of the I/O. You'd need to program that in C#.

**GAURAV:&nbsp;** Yup, that's correct.

**CHUCK:&nbsp;** Can I pile on with that?

**GAURAV:&nbsp;** Yes.

**CHUCK:&nbsp;** You said that Outlook.com or whatever, was written in Chakra.

**GAURAV:&nbsp;** I mean they're using Chakra. They're hosting Chakra for some of the work that they do.

**CHUCK:&nbsp;** Okay. So, is that what AJ as how they're using it?

**GAURAV:&nbsp;** Yes, yes. Basically…

**AJ:&nbsp;** So, it's a .NET framework is interfacing with it and…

**GAURAV:&nbsp;** It could be .NET. It could be C, C++, it could be anything that you want to interface with.

**AJ:&nbsp;** Well, what is Chakra?

**GAURAV:&nbsp;** Chakra is our JavaScript engine.

**AJ:&nbsp;** No, I mean like the language that it's written in.

**GAURAV:&nbsp;** Oh, Chakra is written in C/C++.

**AJ:&nbsp;** Oh, okay. I thought it was…

**GAURAV:&nbsp;** No, no. It's all written in C/C++.

**AJ:&nbsp;** I thought it was .NET. Okay, okay.

**GAURAV:&nbsp;** Yeah. So, it can interact with any languages though. There's always, you can do marshalling across different languages and work across it.

**CHUCK:&nbsp;** Yeah.

**GAURAV:** But for example, the big use case is really any application that needs scriptability for example NoSQL stores which is what Azure DocumentDB as a service is. It's just a NoSQL store. You want to have JavaScript programmability. How do you get that JavaScript programmability? You need to have a JavaScript engine that runs the JavaScript that developers write.

**CHUCK:&nbsp;** Right.

**GAURAV:&nbsp;** And so, it's Chakra that is powering that service as an example.

**AJ:&nbsp;** Okay. And then so, you're talking about how you're trying to make the API interface the same as V8 so that tools that are currently built around Node with V8 will work just as well. But you're also targeting performance. So, is there any conflict there where your shims decrease performance? Or is it all negligible? Or is it arbitrary?

**GAURAV:&nbsp;** So, I think that's a great question. And I would say that from the preliminary results that we are seeing, it's a mix. There are certain cases where we are faster, we are much faster. There are certain cases where we still need to catch up. I think this was what we really wanted to do as a first step was to actually write the whole thing so that we can believe ourselves that first it is doable. And the first step is now that we have crossed that first step, now comes the second step of, “Okay, let's make this [mode] performant as well. All of those things can be made performant. So, that's just a matter of time is all I think. But eventually yes. If it's a mixed bag it's not like I can say it's one way or the other. There are certain things that definitely perform better. There are certain that don't.

**CHUCK:&nbsp;** Yeah, my experience… so, listeners to the show know that I have come mostly from a Ruby background.

**GAURAV:&nbsp;** Okay.

**CHUCK:&nbsp;** But four or five years ago, a lot of the conferences would have at least one or two talks comparing different Ruby VMs.

**GAURAV:&nbsp;** Right.

**CHUCK:&nbsp;** So, they would have the timestamps or where they measure the speed and they would basically yeah, it would be “So, this Ruby implementation is way faster than this one doing this” and then the next slide would be “And it's not so much faster doing this.”

**GAURAV:&nbsp;** Right, right.

**CHUCK:** Or “It's much slower doing it” and so it just depends on the way it was implemented and how things came together.

**GAURAV:&nbsp;** Yes.

**CHUCK:&nbsp;** And then what they could optimize afterwards.

**GAURAV:** Yup. And that's why like I was saying in the beginning, each JavaScript engine or each JavaScript VM is optimized for a specific set of scenarios. When we started working on Chakra our goal was really to look at the real-world web and go optimize for that.

**CHUCK:&nbsp;** Yeah.

**GAURAV:&nbsp;** And that was one of the reasons we said, “Hey, even in terms of our architectural pipeline we need to have an interpreter and a JIT compiler right from the very beginning.” Because how it works is as soon as JavaScript code hits the browser, let's say you navigate to a particular page right? It pumps JavaScript code. And an interpreter can immediately start running it. It does not need to compile it. It does not need to wait for that. But a JIT compiler, to produce optimized code it will take time to compile that code and actually run it.

**AJ:&nbsp;** So, I've noticed on Raspberry Pi when I run Node, oh it can be so slow. And same thing if you're using an Android phone, their processors on Android phones are sub-par because I don't think the browsers get implement to use multiple cores. So, visiting web pages on Android phones is slower. And I think that's in part due to that ramp up time that it has.

**GAURAV:&nbsp;** It possibly is. I am not an expert in that.

**AJ:&nbsp;** Okay.

**GAURAV:&nbsp;** I've not looked at how they perform on the Android phones. I have looked at them from a desktop perspective [inaudible].

**AJ:&nbsp;** Well, but from your perspective the wait time between when it gets data, when it gets JavaScript text…

**GAURAV:&nbsp;** Right, right.

**AJ:&nbsp;** And when it starts running the JavaScript text, it's pretty much no wait time?

**GAURAV:&nbsp;** You have to imagine that it's a pipeline where you have steps of work to be done. So, let's go through it.

**AJ:&nbsp;** Okay.

**GAURAV:&nbsp;** The JavaScript engines get the JavaScript code. The first step is that the engines parse that code, generate the ASTs. And then which Chakra we actually with the AST we just generate bytecode that we start executing. If you have a JIT compiler you would take those ASTs. You would probably let them, give them to the compiler. The compiler is going to actually compiler them and generate the actual…

**AJ:&nbsp;** Yes.

**GAURAV:** Native code that runs.

**AJ:&nbsp;** Okay.

**GAURAV:&nbsp;** In Chakra we start running with the bytecode but give that to the concurrent threads that we have. So, we take advantage of concurrency that is available on multiple cores that are available on your hardware. And this is true across any devices like be it the Raspberry Pi, be it phones…

**AJ:&nbsp;** Okay.

**GAURAV:&nbsp;** Be it desktops. So, we basically compile the JavaScript in the background and as soon as a function is ready, we swap that function [entry point] in the interpreter. So, the next time you run you're actually running the jitted code instead of the interpreted code.

**AJ:&nbsp;** Okay, that sounds really, really…

**CHUCK:&nbsp;** Yeah.

**AJ:&nbsp;** Cool. Because I try to track down where some of my problems were on starting an application.

**GAURAV:&nbsp;** Sure.

**AJ:&nbsp;** And it's Node's vm.compile.

**GAURAV:&nbsp;** Yes.

**AJ:&nbsp;** That is…

**GAURAV:&nbsp;** Yes. So, it does take time. It's not free.

**AJ:&nbsp;** Yeah.

**CHUCK:&nbsp;** Yeah.

**GAURAV:&nbsp;** So, there are these steps that you have to go through. Some of these steps you'll have to go through even when you're interpreting. But with interpreting you can just start running very quickly.

**CHUCK:&nbsp;** Yeah.

**AJ:&nbsp;** Yeah. That sounds awesome.

**CHUCK:&nbsp;** Now, I know that you wanted to get to this other session. So, we'll go ahead and wind down. One thing that we do as part of our show though before we let you go is we do what are called picks. And basically it's just, some people pick TV shows. Some people pick coding tools. It can be anything that you're just into right now.

**GAURAV:&nbsp;** Right.

**CHUCK:&nbsp;** So, what is it that you're into right now? Just one or two things.

**GAURAV:&nbsp;** Yeah, great question. I think right now I'm pretty much into TypeScript and learning TypeScript. I've been with the JavaScript world for a very long time and I kind of had this thing like JavaScript is awesome. And I just started learning TypeScript and to be honest, it's amazingly powerful. When it comes to the productivity aspect of how productive you can be in writing a JavaScript application it is immensely, immensely helpful with the feature sets. And of course given that it is a pure superset of JavaScript that helps. The ramp up time to start learning it is very less. And then as you start converting… so, that's one of the things I've recently started learning. And I would definitely recommend everyone to go check it out if you would love to. Because it is supported across any editor, any IDE of your choice. It's not only limited to Visual Studio or VS Code. It's available for [inaudible], vim, Sublime, Atom. Anything that you love using, you can go try it out. And it really helps with catching the issues, maintaining very good code velocity or the productivity of the team. And it really helps in terms of productivity from that respect.

**CHUCK:&nbsp;** Awesome. And then if people want to check out ChakraCore or find out more about Chakra and where it's implemented and how they can start experimenting with it, where do they go?

**GAURAV:&nbsp;** I would say start with the ChakraCore GitHub repo. That's the best place for you to get started.

**CHUCK:&nbsp;** Awesome. And then are you on Twitter or GitHub where people can follow you?

**GAURAV:** Yes, I am on Twitter.

**CHUCK:&nbsp;** Okay, what's your handle?

**GAURAV:&nbsp;** My handle is @gauravseth. That's G-A-U-R-A-V-S-E-T-H.

**CHUCK:&nbsp;** Okay. Awesome.

**GAURAV:&nbsp;** Yeah.

**CHUCK:&nbsp;** And then just to wrap up I also am just going to kind of pick Richard Campbell and Carl Franklin from '.NET Rocks!' for inviting us out. It's been fun. We've gotten to talk to a whole bunch of really interesting people. And this has just been a great experience. So, thank you and thanks also to them for setting all this up.

**GAURAV:&nbsp;** Oh, thanks for having me over. And it was great talking to both of you guys.

**_[Bandwidth for this segment is provided by CacheFly, the world’s fastest CDN. Deliver your content fast with CacheFly. Visit CacheFly.com to learn more.]_**

**_[Do you wish you could be part of the discussion on JavaScript Jabber? Do you have a burning question for one of our guests? Now you can join the action at our membership forum. You can sign up at JavaScriptJabber.com/Jabber and there you can join discussions with the regular panelists and our guests.]_**


