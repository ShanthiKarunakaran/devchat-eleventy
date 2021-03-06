---
layout: layouts/post.njk
title: >
      259 RR Pair Programming with Jay Bobo of Pair Columbus
date: 2016-05-11 07:00:31
episode_number: 259
duration: 01:01:59
audio_url: https://media.devchat.tv/ruby-rogues/RR259JayBobo.mp3?rss=true 
podcast: ruby-rogues
tags: 
  - ruby_rogues
  - podcast
---

01:59 - Jay Bobo Introduction

- [Twitter](https://twitter.com/jaybobo) 
- [GitHub](https://github.com/jaybobo)
- [Pair Columbus](http://paircolumbus.org/)

04:20 - [Pair Columbus](http://paircolumbus.org/)

07:28 - Meeting Formats

- [OWASP](https://www.owasp.org/index.php/Main_Page) 
- [Challenges](http://paircolumbus.org/challenges/) 

11:21 - Organization

- [@cowboyd Tweet](https://twitter.com/cowboyd/status/723174606027124737) 

14:57 - Attendee Experience Levels

15:56 - Matching People

18:04 - “Three Amigos”

19:33 - [Pair Programming](https://en.wikipedia.org/wiki/Pair_programming) and Communication/Chemistry

- [Dan North - Embracing uncertainty: why you should and why you won’t](http://www.ustream.tv/recorded/86148915) 
- [Jay Bobo: Do u even pair bro?](http://slides.com/goodproduce/do-u-even-pair-bro) &nbsp;(Slides)

31:50 - Dealing with Difficulties During Pair Programming

34:50 - Useful Strategies For Pairing Related to Hiring

- [Conway’s Law](https://en.wikipedia.org/wiki/Conway's_law)
- [What's Wrong With Ruby's Object Model (And Why That's a Good Thing) by David Brady](https://www.youtube.com/watch?v=LmtcDFnOYj4) 

54:14 - More Episodes on Pair Programming

- [Ruby Rogues Episode #026: Pair Programming](https://devchat.tv/ruby-rogues/026-rr-pair-programming) 
- [Ruby Rogues Episode #126: Remote Pair Programming with Sam Livingston-Gray](https://devchat.tv/ruby-rogues/126-rr-remote-pair-programming-with-sam-livingston-gray) 
Picks[Jarvis Desk](http://www.ergodepot.com/Jarvis_Desk_s/566.htm) (Sam)[What Do Women Want At Hackathons? NASA Has A List](http://www.fastcompany.com/3059036/most-creative-people/what-do-women-want-at-hackathons-nasa-has-a-list) (Sam)[Dan North - Embracing uncertainty: why you should and why you won’t](http://www.ustream.tv/recorded/86148915) (Jessica)[Common Ground and Coordination in Joint Activity](http://jeffreymbradshaw.net/publications/Common_Ground_Single.pdf) (Jessica)[Apprenticeship Patterns: Guidance for the Aspiring Software Craftsman](http://chimera.labs.oreilly.com/books/1234000001813/index.html) (Jay)[Zach Holman: How to Deploy Software](https://zachholman.com/posts/deploying-software) (Jay)[Patricio Gonzalez Vivo: The Book of Shaders](http://patriciogonzalezvivo.com/2015/thebookofshaders/) (Jay)[Black Mamba Hot Sauce by CaJohn's](http://www.amazon.com/Black-Mamba-Hot-Sauce-CaJohns/dp/B001I4TC6A) (David)

### Transcript

 **DAVID:&nbsp;** There's a magic editing fairy and she has a magic wand. And she makes all of us sound about 30 IQ points smarter than we actually are.

**_[This episode is sponsored by Hired.com. Every week on hired they run an auction where over a thousand tech companies in San Francisco, New York, and L.A. bid on Ruby developers providing them with salary and equity upfront. The average Ruby developer gets an average of 5 to 15 introductory offers and an average salary offer of $130,000 a year. Users can either accept an offer and go right into interviewing with a company or deny them without any continuing obligations. It's totally free for users. And when you're hired, they give you a $1,000 signing bonus as a thank you for using them. But if you use the Ruby Rogues link, you'll get a $2,000 instead. Finally, if you're not looking for a job but know someone who is, you can refer them to Hired and get a $1,337 bonus if they accept the job. Go sign up at Hired.com/RubyRogues.]_**

**_[I'm excited to tell you about a new sponsor to the show, Rollbar. One of the frustrating things about being a developer is dealing with errors. Ugh. Relying on users to report errors, digging through log files to debug issues, or a million alerts flooding your inbox ruining your day. With Rollbar's full-stack error monitoring, you get the context and insights and control you need to find and fix bugs faster. It's easy to install. You could start tracking production errors and deployments in eight minutes or less, or automatically create new issues in GitHub, JIRA, Pivotal Tracker, et cetera. They have a special offer for Ruby Rogues listeners. Go to Rollbar.com/RubyRogues to sign up and get the bootstrap plan free for 90 days. That's 300,000 errors tracked free. Give Rollbar a try today. Go to Rollbar.com/RubyRogues.]_**

**DAVID:&nbsp;** Hey, hello and welcome to episode 259 of the Ruby Rogues. Today on our panel we have Sam Livingston-Gray.

**SAM:&nbsp;** This is not my beautiful house.

**DAVID:&nbsp;** We have Jessica Kerr.

**JESSICA:&nbsp;** Good morning.

**DAVID:&nbsp;** I'm the guest host today, David Brady. And because I'm guest hosting I don't do my intro joke. I'm just going to screw it up and I'm already well underway. And today we have a special guest who is Jay Bobo.

**JAY:&nbsp;** Hi. Thanks for having me.

**DAVID:&nbsp;** You bet. Welcome. So Jay, why don't you tell us a little bit about yourself?

**JAY:&nbsp;** Sure. I am a developer at CoverMyMeds. I've been doing a lot of training stuff, so I handle all of our trainings for new hires I guess over the last six to nine months. And I'm also one of the organizers of Pair Columbus here I Central Ohio.

**DAVID:&nbsp;** Now, in the pre-call I tried to say you are the organizer of Pair Columbus and you had like an allergic reaction. It was awesome.

**JAY:&nbsp;** Yeah. I mean, my parents beat it into me as a kid that I should really speak in the royal we in those cases.

**DAVID:&nbsp;** [Laughs]

**JAY:&nbsp;** So, when working in the community or anything where there's a group I really like to try to emphasize the work that other people were doing, because if it was just me by myself then it would be a complete failure. [Laughs]

**DAVID:&nbsp;** Okay. So, you organized Pair Columbus and you're very, very good at it is what I'm hearing.

**JAY:&nbsp;** No.

[Laughter]

**JESSICA:&nbsp;** [Inaudible] a sense of organization isn't something you do alone.

**DAVID:&nbsp;** Yeah.

**JAY:&nbsp;** Yeah, definitely. I don't think we do anything alone, right? If you think about it from friendship, to the teams that we work in at work, to going out and having a good time. It's always some sort of group experience even if you're organizing a meetup. So yeah, I'd agree. So yeah, as a part of that if it's okay, I'd definitely like to shout out…

**DAVID:&nbsp;** [Absolutely]

**JAY:** Some of the organizers of Pair Columbus. Brian Lees, Susan [inaudible], Vasanth Pappu, those two guys have definitely been there since the beginning. They've helped out in a tremendous amount of ways. And the list is extremely long so, I won't go on and on. But definitely those two guys have been really, really helpful. And [inaudible] the support of the community. We wouldn't be able to do any of the stuff that we've done without the support of the local Columbus Ruby Brigade and CoverMyMeds is one of our sponsors.

**DAVID:&nbsp;** Vasanth and Brian, nobody knows really where they work. I hear it's another small health [informatics]…

**JAY:&nbsp;** [Laughs]

**DAVID:&nbsp;** Company in Columbus, Ohio that you and I work at.

**JAY:&nbsp;** Yeah, yeah. That's what I hear. [Laughs]

**DAVID:&nbsp;** Yeah, yeah.

**JAY:&nbsp;** That's what I hear.

**DAVID:&nbsp;** Yeah.

**SAM:&nbsp;** So, it's an organized conspiracy.

**DAVID:&nbsp;** Yes.

**JAY:&nbsp;** Yeah, it feels that way sometimes.

**DAVID:&nbsp;** Yeah. So, what is Pair Columbus? Do you grow a pair of [inaudible]?

**JAY:&nbsp;** We've thought about it. No, Pair Columbus is just the emphasis is pair programming. I don't even know how the name came together. It just happened. It started…

**DAVID:&nbsp;** I guess I would say it's because you're doing pair programming and you're in Columbus?

**JAY:&nbsp;** Well yeah, we didn't really put a lot of effort into [inaudible].

**DAVID:&nbsp;** Oh my god, woo! I'm just [floating] [inaudible].

**JAY:&nbsp;** Like, I'm [inaudible] pair, added Columbus. But I felt like we could have been… like, it's not as cool as Ruby Rogues in my opinion, right? But yeah, we started actually at the Columbus Ruby Brigade when I had moved back to Central Ohio from Chicago. I [inaudible] after the meetup and said, “Hey, who wants to get together and pair on some stuff? Mentoring new people, whatever?” And eight people grabbed me afterwards and we started meeting at the library. And we were meeting weekly. And then a bunch of other people wanted to come, which is kind of crazy because we meet at Saturday mornings. [Laughs]

**JESSICA:&nbsp;** Whoa.

**DAVID:&nbsp;** [Inaudible] cartoons?

**JESSICA:&nbsp;** Whoa.

**JAY:&nbsp;** Yeah, exactly. We [conflict] with Saturday morning cartoons, which I guess are still a thing? I don't know.

**JESSICA:&nbsp;** Oh.

**DAVID:&nbsp;** No, actually they're not. For those of you under the age of 30, cartoons used to only be on Saturday morning. There was not a network.

**JESSICA:&nbsp;** Yeah, they used to have a fixed time and you had to watch them the same time as everybody else. And you couldn't pause them.

**DAVID:&nbsp;** Yep. And Dungeons and Dragons was on it 4:30 in the morning.

**JAY:&nbsp;** Yeah, it was insane. Yeah. Yeah, you had to get up early for that stuff. But anyway, so we conflict with someone's cartoon watching. I'm sure someone watches cartoons Saturday morning. But yeah, so it just got bigger and a lot of other people started to come by. And we had experienced developers and we had new people and some folks who have never written code before. So, it's been this really interesting exercise of trying to make a meetup work for people of different backgrounds and different experiences which is definitely difficult. But we've pivoted almost every meetup [laughs] to make it better.

**JESSICA:&nbsp;** Really?

**JAY:&nbsp;** And we've had a number of different tools in place. So, this may, obviously this month, the meetup will be completely different than it was from last month. So, I think that's also why the community has been strong over the two years that we've been around. It's just because you really never know what may happen. But it's always helpful. It's always really cool. And you actually write code. That's the other big thing. The last month someone came up to me and they said, “You know why I like coming to this thing even though it's in the morning on a Saturday?”

**DAVID:&nbsp;** [Chuckles]

**JAY:&nbsp;** “It's because we actually write code as opposed to just complaining about our jobs.”

[Laughter]

**DAVID:&nbsp;** Wow.

**JAY:&nbsp;** And that's it, right? So, I think that's really cool that it's fun. You're going to get together with some people. You're going to meet new people. It's a rather diverse. We have a very inclusive environment. And it's fun. It's fun. We get up and we say, “Hey, did you learn anything today?” and someone says, “Yeah, a little bit.” “Did you build anything today?” “No.” “Okay, so what broke?”

**DAVID:&nbsp;** [Laughs]

**JAY:&nbsp;** [Then you just] come up and you're like, “I ran into this error and I couldn't figure it out,” or, “I accomplished nothing whatsoever in trying to learn this new thing.” So, it's fun. It's definitely a fun space.

**DAVID:&nbsp;** That's awesome.

**JESSICA:&nbsp;** But Jay, tell me about what was the format of the meeting in April?

**JAY:&nbsp;** Okay. Oh my goodness. I have to try to remember. I have to look at my list.

**JESSICA:&nbsp;** Or you could really tell me any general meeting.

**DAVID:&nbsp;** Yeah. We have no way of spot-checking you on this.

**JAY:&nbsp;** [Laughs]

**JESSICA:&nbsp;** Yeah, yeah, yeah. Yeah, you [inaudible].

**JAY:&nbsp;** Yeah. So, the basic format for Pair Columbus, it changes from meetup to meetup. We meet monthly now. Just recently within the last three months we are now the newest chapter of NodeSchool which is an international organization. They don't have an official designation.

**DAVID:&nbsp;** Oh, wow.

**JAY:&nbsp;** But there's a NodeSchool in Santiago. We were admitted to NodeSchool which is all about Node.js and JavaScript about I think the same time that Havana, Cuba was. So, that's really cool. But it covers everything. You could learn about shaders. You could learn about Node in itself. You can learn about functional JavaScript, if there's such a thing I guess, all these functional concepts. You can learn about shaders and gaming and all types of different things.

**DAVID:&nbsp;** That's cool.

**JAY:&nbsp;** So, that's one of the things that we do. And then we come up with themes. So, a theme might be, I think our last theme was like a mini hackathon. So, we gave everyone a list of APIs and we'd say, “Hey, build something interesting with these APIs. You have two hours in which to do it. And then at the end of two hours, come up and present it.” So, that's one thing. Or we might have a thing that's something like technical interviews. It really depends on our audience. They'll come to us and say, “Hey, you guys should do this.” We had one last year that went over really, really well. It was a capture the flag sort of intro to OAuth training which was really, really great. You had to access this application and then get access to an email account which led to a Twitter to you defacing a Twitter account which led to pulling up, finding a person's GitHub account, accessing a private repository, then finding out about other stuff like endpoints that you may not have known about in the application. It was all types of wacky stuff.

**DAVID:&nbsp;** Holy crap, why have I not been coming to this? Holy freaking crap.

**JAY:&nbsp;** [Laughs]

**JESSICA:&nbsp;** Yeah, that's like…

**SAM:&nbsp;** Well for one thing Dave, you're in Utah.

**JESSICA:&nbsp;** So, you get to learn about authorization and not hate your day at the same time?

**JAY:&nbsp;** [Laughs]

**JESSICA:&nbsp;** I've definitely never achieved that before.

**JAY:&nbsp;** Yeah, it was definitely pretty cool. I think our attendees had a lot of fun with that one. So, but yeah, no it could be anything. And we tried to really keep it light and free-flowing just so that everyone continues to have fun. And you know, because sometimes you just get in a rut, right? Like I know I'm going to get there and it's going to be some lightning talk and then I'm going to grab a beer and then we're going to stand around a bar. So, we just try to like, you know… but that stuff is cool, too. I'm not trying to drag on other meetups. I think people definitely need that social outlet. But we do recognize that a lot of people are looking at trying to get better or [inaudible] trying to become better craftspeople while at the exact same time they want to meet new people over something that you really enjoy. And so, that's what our focus is at Pair Columbus.

**JESSICA:&nbsp;** And on Saturday you still have your brain.

**JAY:&nbsp;** Yeah. Well…

**JESSICA:&nbsp;** Unlike evenings.

**JAY:&nbsp;** Yeah.

**JESSICA:&nbsp;** Weekday evenings I can go to the meetups. But programming at them is sometimes hard.

**DAVID:&nbsp;** Okay, moment of truth. How many Pair Columbus's have you shown up to hungover, Jay?

**JAY:&nbsp;** Oh, that's a great question. So…

**DAVID:&nbsp;** [Laughs]

**JAY:&nbsp;** That's a really…

**DAVID:&nbsp;** Actually that's an awful question. I was mostly kidding.

[Laughter]

**JAY:&nbsp;** Well, I have to say that nine. I'll say nine. But yeah no, it's tough because sometimes I haven't… I've definitely procrastinated, like I need something the night before. I'm pretty sure the capture the flag one I stayed up, I think I deployed that thing into Heroku at four o'clock in the morning before. So [laughs].

**DAVID:&nbsp;** That is awesome. And so, you guys sound almost as decentralized in organization and topics as the name of the meetup suggests. That you don't get together and say, “We're going to do this.”

**JAY:&nbsp;** Yeah.

**DAVID:&nbsp;** And it's the obligatory joke. If you guys are NodeSchool, then the topics are endless. You could do a whole our on why threading is hard. You could do a whole other hour on why threading is dumb. You could do a whole other hour on why threading is evil. The topics really are just endless.

**JAY:&nbsp;** Yeah. I definitely have to agree with that. And we've attempted to become more language agnostic over time.

**DAVID:&nbsp;** Mmhmm.

**JAY:&nbsp;** At the exact same time, we started… I say that we are the children of Columbus Ruby Brigade. And if you look at some of our challenges which are pooled from all over the place, a lot of that stuff is done in Ruby. But we just recognize that we wanted to be a place that brought people together and to go on those different, go along those different pathways that you just mentioned. Like we didn't want to be locked to something besides the fact of our model is bringing people together and then we're not going to be tied down to saying, “We're only going to work in a certain language. And if you want to learn, I don't know, Elixir or something go somewhere else.” And so, NodeSchool just made sense because of they already had a really awesome community, international community. Different coding challenges are baked in different languages. And it just made sense because if I had to say, our focus is definitely web development. So, we can't do that without JavaScript obviously. I guess…

**DAVID:&nbsp;** Yeah.

**JAY:&nbsp;** You know.

**SAM:&nbsp;** Speak for yourself, mister.

**JAY:&nbsp;** [Laughs] So, you know.

**DAVID:&nbsp;** Hello and welcome to episode 259 of JavaScript Jabber. Today our guest is…

**JAY:&nbsp;** [Laughs] So you know, just saying that as we're just about bringing people together for the benefit of the community and that's what it's about. So, wherever the community wants to go, we're willing to go there too.

**DAVID:&nbsp;** Charlie Lowell made a really great tweet. He's @cowboyd on Twitter and he tweeted a couple of weeks ago that, it was about Ember rather than about Node but he said, “Ember is not a framework. It's a community. And until you understand that, you will never understand the framework.” And I wrote back to him and I said, “So, what you're saying is if it bleeds, we can kill it?” And he didn't really agree with that, but yeah. So, I like this notion that Node, that you guys can champion Node without excluding other languages. If somebody wants to show up and do something completely different you can say, “Hey, that's fine.” But if somebody needs a reason to come to Pair Columbus beyond just pairing you can say, “Well hey, you want to sharpen up your Node skills?”

**JAY:&nbsp;** Yeah.

**DAVID:&nbsp;** “We're a NodeSchool.” That's awesome.

**JAY:&nbsp;** Yeah. And in addition to other languages, too. So, recently we established a relationship with the Columbus PHP group. And it's pretty much about taking all of our Ruby stuff and our Rails stuff and our Sinatra stuff and just attempting to make our place more welcome. You can't say, “Oh, we have this inclusive environment that's open to people from different backgrounds,” and so on and so forth without giving people an opportunity to connect with you in, I want to say like a language like a programming language, but just without having some sort of common ground there. And also to give them an ability to go in different directions. We don't have a thing where it's like, “Well you know, I want to learn Go or something. And because you guys don't really deal with that sort of stuff then I'm going to stop coming to Pair Columbus.” So, I think that was really our big focus is to be more people-centered and without a focus on frameworks and languages.

**SAM:&nbsp;** So Jay, I'm curious about the make-up of Pair Columbus. Do you get a lot of beginners, a lot of people who've used six languages? And what's the overlap between your group and say the Columbus Ruby Brigade.

**JAY:&nbsp;** That's a great question. It's a really great question. I would say that on a given day, that beginners may be anywhere from, I don't know, I'm going to say 10 to maybe 30% of our attendees. And it's broken up just the way you mentioned it. We have some people who say, “Hey, I don't know, I've been working in Perl or something for a long time,” or something. “I haven't done anything else or something. I don't know. “I've been working Java forever. I want to learn something new.” So, we have those sorts of folks. And then there are the people that say, “I just heard about this thing in a class. I go to Ohio State University and I'm here. What should I do next? What should I do post-graduation?” It's all types of stuff.

**JESSICA:&nbsp;** How do you match people up in pairs?

**JAY:&nbsp;** That's another awesome question. So, when we first started it involved me and a whiteboard and lots of running around. [Laughs] But that's changed. Thank god that changed. So, what we've done is we've built a Meteor app that we utilize. And we have people come in and they access the application. And they enter in their email address or name, what they're there to learn and what they're there to teach. So, it's not just this one-way sort of thing. You come in and say, “Hey, I'm just trying to get better at technical interviews,” or something. There's that. And then you throw in your experience. And we just keep that in mind. What we've learned is that we try to come up with an overall theme and that theme is broken into two pieces. So, one will say here's something that's just for novices and here's something that's for people with a little bit more experience.

So, I think I mentioned earlier about working with the APIs thing that we did. I believe that was last month. And the way that actually ended up working out was that the more experienced folks worked with APIs. The other group worked on object-oriented programming, building just really basic command line scripts. So, it gives people an opportunity to, if they're beginners, to either sit in on something so to do like a three amigos thing. Or what we'll do is if they're really, really, really, really new, and that for them even seem like… I try to sit down with each person to say, “Hey, how do you feel? What do you think about this?” and that's not something that they're open to, then we'll sit and we'll pair them together on something like Codecademy or Code School or Zed Shaw's 'Learn the Hard Way'. Maybe they'll work through some of that stuff.

So, that's great for people who have to Pair Columbus for the first time. And so then, what happens is they come the next month and they say “I went through all of 'Learn Ruby the Hard Way' and I feel awesome. And now I'm ready to do this other thing.” So, it's amazing to people graduate through us. Like we're not a bootcamp or any of that other sort of stuff. But it's amazing to see people who say, “I have three months of programming underneath my belt. I just finished Code School,” and they're now working as a developer somewhere. So, that's amazing.

**DAVID:&nbsp;** Awesome.

**JAY:&nbsp;** So, [inaudible].

**DAVID:&nbsp;** Jay, you mentioned a term that I think has some currency outside of CoverMyMeds but it's definitely lingua franca inside the company. You said three amigos. Do you want to give a definition to that? Because we're not just pretending to be Steve Martin and Chevy Chase.

**JAY:&nbsp;** [Laughs]

**DAVID:&nbsp;** And I think Martin Short?

**JAY:&nbsp;** Yeah. In the case of Pair Columbus, we just look at it as shadowing a pair. Three amigos in other places may be a pair and a test engineer or a pair and an infrastructure developer, DevOps person, I don't know what the titles are.

**DAVID:&nbsp;** Or a business advocate.

**JAY:&nbsp;** Yeah.

**DAVID:&nbsp;** Yeah.

**JAY:&nbsp;** Yeah, or something along those lines. But yeah, for us that's what it is. We try to avoid that because we do this whole talk on Pair Programming 101 that I find hilarious but I guess no one finds any of my jokes funny. [Laughs] So we try to lead with that.

**SAM:&nbsp;** As long as you entertain, that's all that matters.

**JAY:&nbsp;** Depending upon how many new people are there, we'll [inaudible], “Here's programming, pair programming. Here are your responsibilities as a driver. Here are your responsibilities as a navigator,” which is cool, which is cool.&nbsp; We've definitely had experienced people. I've had very experienced people come in and say, “Hey, what is this pair programming thing that you guys are doing? Can you explain it to me? We've done it this way,” and I'm like, “Yeah. I guess. [Laughs] We can give you some advice.” We're just some crazy people that get together and write code. I don't know.

**JESSICA:&nbsp;** [Inaudible]

**JAY:&nbsp;** I [inaudible] our advice.

**JESSICA:&nbsp;** I think you said something important there. [Inaudible] people who are experienced programmers come to find out what pairing is. And…

**JAY:&nbsp;** Yeah.

**JESSICA:&nbsp;** I think part…

**SAM:&nbsp;** Almost like it's a separate skill or something.

**JESSICA:&nbsp;** Exactly. And it is a separate skill and it's hard to recognize that. And then when you try to do it and you don't enjoy it, well you're probably doing it wrong. At least if at first you don't enjoy it, try pairing with someone experienced in pairing, even if they're not experienced in what you're doing. Because yeah, it really is a different way of working. Last week I was at Craft Conf in Budapest. And Dan North did a keynote. And he had a really interesting point. He was talking about the koan of what's the sound of one-hand clapping. And what he gets personally out of that koan is that the clap is a property of the system. It's not a property of either hand but of the relationship between them. And pair programming is like that. Something comes out of pair programming that does not come out of programming by yourself.

**JAY:&nbsp;** Yeah. I would definitely agree. There is so much to be learned from it, if you want. And that's what we talk about in the slides. I have to find the slides for you all on it. And you know, there's something to be said for having to attempt to express your ideas in your native tongue to your partner without having your hands on the keyboard. I think it helps make… being a better communicator is… being a good communicator is great for working in a team. And who doesn't really work in a team? And then also too, I think it requires you to do some more self-reflection about who you are as a person. This is outside of programming, about how much empathy do you have for an individual. And you recognize that hey, you are capable of making the same sort of mistakes. I think it helps as far as remove… it doesn't remove ego but it helps suppress it, I feel like. Especially if you're willing to take some effort to be a good partner, a pair programmer. It's like, it's almost being a good friend, or just a good life partner. [Laughs] you know?

**JESSICA:&nbsp;** You're doing more than learning a new way of coding. You get to be in someone's head when you're coding with them. And you get to learn a new way of thinking, especially if they're a lot different from you. That's the best. If you could be present in that moment and really listen.

**JAY:&nbsp;** Oh yeah.

**SAM:&nbsp;** Yeah.

**JAY:&nbsp;** Yeah, definitely. I would agree wholeheartedly.

**SAM:&nbsp;** Yeah, my favorite part of pair programming, especially with a new person, is that moment where I'm surprised. They just used a command line trick or a key binding that I don't know. But it's something really cool and so, I ask about that.

**JAY:&nbsp;** Yeah.

**SAM:&nbsp;** Or even better, I'm trying to railroad us through this thing and then somebody says, “Wait, why don't you just do it this other way?” And I stop and I'm like, “But that would mess up the next three things I had planned and… oh wait, you're right. That is much better.” [Chuckles]

**DAVID:&nbsp;** Mmhmm. Mmhmm.

**JESSICA:&nbsp;** Yeah, yeah or when they type something wrong and you're like, “What?” But if you just kind of go with it for a few minutes then you're like, “Oh. I wouldn't have thought of that.”

**JAY:&nbsp;** Right.

**DAVID:&nbsp;** Yeah. A lot of people think being the navigator is you're being the spell check. You just typed 'pirnter' there instead of printer, kind of. That method call is not going to work because you mistyped it.

**JESSICA:&nbsp;** That's important in Ruby.

**DAVID:&nbsp;** And to be fair… No, you can hook method missing to make it catch pirnter and redirect it to printer. But [Laughs]

**JAY:&nbsp;** Point for David.

**DAVID:&nbsp;** [Inaudible] into the call. Jessica just put her face in her hands.

**JESSICA:&nbsp;** [Laughs]

**DAVID:&nbsp;** That was awesome.

[Laughter]

**DAVID:&nbsp;** And to be fair, you really do a lot of spell checking. But yes, you do end up doing this navigation checking. And I have a possible tangent question. Does somebody have a follow-up before I switch a little bit?

**SAM:&nbsp;** Yes, I did.

**JESSICA:&nbsp;** I think the purpose of the pair, or the navigator is to look at things at a slightly higher level, in addition to picking up…

**DAVID:&nbsp;** Yeah.

**JESSICA:&nbsp;** That little detail. But to remember why we're doing this at all… and you know how sometimes you're trying to code something or worse, debug something, and you get way down in the weeds and it's just immensely harder than you thought it was but you keep going and then your pair says, “Wait, why are we doing this again?”

**DAVID:&nbsp;** Mmhmm.

**JESSICA:&nbsp;** “Maybe it isn't worth it. Maybe we should just back up.” And you're like, “Oh, okay. Yeah.” And you know you would have spent another six hours beating your head against it if somebody hadn't said, “Wait a minute. Wait a minute. Why?”

**JAY:&nbsp;** Guilty.

**SAM:&nbsp;** Yeah.

**DAVID:&nbsp;** Yeah. I wrote out this big, long thing to the XP mailing list back when Agile was called XP before Microsoft released an operating system that took over that namespace. When Agile was called Extreme Programming, I wrote this big, long thing about testing in C++ about how you do the setup, you do the tear-down, da-da-da-da-da, da-da-da-da-da. And I posted 300 lines of boilerplate that made everything just so plain and calm and easy. And Ron Jeffries, bless his heart, is not known for being a kind soul or for suffering fools. And he changed my career by actually stepping out of character and being kind and empathetic. And he just wrote back one sentence and he said, “David, does it have to hurt this much? -Ron.” And [blugh], I'm like, “Maybe not.” So yeah, it's great to have somebody at that higher level.

**JAY:&nbsp;** Yeah.

**SAM:&nbsp;** I was going to mention that one thing I notice as somebody with more experience in programming and pairing both, when I'm pairing especially with somebody who's really new, my instinct when they start to typo something or they mess up the arguments to a method, my instinct is to correct them immediately.

**DAVID:&nbsp;** Mmhmm.

**SAM:&nbsp;** But I actually have to stomp on that, because I think it's probably more useful as an experienced pair to give people the space to make those mistakes and to learn what happens when you make those mistakes. I realize it's a little bit arrogant even to phrase it that way, because sometimes people, you think that somebody's making a mistake and you actually learn this other thing new, too. But, yeah.

**DAVID:&nbsp;** Yeah, yeah.

**JESSICA:&nbsp;** But balance that. Yes, let them get the error message and let them find it. But if they don't find it right away, then show them what that error message means.

**JAY:&nbsp;** Oh yeah. Absolutely give them hints.

**DAVID:&nbsp;** Mmhmm.

**JESSICA:&nbsp;** And then they've learned something. But don't, this happened to me once, let them go the entire afternoon struggling with something that you happen to know how to do…

**DAVID:&nbsp;** Yeah.

**JESSICA:&nbsp;** Just to show them at the very end of the day how stupid they were and that you knew this all along. And then they go to the bathroom and cry for 10 minutes. Okay, that happened to me.

**JAY:&nbsp;** That happened to me, too.

**DAVID:&nbsp;** They had that coming. I was the guy who did it, sorry. No. [Chuckles] So, I have to give a huge shout-out right now to DJ Destefano. He works at CoverMyMeds. He's my pair, partner right now. We do kind of monogamous long-term pairing at CMM. I'm trying to push us more towards a little more promiscuous pairing. But right now he is my assigned marital partner if you will in terms of pair programming. And he's new. He's got less than a year of Ruby under his belt. And he and I, I know that pairing between a very senior and a very junior person is supposed to be awful, that it's supposed to be… all the studies have shown that that's the version of pairing that just has the… there's such an impedance mismatch between the ability to communicate your thoughts. And it's just not there with DJ and I.

We have hit this magical point where… we all know that if you pair program you're going to get about one person's work done in a day. But that level of work will be three or five times higher quality than one person could have produced that one person's worth of work in a day. DJ and I just click so well and so fast we are getting all of his work done and all of my work done in a single work day. And it's the three to five times quality. There's something magical there. I don't know why. I'm so…

**JESSICA:&nbsp;** You all have chemistry.

**DAVID:&nbsp;** That's probably true and I probably would kiss him but he has a beard.

**JESSICA:&nbsp;** [Laughs]

**DAVID:&nbsp;** It's kind of [inaudible].

**JAY:&nbsp;** [Laughs]

**DAVID:&nbsp;** But if you're into kissing guys with beards, it's cool. But I'm not. So anyway, my point is that there's something magical going on there that I don't understand which fascinates me endlessly. And to speak to Jessica's point, we had two times where it went both ways.

Last week we were in the middle of a thing and DJ was like, “I'm trying to make this thing work and I'm having trouble with it and I want to go this,” and that's the first sign of a good pair is we're talking. He's actually talking out what he's trying to do. He was the one driving but he was talking out what he was trying to do. And he's like, “I can't seem to make this work.” And I threw out a leader question or a leader statement which was, “I see what you're trying to do. And I have an idea. I have a quick solution that will work. However, you are on the right track to discovering that idea. So, if you'll forgive me I'd like to just follow along with you as you develop this idea.” And he went, “Heck yeah.” And so, we spent half an hour solving something that I could have just banged out in five minutes and he would have been none the wiser. And the next time he ran into that situation he would have the same dilemma. We spent half an hour on it.

**JESSICA:** And you negotiated that upfront?

**DAVID:&nbsp;** Upfront, yes. I told him.

**JESSICA:&nbsp;** That's awesome.

**DAVID:&nbsp;** I told him I see a shortcut but I can't take you through that shortcut without you missing all of the scenery. And it was the middle of the week. We had some time. Did I mention we're very productive the other… we had some time coming to us. And he's like, “I want to learn this.” And I really view the senior person's role in a job is not to make sure that the code gets written but rather to make sure that the junior partner gets educated so that they can write that code…

**JAY:&nbsp;** Yes.

**DAVID:&nbsp;** Next time.

**JESSICA:&nbsp;** But that's so amazing that you talked about it.

**JAY:&nbsp;** Yeah.

**JESSICA:&nbsp;** Because that kind of going meta and being able to talk about what you're doing abstractly is so important in communication and in improving because what if he was really tired that day?

**DAVID:&nbsp;** Right.

**JESSICA:&nbsp;** And he knew he wouldn't be able to catch the thing and it would have been better to learn it later. Then he could have said, “No, I just really want to feel productive right now.”

**DAVID:&nbsp;** Mmhmm.

**JESSICA:&nbsp;** “Please show me. We'll come back and learn that thing later.”

**DAVID:&nbsp;** Absolutely. And yesterday morning we had the same situation happen and we made the opposite decision. We were deploying code to production. And we deployed. We did a single-node roll out into production and things were going wrong. And it wasn't… our functional specs weren't passing and we were trying to figure out why. And DJ started down a little bit of a rat hole and I started to do the thing of, “Okay, well I see a solution here but I want to show you the way.” And then I stopped myself in mid-sentence and I said, “You know what, DJ? We're deploying to production. How about I just jump us ahead to this and then we can circle back if we want?” and he went, “Thank you. Yes, please.”

**JAY:&nbsp;** Hmm.

**DAVID:&nbsp;** Now, you said chemistry Jessica. And I can sum up his chemistry in one word and that's humility. I can say, “I know the answer,” and it comes out about like that.

**JESSICA:&nbsp;** [Laughs]

**DAVID:&nbsp;** I try to be a little more empathetic. [Chuckles]

**JAY:&nbsp;** [Laughs]

**DAVID:&nbsp;** I try not to stress I know the answer. I don't say, “And not you,” that kind of thing. No, my point is I try not to be a jerk. When I say, “I see a way through this,” I'm not saying that there's no other way through it and that you're dumb for not knowing it. So, I try to lay this out there as an option. And he picks it up with humility. And he has the safety to tell me, “Yes, let's jump ahead,” or, “Yes, let's…” There's no “no” there. There are two yeses. He can just say, “Yes, let's jump ahead,” or, “Yes, let's take the long way and then I will know the route through these mountains next time.” And the next time we hit this problem he can teleport straight to the end.

**JAY:&nbsp;** Yeah.

**SAM:&nbsp;** Yeah, you said something…

**JAY:&nbsp;** Yeah. I think that communication, that communication is really, really important. I think it doesn't have anything to do with necessarily experience. But I think about just being a good teammate. And it's not even just in pairing, right? That happens in pairing but it also can happen between engineering and business. We have our own priorities for stuff. It just happens all the time in life. But pairing I think is a good exercise. I've learned a lot about myself in undergoing it and saying, “Hey.” I'm attempting to look outside of myself at my relationship with someone else and say, “Okay alright, how am I responding to this person? Am I communicating clearly? Am I taking into consideration what's important to them?” Just [inaudible] of that stuff. And I think that you all have hit it right on the head. And that's what our focus is for Pair Columbus.

**DAVID:&nbsp;** That is awesome. So Jay, let me put you on the spot a little bit. Horror stories. Wait, wait, wait, wait. No, let me give you the ability to say yes here.

**JAY:&nbsp;** Pair programming horror stories? [I've got some.] [Laughs]

**DAVID:&nbsp;** Yeah. Can you share with us how we might deal with some difficulties that you might have observed in pair programming? [Chuckles]

**JAY:&nbsp;** Oh yeah. I think it's very similar to just other war stories you have when working with other people. I've seen it with other people. I've seen two guys about to come to blows while pairing. That was interesting.

**DAVID:&nbsp;** Okay. So, one rule. No fighting.

**JAY:&nbsp;** Yeah. That was [inaudible]. I don't even know. I don't remember exactly what it was over. But it was something trivial. They were working on something and they were both very, very…

**JESSICA:&nbsp;** Was it tabs and spaces?

**JAY:&nbsp;** Yeah, I'm sure it's probably what it was. [Laughs] But they had very strong opinions about how to solve one thing. And they were I guess what I call cowboy-like coders. They pair but it's like, “Let me have the laptop,” or, “Let me have the keyboard,” sort of thing. And I think they just rubbed each other wrong. I've seen that sort of thing happen. And I've had situations where when working on a team, with a team of developers, one person takes this very sort of, I guess it's this type A personality. I'm not sure. But has this opinion and feels as if the group should follow their opinion and is not considering anyone else. And I've definitely had to come to a person. “Hey listen. You've been voted off the island but we still love you.”

**DAVID:&nbsp;** [Laughs]

**JAY:&nbsp;** I've [inaudible]. And I feel like there were definitely times where I could have been a better pair. And I've had to work against my own ego and my own insecurities as well.

**DAVID:&nbsp;** I've had days when my partner and I have just needed to hug it out until he couldn't breathe.

[Laughter]

**DAVID:&nbsp;** To be fair, if it was tabs and spaces and one partner was advocating both tabs and spaces, violence was merited there.

**JAY:&nbsp;** [Laughs]

**SAM:&nbsp;** That person gets [defenestrated].

**JESSICA:&nbsp;** Sometimes not [inaudible] say yes [inaudible].

**JAY:&nbsp;** [Laughs]

**DAVID:&nbsp;** Yes, yes. There are three options here. There's yes and, and another yes and, and then there's no effing way.

**JAY:&nbsp;** [Chuckles]

**JESSICA:&nbsp;** Sam has a word of the day.

**SAM:&nbsp;** Oh, yes. I misheard Jay when he said the word personality. It sounded to me like pair-sonality and we were talking about pairing. So yeah, I don't have a definition for it. But I will throw that out [inaudible].

**DAVID:&nbsp;** That's awesome. That is awesome.

**JAY:&nbsp;** It [should] be a thing. It's a book. I think you three should work to put a book together about pair-sonality.

**DAVID:&nbsp;** Yeah.

**JAY:&nbsp;** Yeah.

**DAVID:** The last time the Ruby Rogues tried to write a book together, well we're still writing it. Actually…

**SAM:&nbsp;** No, you're not.

**DAVID:&nbsp;** No, we're not.

**JESSICA:&nbsp;** [Laughs] There's a reason we work together on a show that someone else does all the work for.

**DAVID:&nbsp;** Yes. Oh my gosh. We should have Mandy write a book.

**JESSICA:&nbsp;** There you go.

**JAY:&nbsp;** [Laughs] I'm sure she's cracking up while editing this.

**DAVID:&nbsp;** I'm a genius. I'm a genius.

**JAY:&nbsp;** I don't know the waveform for that.

**DAVID:&nbsp;** Yeah.

**JESSICA:&nbsp;** There's going to be [inaudible].

**DAVID:&nbsp;** Mandy, that needs to go in the show. Just so you know. That's freaking awesome.

**JAY:&nbsp;** Well, let me say this. [Inaudible] aside, maybe this will give it a direction moving forward. I think that a lot of the sorts of strategies that are useful for pairing are things that companies should utilize when bringing on new developers or apprentices or juniors. I think some of that is the same stuff about empathy, the same things about communication, as it relates to stuff like documentation, as it relates to informing them of their responsibilities as far as organization and preparing as well. I think some…

**DAVID:&nbsp;** Project lore. Stuff that isn't written down but you have to know.

**JAY:&nbsp;** Yeah. Like, what can we do to… there will always be tribal knowledge that's passed around. But is there a way in which we can… to define some of those things and put people in a place where they can be successful? And I see that sometimes that doesn't happen. When I speak to… well, it doesn't happen a lot. For example, let's say we've had some of the folks who've come through Pair Columbus who are now working as developers in some places. They're kind of unsure where they are, what they need to do. I think that also falls into, is it the responsibility of a company to… I don't know. I know some entities have apprenticeship programs. And I think that those are great if they are truly apprenticeship programs. But if not, are we being thoughtful about how we bring people in as opposed to just saying, “Hey, alright,” you know.

**JESSICA:&nbsp;** So Jay, did you say you do training for new hires at CoverMyMeds?

**JAY:&nbsp;** Yeah. So, at CoverMyMeds it's one of the things that I've handled. And it's one of the things that I think that I've worked on a lot within the company and outside of the company, is attempting to kind of… especially for people who are new, extremely new to the industry. They have lots of questions about things like what should my approach be to working with my manager? Or what should I focus on? Where should I focus my energies? How do I deal with conflict when I'm on a team? Things like that.

So, what I'm thinking is that some of the things that I've learned about pairing, learned about myself, some of those traits and those qualities, I feel like companies and organizations, they become… I don't want to get into a political conversation at all. But I do want to say I feel like there is a responsibility that we have to employees, especially new people as well. And a lot of the conversations that I've had with friends of mine who are being hired at companies all over the world, there seems to definitely be this disconnect in a lot of places between employee and employer. And it's like, I don't know. “Alright, this is a job. I go home. This is cool,” but there are a lot of things that are left unsaid, just because communication is poor. And I think that communication is really important to pair programming. Empathy is really important to pair programming.

And it's helpful from a managerial aspect to keep this stuff at the forefront of your mind when you're bringing people in and [not] say, “Hey, we got a new person.” “Okay, cool. Send him over there and give him some work to do.” I'm just seeing that in conversations with friends who are in the industry. So, I don't know. That's just my two cents on that.

**DAVID:&nbsp;** That's awesome. That's awesome.

**JESSICA:&nbsp;** So, I think you said that the qualities that make a good pair programmer make a good member of a community, and therefore a good member of a company?

**JAY:&nbsp;** Yeah. But I would say it's tough to, if you're looking at it from a company perspective it's weird. Because you have pairing between an individual and an organization. So, what I'm saying is that I feel as organizations, as members of organizations, we have to make sure that the things that you might see in pair programming aren't getting lost in that relationship between individual and organization. So, are we doing our best as an organization? A good example is, well how do you bring on new people? How do you make sure that people are [inaudible] part of a team?

Let's think about remote developers for example. Are the resources that are available to people in office, are those same resources… and that may be things like trainings that are available. There may be a lot of hallway conversations happening. How do we make sure that they're getting those things that they need in order to be successful? And I think all of those things at the end of the day, are they shipping code? No. but they're really important. And so, it's important for us, I think it's important for us whether we are… someone like myself who's in the office and I'm working with someone who's remote like Dave, we say, “Hey, are we doing what we need to do? Are we empathetic to making sure that someone like Dave is getting what he needs to be successful?” Or a new person or whatever.

And I feel like because that stuff is… you don't… there's not some emotional quotient or something that's being touted in the Wall Street Journal, there's not going to be a CEO who's like, “Oh yeah. We didn't bring in as much money but boy we feel a whole lot better.” And I think that's really…

**DAVID:&nbsp;** [Laughs]

**JAY:&nbsp;** I think that's important when you think about things like churn, too.

**DAVID:&nbsp;** Yeah.

**JAY:&nbsp;** Which affect everyone, right? If you have a friend that comes in and starts working for you like, “Hey, I love to work with these people that I'm working with but everyone keeps leaving. Why am I still there? Why are these other people leaving?” So, I think it's those sorts of things that happen at all types of different companies. And so, this whole big spiel was just to say two things. That we definitely have to focus on communication organization to individual, like between organization and individuals. And I think also focus on empathy, treating people the way that we would like to be treated.

And then there's a great quote. It's somewhere on my Twitter. It's Billy Graham. I heard it on NPR and he said, “How should a man live in order to not feel regret?” or something along those lines. And so, for me that's why I really enjoy the job that I have. It's just really important I think. I like to see people excel. And I think a part of someone doing well, they need to know what they need to do. And we also have to watch out for them. You want someone looking out for your best interests. And that's what happens when you're pairing. So, that's my speech. [Laughs]

**DAVID:&nbsp;** That's awesome. That's awesome.

**JESSICA:&nbsp;** David made the point earlier that Ember is a framework that grew out of a community. But really, every great program, every great complex system that we're developing grows out of a community that is the team. And if you don't have that community building, if it's not a stable community, it's not going to be a stable system.

**DAVID:&nbsp;** Wow.

**JAY:&nbsp;** [Inaudible]

**DAVID:&nbsp;** Wow. That is mind-blowing. Because basically what you've taken is you've taken what Charles said and turned it into if you want to produce something, it's the law of the harvest. You sow what you reap. And if you want to produce something great, you have to create the community to create that. I wonder if Jay's comment about companies having a responsibility to pair up with new hires, I wonder if that's why, going back to the beginning of the show,&nbsp; why he's doing so well with Pair Columbus. I shouldn't keep talking about Jay like he's not in the room.

[Laughter]

**DAVID:&nbsp;** Jay, how do you feel that that attitude… do you feel that that influences the way Pair Columbus is run? Do you feel like there's a responsibility there?

**JAY:&nbsp;** Do I feel that I have a responsibility to each new attendee? Is that what you're asking?

**DAVID:&nbsp;** Yeah, yeah. Please say no. I would love to have some dirt on you.

**JAY:&nbsp;** [Laughs] No, without a doubt. Without a doubt. I try to… well, I'm not going to mention any meetups. But I'll say this. I remember when I first started going to meetups, industry related meetups. And I remember my first time going and sticking out like a sore thumb and being this relatively young and gray-haired white dude. And being in the room and I have weird social anxiety that comes up at weird times. And being there not speaking to anyone, not having anyone say anything to me but wanting to be there but not necessarily feeling welcome. And it's not because people weren't… I don't think wanted to be welcoming. It's just like, “I don't know this guy so I would not say anything to him.”

And so, after Pair Columbus I'm usually absolutely exhausted and that's because I force myself to make sure that if I do not recognize you that you are greeted when you come in the door and that you are welcome and that you feel like you can grab me or bother me at any time. And I also try to make sure that if it's not something that, if I can't help introduce you to what we're doing, that I have introduced you to someone who's a part of our team or a long-time attendee who can make you feel welcome. So, I think that's cool. High school nightmares lingered with me [laughs]. The lunch room, right?

**DAVID:&nbsp;** [Chuckles]

**SAM:&nbsp;** [Inaudible] all of us.

**JAY:&nbsp;** I'm sure with other people, right? You come in. And it's like, “Okay, hey, where do you sit at?” or, “I'm here in this corner by myself.” For me, that's just my overall life philosophy is to, if I've been through something that's been difficult for me, to try to help other people avoid that. And so, I think a lot of the work that I've done… and it's also a testament to a place like CoverMyMeds who are like, “Hey, you seem to really love this. You seem to really love working with new people. This seems to be a passion point of your.” They said, “Hey, why don't you do that for us on top of development stuff?” But yeah, to answer your question, a really long answer to your question Dave, yes. Yes.

**DAVID:&nbsp;** No, that's awesome. That is freaking awesome. That is freaking awesome.

**SAM:&nbsp;** You mentioned greeting people as they come in, especially new people. That's so important. We had somebody that took over the running of the Portland Ruby Brigade a few years ago now. And he made it a point to personally greet everybody who came in. And it just made everybody feel so much more welcome and made such a huge difference.

**JAY:&nbsp;** Yeah. Yeah, you see it too, right? You see it in people's faces. They come in and they're a little bit wary. They don't know where to go. And there's something… a good example was just here in the workplace. Some new folks came, a new group of people. They were all relatively new hires who play games, tabletop games. I come to find out they didn't know that it was a whole other group of people who'd been here for a long time. And they didn't know each other. So I'm like, “There's more people to play games.” They're like, “What? No way.” And so, just the excitement of knowing, “Hey, we're going to have one more for that Magic: The Gathering draft.” [Laughs] It brought a lot of excitement to people's faces. But I think that we spend so much time of life at work it makes no sense for us to work and be unhappy. So, if I can…

**DAVID:&nbsp;** Amen.

**JAY:&nbsp;** If I can help people through that, which then brings… which has now increased my happiness, then of course. So, that's my two cents on that. Physics of software is people. Amen.

**SAM:&nbsp;** Oh yeah, I was going to mention earlier…

**DAVID:&nbsp;** I like that.

**SAM:** &nbsp; While you were talking about organizations and how to interact with new people. We were sort of dancing around Conway's Law a little bit, which I'm looking at the Wikipedia entry for it. It states that organizations which design systems are constrained to produce designs which are copies of the communication structures of those organizations.

**JESSICA:&nbsp;** The way to use Conway's Law is to decide how your system needs to work and then structure your organization like that.

**DAVID:&nbsp;** Oh my gosh, I've never thought about weaponizing Conway's Law.

**JESSICA:&nbsp;** [Laughs] There you go. We're getting violent.

**JAY:&nbsp;** [Laughs]

**JESSICA:&nbsp;** This is not about violence, David.

**JAY:&nbsp;** It's a tool.

**DAVID:&nbsp;** Okay. Okay.

**JAY:&nbsp;** No, you're a tool. [Laughs]

**DAVID:&nbsp;** When I say weaponized… [Chuckles] Yeah, what I mean is we always accept Conway's Law like gravity. You can't just force gravity to go the direction that you want. All you can do is just build from the bottom up and just accept that. But we can change an or-…

**JESSICA:&nbsp;** [Inaudible] water wheel.

**DAVID:&nbsp;** Yeah, you're right. It's more like a water wheel. We can change the communication structures of an organization in order to… holy crap. That's coming up at the next team meeting.

[Chuckles]

**DAVID:&nbsp;** Right? If software is being difficult, maybe it's not the programmers. Maybe we need to sit down and change. And we need… in fact, don't even look at… oh man, I am screwing this up but whatever. Instead of looking at the software is difficult, why is it difficult? I wonder if we can all sit down and say, how could I change the communication patterns in this organization without a need, without having to come up with a business case for changing those? Just say, “Hey, let's change our communication pattern so that the software will change.”

**JAY:&nbsp;** Yeah. Interesting point. And also, in order to do that you have to be mindful of the path. You know what I mean?

**DAVID:&nbsp;** Yeah.

**JAY:&nbsp;** So, that's also a part of that as opposed to saying, “Well, we're just constantly reacting to whatever is going on around us.” Oh, we are growing and so we're going to react to that growth [inaudible] we know that we're growing.” And be mindful of the things that we try out. But it's just one of those things for me that's rooted in things that I was taught as a kid. And I think it makes sense. It makes sense. I wanted to be a teacher at some point in time. I don't know if I'm a teacher now.

**DAVID:&nbsp;** [Chuckles]

**JAY:&nbsp;** But it's more of helping people find the things or helping people find the things or people, other people that they need in order to not necessarily be successful but to me more content I think in life. And I think contentment comes from… contentment comes from… oh my goodness, this is philosophy 101. I don't know where contentment comes from. What am I talking about? [Chuckles] But I think it helps with my overall contentment. [Laughs] Oh, man.

**DAVID:&nbsp;** This is… This is…

**JAY:&nbsp;** [Inaudible] myself into trouble.

**DAVID:&nbsp;** No, no, no, no, no. This is exactly the anatomy of… this is the… for those of you listening at home very carefully, this is the secret anatomy of why a Ruby Rogues show is awesome or an episode is less awesome. It's because we pick a really technical topic and then we end up talking about happiness.

Speaking of happiness, and going back to pair programming we talked about earlier, I gave a talk at MountaintWest RubyConf three or four years ago called 'What's Wrong with Ruby's Object Model (And Why that's a Good Thing)'. And I ended up spending half my talk time talking about the human brain because I just read 'The Master and his Emissary' which is a book about right brain versus left brain. And TL;DR, we all know that right brain/left brain is bunk, right? Left brain is logic, right brain is creativity. That's bull crap, right? Well, actually the bull crap is bull crap. It turns out that the left brain and right brain, yes there are studies that show there is absolutely no function that one side of the brain can lose that the other side can't pick up and take care of because the brain is very, very plastic. But if left brain and right brain really is just completely garbage, how come if you get kicked in the left side of your head you lose language every time? Except for five percent of people because their brains are actually flipped.

The left brain, the neural network, develops into tightly optimized cells. And those cells communicate with each other loosely. The right brain has very loosely compacted nodes for doing everything. But those nodes are fully interconnected with each other. And so, what happens in pretty much every species that has a bilateral brain because we have evolved relentlessly to capitalize on this specialization, the left brain, those of you five percenters can just flip this in your head, but those of us that are the 95% here, and this goes all the way down to birds, the left brain is designed to narrow in and focus and isolate things out of, take things completely out of context. Like a bird pecking on the ground is going to go, “That's a rock. That's a rock. That's a rock. Seed. Eat it.” And the right brain is continuously integrating everything in the universe at once. It's continuously going, “Yeah, I'm hungry. The wind is blowing. Or the wind is not blowing. And the grass is rippling over there. That might mean there's a cat that I have to be thinking about flying away.” And the right brain is continuously integrating everything.

And the reason I bring… so, that's the end of the TL;DR. The reason I bring that up going back to pair programming is that the driver is often the left brain and the navigator is often the right brain. And the amount of talking you are doing is how active or dead the corpus callosum is in your pair.

**JAY:&nbsp;** Cool.

**DAVID:&nbsp;** If you're not talking, you’re brain-damaged as a pair. And if you're talking non-stop your corpus callosum is fully activated. Actually, if you're talking completely non-stop that means you're having an epileptic fit. But I'm taking the metaphor a little bit too far.

The reason I called back to that just now is that the reason we said in the 1980s that left brain/right brain is bunk is that we invented the fMRI. And we found that when you're doing a math problem you use your right brain and when you're painting a painting you use your left brain. And even though you're not supposed to, art's supposed to be on the right and math's supposed to be on the left and da-da-da, it turns out that when you are working a math problem you're holding the rules of arithmetic in your left-hand side and you're trying to creatively put them all together into an integrated solution on the right. When you're painting a painting you're trying to hold the gestalt of the entire painting in your head in one side of the brain. On the other you're trying to actually guide the specific brush strokes and which components are going to work together here to help contribute to that whole. And I mentioned that because every time someone in an MRI has reported doing something fulfilling, contentment-making, contenting…

**JAY:&nbsp;** [Chuckles]

**DAVID:&nbsp;** Something contentful… contentious is probably the wrong word. Something that makes us feel contentment and something that makes us feel happiness, they light up fully on both sides of the brain at the same time. So, if you want to be fully energized as a pair, you have to make sure that both pairs are fully lit up and engaged and communicating with each other. And yeah.

**JAY:&nbsp;** That's amazing. My dad would say, “That's powerful.” [Laughs]

**DAVID:&nbsp;** Yeah.

**JAY:&nbsp;** But I would take that and go back to what I was talking about before and then pull that apart and say… not pull it apart but then extend it to individuals and organizations as well.

**DAVID:&nbsp;** Yeah, yeah.

**JAY:&nbsp;** I would say the exact same thing.

**DAVID:&nbsp;** Yeah. That's the fun thing about Ruby Rogues. You get one of these episodes and you never know if I'm going to go meta or if I'm going to go to the poop joke. And…

[Laughter]

**DAVID:&nbsp;** If you'll pardon the pun, it's a crapshoot. So, there you go.

**JESSICA:&nbsp;** [Laughs]

**JAY:&nbsp;** Oh, that's cool.

**DAVID:&nbsp;** So, I think we probably ought to move onto picks. This has been a fantastic show. Does anybody have anything else they want to wrap up before we move to picks?

**JAY:&nbsp;** I want to say yeah, I want to say thanks, Dave, because you've been amazing and I'm happy to have met you and to work with you. Thanks also too for suggesting Michael Feathers as a speaker at Pair Columbus. He came and hung out with us recently.

**SAM:&nbsp;** Oh, very cool.

**DAVID:&nbsp;** Awesome.

**JAY:&nbsp;** We had a hundred and sixty something people show up.

**DAVID:&nbsp;** Nice.

**JAY:&nbsp;** So, that's cool. He was like, “I didn't…” I'm pretty sure he said [laughs] “I didn't know Columbus existed.” No, he didn't say that.

[Laughter]

**JAY:&nbsp;** But it was like, “I didn't know you guys' community was so strong.” And I was like, “I didn't know that either.” But no, it was really great. And you had a lot to do with that. So, I want to say thanks for your advice. I appreciate you.

**DAVID:&nbsp;** That's awesome. Thank you very much. Mandy, could we take that sound clip and have it bronzed and sent to my house?

**JAY:&nbsp;** [Laughs]

**DAVID:&nbsp;** That would be fantastic. That would be great. Let's…

**SAM:&nbsp;** I do want to call back if I may to, for the listeners who may not have been with the show for as long as some of us, episode 26 was about pair programming and episode 126 coincidentally was about remote pair programming. And both of those get into a lot more, well a lot more volume I suppose, of theory and detail about pairing [inaudible].

**DAVID:&nbsp;** Okay. Let's go ahead and jump into picks. Sam, do you want to kick us off?

**SAM:&nbsp;** Sure. I'll just do two today. The first one is I have a standing desk, or rather a sit/stand desk. It's motorized. And it's called the Jarvis. It's sold by a company called Ergo Depot. And they have [inaudible] in Portland and San Francisco. And I bought this desk about two years ago and I put a nice, big piece of plywood on it because I thought that [inaudible] this big desk. It turns out that is a really good way to accumulate more stuff on my desk that just piles up and drifts. So, I recently went and I got a smaller tabletop from IKEA and put it on my desktop. In that process it broke, which was super annoying and actually hurt my back because it broke in such a way that it was several inches higher than it normally should have been. So, my shoulders were hunched [down].

**DAVID:&nbsp;** Mm.

**SAM:&nbsp;** But I wanted to give a shout out to Ergo Depot because their warranty support was amazing. They have a warehouse here in Portland so I was actually [inaudible] to go over and drive and pick up the parts that I needed the very next day rather than having to wait two or three days for it to be mailed.

**DAVID:&nbsp;** Nice.

**SAM:&nbsp;** And they were super friendly and the desk is that amazing. It has this lifting capacity of 350 pounds, which is absurd. But anyway, yeah, the Jarvis desk. It's pretty cool.

The other thing I want to pick is a quick article called 'What Do Women Want at Hackathons? NASA Has a List'. And this talks about a couple of things that event organizers can do to increase the number of women who show up. This covers basic stuff like welcoming language on the website and emails and other marketing material. And having pictures of people who look like you on the website offering child care, which isn't a woman's issue. It's a parent's issue. But I guess [inaudible] stuff. But what I found especially interesting about this article was that NASA found that women really wanted to show up a day early for the hackathons so that they can network with other women and get comfortable in the space before the hackathon started.

**DAVID:&nbsp;** Wow.

**SAM:&nbsp;** Personally I've never been a fan of hackathons. But if you're going to run one and you want more women to show up, scheduling a workshop for the day before sounds like it would be a pretty effective strategy.

And [inaudible] my picks.

**DAVID:&nbsp;** That's awesome. Very cool. Thank you. Jessica, do you want to go?

**JESSICA:&nbsp;** Sure. I've got some picks. The last time I was on I picked Craft Conf ahead of time. So this time, I'll pick on talk from there. Dan North did the opening keynote and it's about 'Embracing uncertainty: why you should and why you won't'.

**DAVID:&nbsp;** Hmm.

**JESSICA:&nbsp;** I'll provide a link to the show notes. And this is the talk that was the origin of that single-hand clapping and pairing and…

**DAVID:&nbsp;** Mm.

**JESSICA:&nbsp;** The product of the system that I mentioned earlier.

My second pick is a paper called 'Common Ground and Coordination in Joint Activity'. This is a paper about people working together. And it also talks about people working together with software. But the interesting part to me is how it breaks down the requirements of coordination in a joint activity, of sharing an objective and working with other people to achieve that objective. It breaks down the prerequisites, the different challenges, and how we can maintain this without the cost of coordination overwhelming the benefits. I'll put a link in the show notes. Totally useful paper, really liked it. Great vocabulary for talking about how you work with your team.

**JAY:&nbsp;** That sounds great.

**JESSICA:&nbsp;** The end.

**DAVID:&nbsp;** Very, very cool. Very, very cool. So, it's tradition for the host to go last and I just want to tell everybody that wants to just turn it off right after Jay is done speaking that I have one pick and it's going to take me less than 60 seconds, by which I mean 90 seconds. But I don't mean five minutes. So, I've got a hot sauce pick today. But it's going to be really quick. So, before that, Jay, do you have some picks for us?

**JAY:&nbsp;** I do. And what I did because I wasn't able… well, not wasn't able to but I wanted to include some of the people from Pair Columbus [inaudible].

**DAVID:&nbsp;** Oh, yeah.

**JAY:&nbsp;** I asked them to give me some picks. So…

**DAVID:&nbsp;** Cool.

**JAY:&nbsp;** But I do have one myself and that would be 'Apprenticeship Patterns', the book from Dave Hoover and Adawale Oshineye. It's a really, really great book. I recommend that new developers, people who are pairing with pairing for the first time or have been pairing for a long time, or even organizations that emphasize pair programming, just take a look at it. I think it says a whole lot about our responsibilities to each other as teammates. And it's really, really great, really, really great book.

And then I have a pick from Brian Lees. It's Zach Holman's 'How to Deploy Software' article.

**DAVID:&nbsp;** Mmhmm.

**JAY:&nbsp;** It's really great. I would suggest that, I haven't read all of it but it looks really, really good. If you have questions and thoughts on how your team deploys software which his advice is it should be boring as hell.

**DAVID:&nbsp;** Mmhmm.

**JAY:&nbsp;** And you should stop stressing about it.&nbsp;

And then my last pick is from a great friend, Vasanth Pappu. And it's 'The Book of Shaders' from Patricio Gonzalez Vivo. Super readable, interactive guide to working with shaders. And there are some technical challenges to it. So, if you're looking for a new challenge, want to something a little bit different, you definitely want to check that out.

**DAVID:&nbsp;** Awesome. Thank you. Okay guys, I'm actually starting a stop watch right now. I have one pick today and it's a hot sauce pick because I mentioned last week I was in Ohio and I stopped by CaJohn's Fiery Foods, discovered them for the first time. And I bought three sauces. And I was afraid to even open the other two. And I opened the middle one this week. It's a two million Scoville sauces. It's called Black Mamba. The top of the box says “This is hate in a bottle.” And it lives up to the name. But this is the exciting thing is you can take this stuff and use it in micro, micro, micro drop format. You don't even put a drop on it. You dip a toothpick in it and get the toothpick stained and then you wipe that in some food. And it makes it insanely hot which means you can make… and there's absolutely no flavor change, which means my food pairing is Dreyers Vanilla ice cream with Black Mama habanero hot sauce. It is crazy, crazy amazing.

The one thing I will warn you about this is that cream covers up some of the heat of the hot sauce which means that as the song 'Rock the Kasbah' says, “The wrong antidote is like a bomb in the throat. In this case it's like a bomb in your stomach or your intestines if you eat too much. So, know your limits put it in soup. But a drop in something. Find out what you can eat. And then don't put more than that in your ice cream. But it tastes amazing. Try it. That's my pick.

And that's our show today. Thank you guys for coming. This was a great show.

**JESSICA:&nbsp;** Thanks Jay, for being a guest.

**JAY:&nbsp;** Yeah, thanks. [Inaudible]

**SAM:&nbsp;** Thank you very much.

**DAVID:&nbsp;** Alright. And we'll see you all next week.

**_[Bandwidth for this segment is provided by CacheFly, the world's fastest CDN. Deliver your content fast with CacheFly. Visit C-A-C-H-E-F-L-Y dot com to learn more.]_**

**_[Would you like to join a conversation with the Rogues and their guests? Want to support the show? We have a forum that allows you to join the conversation and support the show at the same time. You can sign up at RubyRogues.com/Parley.]_**

**_[End of podcast]_**


