---
layout: layouts/post.njk
title: >
      225 JSJ Functional Programming with John A. De Goes
date: 2016-08-17 07:00:51
episode_number: 225
duration: 56:10
audio_url: https://media.devchat.tv/js-jabber/JSJ225FunctionalProgramming.mp3
podcast: js-jabber
tags: 
  - js_jabber
  - podcast
---

03:08 - John A. De Goes Introduction
- [Twitter](https://twitter.com/jdegoes)
- [GitHub](https://github.com/jdegoes)
- [Blog](http://degoes.net/)
- [SlamData](http://slamdata.com/)
04:07 - [PureScript](http://www.purescript.org/)
- [JavaScript Jabber Episode #189: PureScript with John A. De Goes and Phil Freeman](https://devchat.tv/js-jabber/189-jsj-purescript-with-john-a-de-goes-and-phil-freeman)
04:58 - “Purely Functional” ![interactive-1](https://devchat.tv/wp-content/uploads/2016/08/interactive-1.gif)09:18 - Weaknesses With [Functional Programming](https://en.wikipedia.org/wiki/Functional_programming)
- [Object-oriented Programming](https://en.wikipedia.org/wiki/Object-oriented_programming)
- [Procedural Programming](https://en.wikipedia.org/wiki/Procedural_programming)
14:36 - Organizing a FP Codebase
- [John A. De Goes: A Modern Architecture for FP](http://degoes.net/articles/modern-fp)
17:54 - Beginners and Functional Programming; Getting Started
- Learning About the History of Functional Programming
- Hiring Junior Devs to do FP
28:20 - The Rise of Functional Programming in JavaScript-land32:08 - Handling Existing Applications36:03 - Complexity Argument41:53 - Weighing Language Tradeoffs; Alt.jsPicks
- [Nadia Odunayo: The Guest: A Guide To Code Hospitality @ RailsConf 2016](https://youtu.be/hHzWG1FltaE) (Aimee)
- [React Rally](http://www.reactrally.com/) (Jamison)
- [Cleanup Algorithm](http://joneshf.github.io/programming/2015/10/04/Cleanup-Algorithm.html) (Jamison)
- [PostgreSQL Exercises](https://pgexercises.com/) (Jamison)
- [iPad Pro](http://www.apple.com/ipad-pro/) (Chuck)
- [Smart Keyboard for iPad Pro](http://www.apple.com/smart-keyboard/) (Chuck)
- [Apple Pencil](http://www.apple.com/apple-pencil/) (Chuck)
- [GoodNotes](http://www.goodnotesapp.com/) (Chuck)
- [John A. De Goes: Halogen: Past, Present, and Future](http://www.slideshare.net/jdegoes/halogen-past-present-and-future) (John)
- [slamdata](http://github.com/slamdata/slamdata) (John)


### Transcript

**_[This episode is sponsored by Frontend Masters. They have a terrific lineup of live courses you can attend either online or in person. They also have a terrific backlog of courses you can watch including JavaScript the Good Parts, Build Web Applications with Node.js, AngularJS In-Depth, and Advanced JavaScript. You can go check them out at FrontEndMasters.com.]_**

**_[This episode is sponsored by Hired.com. Every week on Hired, they run an auction where over a thousand tech companies in San Francisco, New York, and L.A. bid on JavaScript developers, providing them with salary and equity upfront. The average JavaScript developer gets an average of 5 to 15 introductory offers and an average salary offer of $130,000 a year. Users can either accept an offer and go right into interviewing with the company or deny them without any continuing obligations. It’s totally free for users. And when you’re hired, they also give you a $1,000 bonus as a thank you for using them. But if you use the JavaScript Jabber link, you’ll get a $2,000 bonus instead. Finally, if you’re not looking for a job and know someone who is, you can refer them to Hired and get a $1,337 bonus if they accept a job. Go sign up at Hired.com/JavaScriptJabber.]_**

**_[Let's face it. Bookkeeping is hard and it's not really what you're good at anyway. Bench.co is the online bookkeeping service that pairs you with a team of dedicated bookkeepers who use simple, elegant software to do your bookkeeping for you. Check it out and get your free trial today at Bench.co/JavaScriptJabber for 20% off today. They focus on what matters most and that's why they're there. Once again that's Bench.co/JavaScriptJabber.]_**

**_[This episode is sponsored by Rangle.io. Rangle's been working with Angular 2 for a long time and they are now putting together an eight-hour, 2-day course designed to help Angular developers learn how to write apps in Angular 2. If you're looking to level up your JavaScript and Angular 2 skills then go to Rangle.io/training and click on the link for Angular 2 training. If you're looking for other training in React or JavaScript, they also have that available at Rangle.io/training.]_**

**_[This episode is sponsored by Rollbar. One of the frustrating things about being a developer is dealing with errors. Ugh. Relying on users to report errors, digging through log files to try debugging issues, or a million alerts flooding your inbox ruining your day. With Rollbar's full-stack error monitoring, you get the context and insights and control you need to find and fix bugs faster. It's easy to install and you could start tracking production errors and deployments in eight minutes or less. We have a special offer for JavaScript Jabber listeners. Go to Rollbar.com/JSJabber and sign up and get the bootstrap plan free for 90 days. That's 300,000 errors tracked for free. Loved by developers at awesome companies like Heroku, Twilio, Kayak, Instacart, Zendesk, Twitch, and more. Give Rollbar a try today. Go to Rollbar.com/JSJabber.]_**

**CHUCK:&nbsp;** Hey everybody and welcome to episode 225 of the JavaScript Jabber Show. This week on our panel we have Aimee Knight.

**AIMEE:&nbsp;** Hello.

**CHUCK:&nbsp;** Jamison Dance.

**JAMISON:&nbsp;** Hello, friends.

**CHUCK:&nbsp;** I'm Charles Max Wood from DevChat.tv. And this week we have a special guest and that's John De Goes.

**JOHN:&nbsp;** Howdy. Good to be here.

**CHUCK:&nbsp;** Do you want to introduce yourself real quick?

**JOHN:&nbsp;** Yes, so I'm John De Goes. I'm currently CTO at a company called SlamData.&nbsp; And we do quite a lot of frontend programming. In fact, we just came out with release 3.0 of SlamData out today. And it is probably the largest PureScript codebase in existence. So, it's an example in the wild of both functional programming and alt JS. A hundred percent open source and available on GitHub for people who want to take a look at what sort of scale that looks like in functional programming.

**CHUCK:&nbsp;** What do you mean by alt JS?

**JOHN:&nbsp;** Well, instead of developing this application in JavaScript we're using one of the alternative languages that compile to JavaScript, in this case PureScript. But TypeScript's an example of another one.

**CHUCK:&nbsp;** Okay.

**JOHN:&nbsp;** And Dart and Elm and so forth. Basically all these dozens and dozens of languages sprouting up that compile to JavaScript.

**CHUCK:&nbsp;** Interesting. So, why build it in PureScript and go all functional programming on it?

**JAMISON:&nbsp;** Well first, can you tell us what PureScript is?

**JOHN:&nbsp;** Yeah. So, PureScript is a statically typed purely functional programming language that's inspired a great deal by Haskell. So, if you're familiar with Haskell then you'll feel right at home with PureScript. And if you're not then you'll be totally confused by its syntax, by its semantics, by everything about it. But it does have a really good interface JavaScript code. You can leverage existing JavaScript libraries. It has a very strong type system. Now quite as strong as Haskell but it's still amazingly powerful. And it has a lot of things that are designed to make it more familiar to JavaScript programmers such as source maps, native JavaScript types for things like records and booleans and strings and so forth, arrays. And it's a really, it's a great little language. We have a growing community. I've been really happy with it.

**AIMEE:&nbsp;** I have a quick question actually. Can you explain what you mean exactly by purely functional?

**JOHN:&nbsp;** Yeah, that's a great question. So basically, purely functional means that if ever you see a function inside a purely functional program then you have the following guarantee. If you pass the function the same arguments, you'll get back the same return value always. And that's actually the definition of a function, really. It's a mathematical function, maybe not a programming language function. But it's a really nice property to have because when you're testing you know if always pass it one, two, and three, you're always going to get back the same value. It's not going to change out from underneath out. And this property of being purely functional makes code not just easier to test but also easier to understand in the large scale because there's less state that you have to keep track of in your head.

Whereas a function that's not purely functional, you pass it one, two, three one time and it will return, “Hello world.” You pass it one, two, three another time it'll return undefined. Pass it one, two, three another time and it's going to pop up an alert. Who really knows what's going to happen? Because its behavior is not dictated by its return value. It's dictated by all the other stuff it's doing behind the scenes, all the global variables it's reading and the console logging functions that it's calling and this and that. And purely functional programs don't have that property. It's all, “Pass me your variables and I guarantee you I will always return the same thing.”

**AIMEE:&nbsp;** I…

**CHUCK:&nbsp;** So first off…

**AIMEE:&nbsp;** Oh.

**CHUCK:** I want to mention. We asked real quick what PureScript is but if you want to know more about that, we did an episode with John and Phil Freeman back in December. So, you can go check that out. We'll have a link to that in the show notes.

And secondly, it seems like if you're building an application with purely functional stuff then what about things like the global variable called your database? Or things like that where…

**AIMEE:&nbsp;** [Chuckles]

**CHUCK:&nbsp;** You have to deal with that, right? Or an API that you're hitting or something like that. Can you write real-world applications with purely functional stuff?

**JOHN:&nbsp;** Yes. And in fact you can. In fact, why don't I paste a screenshot into Skype? You can take a look and maybe upload it for your listeners. But this is an example of the kind of real-world application you can build. Alright. So, the question is can you build real-world applications with functional programming? Which is actually probably the most common question that I get when I tell people that I'm a functional programmer. And the answer is, well look at that screenshot there and it will give you a taste of the type of applications you can build in a purely functional style. And yeah, you're right. There are things like databases and things like web servers that you have to call. And all of this involves lots of state. And purely functional programming languages, they have a bunch of means to deal with such things.

And the simplest is just to basically describe such effects as a hunk of code. So, when you call a function that does like a 'run this query on this database' you get back not the result but you get back a promise to run that result at some future time. And this is the idea behind Haskell's I/O monad. And it's the idea behind PureScript's F type and it's the idea behind a lot of ways to model the impure messy stuff that happens in the real world. And what it does is it means that you pass a function a parameter like its SQL query and you get back this promise to run this hunk of code at a future time, which enables you to have a purely functional way to model that thing that we need to do, which is things like global state or third-party web services and so forth.

And yeah, if you're going to write your whole functional program in that style by passing around hunks of code it's going to be a lot harder to test and a lot harder to reason about. But fortunately in most cases, you can write 90% of your program in a way that's much more declarative and easier to reason about where you're not just passing around hunks of opaque code but you're actually describing your problem at a high level and a declarative way. And then for the messy stuff that every single program has to do, you end up passing around these hunks of code or an equivalent technique. That's actually not the only technique in functional programming. It's not even the one used in SlamData. We used a more advanced one but it's just the easiest one to describe.

**JAMISON:&nbsp;** So, I have a few questions. So, I wasn't programming when object-oriented programming became the solution to everyone's problems.

**JOHN:&nbsp;** Yeah.

**JAMISON:&nbsp;** But I imagine it felt a lot like it feels to hear about functional programming. Like everything is better if you have these objects. They encapsulate all their state. They send messages to each other and you bundle their behavior in your data. And you just get this long list of amazing benefits. And we have those with functional programming too, right?

**JOHN:&nbsp;** Right.

**JAMISON:&nbsp;** Easier to reason about is one of the key phrases that every functional programmer loves to say. And pure functions and easier to test. But there's this giant laundry list of problems with object-oriented programming and some downfalls it encounters in the real world. And I feel like I don't hear any of that side about functional programming. Do you feel like you know enough to talk about maybe some of the weaknesses with functional programming? Things that it struggles with or that teams might struggle to adopt it with or anything like that?

**JOHN:&nbsp;** Yeah, that's a good question. So, I think that many of the problems in object-oriented programming, they became apparent after people started writing multi-million line of code applications and maintain those over some period of time. And as anyone who's ever worked in a Java codebase of that size knows well, your application becomes so incredibly coupled. And reasoning about something becomes very, very difficult. And of course programmers being programmers they end up making shortcuts in many cases. And that leads to things like singletons for basically passing around information, avoiding the need to propagate information through a billion different methods. And you see all these sort of just grossly coupled and stateful patterns emerging in object-oriented programming in the wild at that scale.

Functional programming has been around long enough. Unfortunately we do have millions of lines of code codebases out there. And I'm not seeing the same types of problems that I see with object-oriented codebases. I think there still are problems. [Chuckles] Any time you try to scale an application by number of people or by size of the codebase you're going to run into problems in any paradigm. But I think the types of problems that you run into in functional programming are more similar to the types of problems you run into in C. obviously you don't run into all sorts of the same problems. But organization of your codebase, how do you really organize a functional codebase well in a way that lends itself to comprehension by developers new to the team, enables people to find what they're looking for…

**JAMISON:&nbsp;** Mmhmm.

**JOHN:&nbsp;** Helps reduce, reuse, and so forth. Those kinds of concerns that you see in a large C codebase, you see in large functional programming codebases as well. The discoverability and the ability for someone to just jump right in, know what to work on, know where to put stuff, that is an issue in large scale functional programming codebases. But what you don't see is a lot of the super tight coupling between state. And you see this to some degree… I often talk about purely functional programming as being a strict superset of procedural programming. Anything you can do in an imperative programming language like C you can do in a language like PureScript, only you can do it better and easier. [Chuckles]

So for example, you can pass around functions instead of passing around void pointers that need to be functions. So, you can do all the same types of stuff which means that you can literally just transition your codebase to PureScript and it can just look like a C program. And it'll be a C program with maybe stronger type level guarantees. But it will suffer from all sorts of the same problems that your C codebase does when it comes time to reason about that. So, you actually have to work to improve it. But I'd say your baseline level of quality is basically like a C program codebase and suffers from all the sorts of problems that a large scale C codebase does.

**JAMISON:&nbsp;** Except seg faults. [Laughs]

**JOHN:&nbsp;** Right. [Chuckles] You know, you are guaranteed no seg faults.

**CHUCK:&nbsp;** [Laughs]

**JOHN:&nbsp;** No null pointer exceptions, no undefineds.

**JAMISON:&nbsp;** Sure.

**JOHN:&nbsp;** None of that nasty stuff. And that's a benefit of total functional programming as you call a function and you're going to get a value back. And it's not going to throw an exception. It's not going to give you null. It's not going to give you anything except what its type tells you. And having that ability in a large codebase just has a tremendously simplifying effect on the way you reason about it.

**JAMISON:&nbsp;** So, it sounds like you're saying there are still… it's not a silver bullet but the baseline of just you go to write some code, you don't think about it a ton, the end result you'll get in a functional programming language is easier to maintain and better than in I guess a procedural or object-oriented language.

**JOHN:&nbsp;** Yeah, I would say that. I would say even if you don't spend a lot of time working to overcome your natural desire to write everything imperatively the baseline is going to be a bit better than what it's like in an imperative programming language like C and certainly substantially better, at least my experience has been that large C codebases are easier to work on and easier to add people to the team than large Java codebases.

**JAMISON:&nbsp;** Sure.

**JOHN:&nbsp;** Although your mileage may vary.

**JAMISON:&nbsp;** Sure. So, I'm glad you brought up the organization thing because that's a thing that I've struggled with in functional programming is I just end up with a bag of functions.

**JOHN:&nbsp;** Yeah. [Laughs]

**JAMISON:&nbsp;** And everything feels like it's at the same level of abstraction. It takes in some stuff and puts some stuff out and they're all just kind of grouped together in the order I wrote them I guess. So, how do you organize a codebase?

**JOHN:&nbsp;** Yeah, I think that's a good question. And I think the answers to that are still emerging. But I would say that first off, that feeling of I just have a bag of functions, even though it's sort of revolting a little bit right, because [chuckles] if you're used to object-oriented programming or even procedural ones you have standard ways of organizing code in these. And it's a bit more foreign when all you have are a bunch of pure functions and a bunch of data constructors. It takes on a different feel.

So, what I would do is say first off, it's not such a terrible, awful thing that all you have is a bag of loosely coupled functions. Because in the long run, the fact that those functions and the data are not strongly coupled is most likely going to enable you to more easily change that codebase over time. Because you'll be able to throw away half the functions without really having an impact on the other half. And that's one of the properties that I've seen in larger functional codebases is you can literally just throw stuff away and replace it with new stuff. And there's less layers of tangling and coupling that you see in imperative codebases. So first off, that's not necessarily a bad problem to have. But I do see that.

And I think that to some degree the answer is grouping related functionality together, so for example data and functions that operate on those types of data structures. And if you are in a language like PureScript that has type classes then you group type classes and then instances for the type classes with data that implements them and so forth. So, you have baseline levels of let's just keep stuff that works on the same data structures or works on the same type classes, let's keep all that stuff together. And that works reasonably well but it still doesn't give you any sort of clue or guide for how you do the large scale architecture of your program.

And what I've been recommending and an approach that I've been a big, big advocate for is so called modern architecture for functional programming in which you structure your application as almost a series of layers of an onion. And in the innermost part of your program you're talking the business language. So, your acceptance tests or whatever you have, whatever is driving the requirements for a product, you're speaking that language. And then you express that language in terms of a lower-level language. And ultimately you sort of boil everything down to Ajax calls and DOM effects. But you don't speak in those terms right away. You speak at higher levels of abstraction and gradually compile down to a lower-level abstraction.

And I wrote a blog about this on DeGoes.net. It's called 'Modern FP Architectures', something like that. But I'll also be writing the sequel to that in the next week or two. So, it's actually pretty timely. And I do think that of all the approaches I've seen to organizing large scale functional programs, that's by far the best. And it shows a lot of promise for the future, in my opinion.

**AIMEE:&nbsp;** So, I wanted to back up a little bit and ask a couple of questions. I know the last time that we talked to you, I had some of these questions. But I feel like functional programming is pretty intimidating to a lot of people. So, I just wanted to bring that up because I feel like as we're talking there might be listeners… there's kind of like this elephant in the room where especially for new beginners. I know, I worked in a codebase at one point and we made the choice that we would not use currying or partial application because we wanted the codebase to be super readable for all different skill levels. And for somebody straight out of a bootcamp or something, that's not always the most readable. So, I guess I kind of… I don't have a specific question. Just your thoughts around this topic. So, do you think it's still a good choice for a codebase where you want to work with people of all levels? And then another question is what advice do you have to people, I'm assuming you've been programming for years, but what advice would you have to people who are interested but they're feeling intimidated? How do you get started?

**JOHN:&nbsp;** Yeah, so those are really great questions. And I think to answer the latter one first, hopefully I won't forget the first one [chuckles]. It's [inaudible].

**AIMEE:&nbsp;** I can [re-ack] it.

**JOHN:&nbsp;** [Laughs] Okay.

**AIMEE:&nbsp;** I know. That was just a lot of thoughts and questions all at once.

**JOHN:&nbsp;** No, that's good stuff. I think to take that latter one first, I think well first off, first time I tried to learn functional programming I failed. [Chuckles] I went [inaudible] and I…

**AIMEE:&nbsp;** That's good [to hear]. [Laughs] Thank you for admitting that.

[Laughter]

**JOHN:&nbsp;** I'm happy to admit that. I went and I played with Haskell and thought, “No, I don't know this syntax. This isn't C-like or Java-like. And what are all these strange terms? The [mere] operators. And what's infix L mean? And what's all this crap? No way.” And I just ran away from it screaming in terror like most people do.

[Laughter]

**JOHN:&nbsp;** Because it is. It's different and different can be scary. But eventually I sort of crept into functional programming through the back door by just seeing what a difference on a very large 400,000 line of code Java application immutable data structures made. And how just profoundly simplifying that had on the application. Just a simple thing like immutable data makes a huge difference in your application. And eventually that enticed me to learn Scala and I picked up functional programming from there. And then the next time I went back to Haskell I'm like, “Okay you know, this is less terrible than it was to begin with.” But I think to answer your question, yes it is unfamiliar and it's unfamiliar not because it's necessarily very complex. Or rather, it's scary not because it's complex but it's scary because it is unfamiliar.

And an example of that is I know two people whose first programming language was statically typed purely functional programming language. Did they have any of the same problems that I encountered when they ran into it? No. because they had no set expectations. And for them, the syntax of JavaScript was super scary [chuckles]. And like all the rules and exceptions for equality and scoping and this and that, super scary, right? And if you think back to the time when you were learning JavaScript you're probably like, “Yeah, that confused me for a good long while.” And yeah, I still get tripped up when I'm writing native JavaScript occasionally on something. And yeah, for someone who's never seen that before, that could be as scary as Haskell. I think the fact that Haskell and PureScript and all these other statically type purely functional programming are different doesn't necessarily mean they are hard.

But I do want to acknowledge the fact that the first time I went there, I ran away screaming in terror. And it took me a while to get back into it. And what I would say is one of the strengths that we can cultivate as a developer is the ability to learn new things.

**AIMEE:&nbsp;** Definitely.

**JOHN:&nbsp;** Because our industry is always changing, right? And JavaScript especially. Who heard of React four years ago? [Chuckles] And just all the build tools out there, all the JavaScript frameworks, all the libraries. There's this constant, constant changing. And the more we work on overcoming that gut-level reaction to run it and scream in terror, then I think the faster progress we'll make as professional developers. But acknowledging that fear and saying, “Yes, I'm going to look at this and it's going to be scary and if I introduce it to my team it's probably going to be scary for people,” and then working on strategies to deal with that fear and to overcome it and to do it bit by bit instead of perhaps all at once, I think those are all very good things and good ways to focus the problem on.

**AIMEE:&nbsp;** Yeah, I agree. Because I feel like… so, you can borrow some functional concepts in JavaScript or something like that.

**JOHN:&nbsp;** Yeah.

**AIMEE:&nbsp;** But that, like you can do your functions or that kind of thing. But that really only gets you so far. And if you really want to go full on functional then that's when it starts to get pretty intimidating. And you don't want to use JavaScript for that because that's just not how JavaScript was designed.

**JOHN:&nbsp;** That's right. And Elm was obviously designed to address that gap. And I think it does a reasonably good job. A lot of people who tried Haskell that, “Nope, not for me,” the tried Elm. And they're like, “Yeah, this is still a big leap but I can sort of get it.” And I think that's a great way to approach it is find something intermediate like Elm. After you've done the, “Okay, immutable data and operations on immutable data structures,” with some of the libraries out there like Immutable.js, and the next step is, “Okay, what's going to get me on the other side of this divide?” in a language like Elm where you have a lot of the functional concepts but they've been greatly simplified and the tooling is really excellent can help you get over to that other side where you can begin to approach languages like Haskell and PureScript without fearing as much.

**JAMISON:&nbsp;** One thing that kind of helped me with that as well was learning a little bit about the history of functional programming. I know when I first learned to program most of the languages I learned were all kind of similar. If you kind of squint, Ruby and Python and JavaScript and even Java or statically typed languages like that, they all are more similar to each other…

**JOHN:&nbsp;** Yeah.

**JAMISON:** Than they are to the statically typed purely functional family of languages. And a lot of that I think comes down to their genealogy. Like our purely functional languages tend to come from an academic history and background. And they're a lot more linked to some mathematical research stuff. So, they just have a… it's like a different family of spoken languages, right? There are the dramatic languages…

**JOHN:&nbsp;** That's right.

**JAMISON:&nbsp;** The romance languages. If you learn one of those, it's pretty easy to learn all the rest of them. But then if you learn a bunch of romance languages and you try and learn something like Mandarin…

**JOHN:&nbsp;** [Chuckles] Yeah.

**JAMISON:&nbsp;** All the [rules] you've [pumped] up in your head about, “This is generally how languages work,” just get thrown away completely and there are a whole bunch of new concepts. So, recognizing that actually helped me because it made me feel less bad about being totally baffled and bewildered by these new concepts.

**JOHN:&nbsp;** I love that analogy just with natural languages, just the fact that there are families and the syntax can be a big thing for some people. Even if the concepts aren't that complex, especially in a language like Elm, it does have a totally different syntax. But once you learn that one thing over there in that family of languages, the others become a lot less [intimidating].

**JAMISON:&nbsp;** Sure.

**JOHN:&nbsp;** And I think we're to some degree, we're still figuring out how to teach this stuff. There hasn't been the same level of effort put into educational resources in functional programming that there has been in object-oriented programming. So, we all know how to teach object-oriented programming now, right? Like you have your standard animal hierarchy or a [shape] hierarchy.

[Chuckles]

**JOHN:&nbsp;** These things that we've all seen a million times and we know how to teach that. But I think we're still figuring out, we're making progress with things like HaskellBook.com. But we're still figuring out how to teach this new style of programming. And once we become better teachers then a lot of this stuff is just going to take care of itself because you'll have so many people who are writing functional programming, is familiar with the concepts, and who know how to explain it to others because that path has been forged. It's going to become a lot easier for the population in general. And then your first question was how do you introduce it to a team or do you introduce it to a team?

**AIMEE:&nbsp;** That was kind of a question that I had too. Yeah, do you think it's a wise choice…

**JOHN:&nbsp;** [Inaudible] levels?

**AIMEE:&nbsp;** For a team where there are junior developers and senior developers all on the same codebase?

**JOHN:&nbsp;** Yeah, I think that's a good question. And I think that the answer depends on whether or not you're going to have management support for junior developers. Because you're right. Someone can come out of a coding camp and they know how to write Ruby, right? Or JavaScript or whatever it is they learned. And they can immediately jump into a codebase and they can start being somewhat productive. You can give them a little bug ticket or something like that and they can go in there and take that on. Maybe with a little help, a little pairing. They can take that on, complete it, and they can ship code probably on day one. And if you take someone from a coding camp who's learned one of these languages and you put them in a totally different paradigm, in a language with a totally different syntax and with totally different set of best practices that doesn't at all resemble anything they learned in coding camp it's going to be very confusing.

And I'm not going to say it can't be done because actually my company has done it at least once, taking a graduate from a coding camp and bringing her all the way up to functional programming. But it's not easy and it's not natural and it requires a certain degree of support and help that may or may not be there depending on how the team is structured and management's expectations around new hires, especially junior hires. So, I would honestly not choose a statically typed purely functional programming language for the frontend if I knew that we were going to be hiring a bunch of people from coding camps and a bunch of junior developers unless management understood what was going on there. And gave their support to offering an additional level of mentoring and pair programming that's necessary to more quickly ramp these people up into totally different paradigm and language and syntax.

**JAMISON:&nbsp;** So, I want to ask you about the rise of functional programming in JavaScript specifically. It seems like it's spread a lot just in programming in general. But especially in JavaScript there's so much excitement about it and interest in it and all the alt JS languages. Why do you think that is?

**JOHN:&nbsp;** I've thought about that a lot. And I honestly don't really know why there's this special affinity for functional programming in JavaScript land. I do know that having worked on server-side apps and desktop applications and games and scientific software and simulations and just about software everywhere over every part of the landscape, user interfaces are really hard. They are really hard to get right. And they don't scale very well. You can add a few people to a team but then after a certain point it becomes very difficult.

And once the codebase crosses a certain threshold then you accept that any new feature you add is going to add its line count in bugs, in new bugs into the code. It's just become very, very important to have QA and then you have a manual QA process. The complexity of user applications is just tremendous especially compared to a lot of the other types of applications I've worked on. The potential for bugs, the amount if state there is insane. And the ways that you can tangle up a frontend and I've one many times with jQuery doing terrible, terrible things that I don't even want to talk about with jQuery and dynamic, treating the DOM as a database and all sorts of other things that I've done. I've created applications that I couldn't even understand myself six months after I wrote them let alone maintain them.

And I think that this complexity problem and this state problem and this maintainability problem, this comprehension problem that we have, this testing problem… how do you test these things? Selenium is crap. WebDriver is crap. All that stuff is terrible, varying degrees of terribleness. And functional programming comes along and says, “Well maybe [chuckles] our view should be a function from state to a bunch of DOM, a DOM model, a DOM data model.” And that is just sort of a profoundly, that's yeah, that's a profoundly simplifying way of solving the user interface problem. So, I think that… and also things like observables, Rx and Cycle.js and its family of programs in which you reason about things using streams, more like Elm, it has a profoundly simplifying effect on the way that you reason about your frontend user application.

And I think that because the benefits even in the small scale, like React is not a purely functional thing by any means but nonetheless it takes a very simple concept in functional programming and applies it to building&nbsp; user interfaces and has such a profoundly simplifying effect on the way you structure these things that its benefits sell themselves. You don't have to sell them. [Chuckles] You could just look at a big jQuery UE app and look at a big React app and it'll sell itself. So, I think the fact that UE programming is so insanely complicated just on every possible dimension and the fact that just a few principles that have been yanked out of functional programming and applied to UE programming have tremendously simplified it is a big driver for the tendency of JavaScript programmers to embrace principles from functional programming. And also alt JS languages that support functional programming well like Elm and PureScript and so forth.

That would just be a guess though. Honestly I've wondered the same thing, why you're seeing all this functional activity on the frontend. But I think that has to be at least part of it.

**JAMISON:&nbsp;** Sure that makes sense.

**CHUCK:&nbsp;** So, let's say that you've completely convinced me. Functional programming is the stuff. And I've got this procedural/prototypal/jQuery/mess that I'm dealing with right now and I'm like, “Well, if it simplifies it that much I've got to try it.” How do I start fitting my current application into a system like this so that I'm getting these benefits out of it? It's one thing to start fresh. It's another thing to move a working application into a paradigm like this.

**JOHN:&nbsp;** Yeah. I think that's absolutely correct. And I think that there's always going to be limitations with existing applications. And that's because you've got customers. You've got deadlines. You've got stuff in your sprint that has to be shipped. You've got all these external pressures that are going to be driving you to make changes incrementally and in a way that minimizes risk but also minimizes value, too. That's one of the flip-sides. So, I think that you sort of have to accept. If you're starting off with a jQuery UE application then there's… you can't expect to change the world. Certainly not all at once. Over time I think you'll be able to make some progress in improving the way that code is structured. But it may be more through application of principles in functional programming versus… you're never going to have the time most likely to just do a wholesale rewrite to React or rewrite to Cycle or rewrite to one of these other different paradigms. And most likely you're not going to have the option of going with an alt JS language like Elm of PureScript. You're just not going to get there.

So, what I would say is if there's one thing that you can do incrementally is it's to focus on making your functions pure over time. Focus on using immutable data structures when that's possible. And I think you can start with that more or less anywhere. You can literally make small changes in your codebase every time you're in there. And ultimately you're going to run into the limitations of jQuery. But the more stuff you can pull out as pure functions and the more data structures you can convert to be immutable, the easier it's going to be to do further architectural refactoring because things will be less coupled. And the implications of one change will be clear when you're in there modifying the codebase. The implications of something will be much clearer because functional programs do this, a nice little version of control thing where you can pass something to someone else and it's not going to change out from underneath you.

So, it gives you a confidence when you're writing code. I'm going to pass that over there and I know nothing bad is going to happen to it. All I have to worry about is the return value from that function and what I'm going to do if anything. So, I'd say that by focusing on changing as many functions as you can to be pure functions so they're easier to reason about, by using immutable data structures and so forth, you can achieve a lot of low-hanging fruit benefits of functional programming without abandoning jQuery UE which is most likely not something that's going to happen unless you have support from management. Which could happen.

Ultimately I've seen this one shop, they had a jQuery UE application that was complex. It was written and maintained by a bunch of different developers. And it got to the point where it was just so buggy and it was so hard to add new features to that codebase. They said, “Okay, we're going to give you six months. Go out there and use whatever you want,” and they ended up using Elm in order to rebuild the second version of that. And that was because I think the developers made a very good case in that particular scenario that the complexity of the application was such that they were not going to be able to ship features at the rate they wanted and not with the quality that they wanted. And so, it was worth taking a little bit of timeout for the next version of the product which had lots of changes anyway that would have required a rewrite of a good chunk of it.

**JAMISON:** I think that argument you just made about this app is so complex that we need to do it in a different language is really interesting. Because I feel like I've heard the opposite argument a lot where we have to do all these complex DOM interactions and it's unclear how we would get this done in a pure language or a language that has all these extra limitations. In JavaScript you just do whatever you want. You can do all these crazy, hacky, cool animation things. And it just seems like the path to accomplish your product goals is sometimes clear whether that's from familiarity with the language or the power of the language itself. But I have heard the opposite argued from what you just said. So, I'm interested in the argument that it's actually going to be easier for us to build this app in this more restricted language that tries to guide you towards good decisions.

**JOHN:&nbsp;** I think that's very interesting. And it's a pain that I have felt. Basically when you're working within the constraints of purely functional programming and you have all these strong types and so forth and you're trying for good architecture it does constrain how you solve a problem. Whereas in a JavaScript codebase where there's just one type, the type of everything and in which you can implement a feature in probably an almost unbounded number of ways… you can add global variables. You can do callbacks. You can add it here in these listeners. Or you can add it over there or some combination of the two. There are lots of ways to implement anything that at the end of the day you have unbounded flexibility that you shoot yourself in the foot. And the plus side of that is you can get anything done and because you don't have to follow any rules you can usually get it done reasonably quickly.

However, the trade-off, there are actually a couple of trade-offs, and one of the trade-offs is that if there is a bad way of doing it and it takes less than a good way of doing it you're probably going to do that unless you have again management support for doing things the best way. And what that means is you're going to… you're going to add some lines of code that you know at the time are just going to create bugs down the line. Or maybe even bugs right there because you don't exactly understand how the existing code works and you're just incorporating this sort of sideways to disturb as little as possible. And so, you do that and you make a trade-off on the long-term maintainability and the quality of the codebase. And that is something that's going to have a very real cost of the business. We tend to discount that.

But nonetheless there's that real cost whereas if you're approaching it from a language like Elm or PureScript and you go in there, well there's going to be fewer ways to implement it. And yes, that means in general I think you're going to spend longer implementing it because you're going to have to go through… you're going to have to prove to the compiler that the types are going to line up correctly. You're not going to be able to use, or at least not easily, mutable variables everywhere over your codebase. You're going to have to thread state through your application. But even though it takes longer to implement a feature the benefits are that you threaded that state through explicitly. So, you don't have to reason about all the background stuff happening in your application. The types are reflected in the codebase so you have that extra documentation.

And in my opinion ultimately it comes down to the lifespan of the application. If you're targeting an application and it's not designed to be around very long or which has unknown lifespan because it's an experiment then just hacking things together in as fast a fashion as possible is going to deliver more business value per unit time than purely functional programming. On the other hand I would say if you're going to be maintaining this application for a long period of time, you're going to be adding new developers, you're going to scale and scale and scale this thing, then even though it's slower to start eventually you reach a point where the benefits of that approach far outweigh the approach of the other. And because you have a lot of programmers all working on a large codebase with the protection of a very strong static type system and in an environment that constrains you to do things in a way that's easier to reason about.

And so, you end up being able to make more reliable progress over the long term, less risky progress. And there's no, “Oh my goodness. There's no way to do this now,” or, “The codebase is so terrible we have to spend 50% of our time just fixing bugs.” But it's a trade-off that I think different companies will fall on different sides of that for very legitimate reasons in different cases. Just because some apps are not going to be there and you don't even know if some apps are going to be there for very long. And it makes more sense to just hack in stuff as fast as you can rather than trying to take the time to figure out how to do it in a way that's going to minimize your long-term cost of maintaining that codebase and adding new devs to the team.

**JAMISON:** That makes sense.

**JOHN:** An example is if you were to jump into the SlamData codebase, most likely any change you make would result in a compiler error [chuckles]. And the compiler would be saying…

**JAMISON:&nbsp;** [Laughs]

**JOHN:&nbsp;** “No, you can't do that. Sorry. I know you want to do that but you can't do that.” And the compiler would continuously be beating you up about, “Nope, that's not going to work. Sorry.” And [chuckles] that could be considered a bad thing if it was a small team and we needed to ship stuff yesterday. But if you're working on the SlamData codebase, you're the next hire out of however many hires, that could actually be a good thing, too. Because if the codebase were entirely all JavaScript and it were all jQuery UE and stuff you could jump in tomorrow and you could make a change and there would be no compilers that complain about it. And it didn't matter what change you made. It would probably go through and possibly even make it all the way to production regardless of the implications of that change on the quality of the codebase or ease of comprehension or whether or not it has even proved to be correct at compile time by the compiler. So, those are the trade-offs that every company needs to evaluate I think on a case by case basis.

**JAMISON:&nbsp;** Sure. Okay. My question is about alt JS in general.

**JOHN:&nbsp;** Yes.

**JAMISON:** So, the trade-off it feels like you make when you choose a language like PureScript or Elm or ClojureScript or any of these non-JavaScript languages is you're trading power in the language, the language has all these extra features that JavaScript doesn't have that you feel are really valuable, for size of community. I imagine the PureScript community is maybe a couple orders of magnitude smaller than the JavaScript community.

**JOHN:** At least.

**JAMISON:&nbsp;** So, there are just a lot fewer people working to solve common problems. And you could argue that you just avoid some problems because of the language. But there are still… you need like a date time library. You need to make Ajax calls. And someone has to read that spec and make sure it's doing all the right stuff. And I don't know, there are just a lot fewer people working on the same problem. How do you weigh those trade-offs?

**JOHN:&nbsp;** So, for me I always gravitate towards languages like alt JS or alt JVM languages [chuckles] that are able to reuse existing libraries in the ecosystem. And that's why for our backend infrastructure we use Scala. And we use Scala, it's basically an alt JVM language, right? Java was the original but now you can run all these other different languages on the JVM. And one of the great things about Scala is that because it runs in the JVM it has seamless interop with literally tens of thousands of really great open source libraries that have just decades and decades of developer time spent into improving them and making sure they're robust and using them in production cases. And I feel like it is useful to be able to leverage the just vast, vast JavaScript ecosystem that is, it's not standing still. [Chuckles] It doesn't wait around just because a bunch of people have gone off and done some alt JS stuff. It keeps on advancing at a very fast pace. And that's great. And I want to be able to take advantage of all the libraries out there inside of my application.

And that's one of the reasons that I gravitated towards PureScript versus some of the other languages. For example, Haskell actually runs in the browser. But it's not a particularly good fit for the browser. And it's hard to reuse JavaScript code in Haskell. It's really nasty and messy. And same for Elm. Elm you can sort of reuse JavaScript code but it's a bit of a pain. And for me, there are so many components inside of SlamData, our application, that we reuse. Like we reuse the Ace editor. We reuse ECharts. We use lots of stuff, just tons and tons of stuff inside the JavaScript ecosystem. And what's enabled that to happen is PureScript's really good support for integrating with existing JavaScript codebases. So, it's almost trivial to reuse other stuff out there inside the JavaScript ecosystem.

And that enables the whole frontend team to benefit from all the work that has been done and continues to be done inside the JavaScript ecosystem and not having to reinvent every wheel from scratch. Some wheels are probably worth inventing just because you can do a fundamentally different approach inside of PureScript than you can in JavaScript. But some wheels are like date time stuff, that's a great example. There's Moment.js and lots of other great libraries out there for date time manipulation. There's no need to reinvent those. And an alt JS language like PureScript gives you the option of reusing all that stuff without any pain, or without much pain anyway.

**JAMISON:&nbsp;** Cool.

**CHUCK:&nbsp;** Yeah, I found the same thing kind of works with some of the other things that I've done with TypeScript and Angular.

**JOHN:&nbsp;** Yeah.

**CHUCK:&nbsp;** Where you just pull it in as part of the build process. As long as it can export the module and do all the other stuff then it works. And it works seamlessly. It's not like I have to go and bend it to my will or write glue code. It just sucks it in and says, “Yeah, you can do that.” And it's good.

**JOHN:&nbsp;** Yeah, TypeScript does an awesome job with that. And there are all these IDLs out there for all these different libraries that you can just reuse. And most likely if it's a popular library you don't even have to write the IDL. It's just already out there. And at worst, you might have to maintain it. So, I think that's definitely the way to go. If you want to reuse a lot of JavaScript code then pay a lot of attention to the foreign function interface for your alt JS languages. Because otherwise, you're going to be reinventing everything from scratch or going through a lot of pain and jumping through a lot of hoops to reuse some JavaScript code.

**CHUCK:&nbsp;** Alright. Any other questions before we hit picks?

**JAMISON:&nbsp;** I'm fresh out.

**AIMEE:&nbsp;** Nothing here.

**CHUCK:&nbsp;** Alright. Let's go ahead and do some picks then. Aimee, do you have some picks for us?

**AIMEE:&nbsp;** Sure. So, hopefully mine is not too much of a repeat for people because it's actually from Ruby Rogues. But I liked it so much that I wanted to share it here in case there's not an overlap. But it's a talk I'm… Chuck, you'll probably do a better job with her last name but she was actually just on Ruby Rogues. It's Nadia and her talk is on code hospitality. I think she did this at RubyConf this year. Or RailsConf or one of the Ruby conferences. But anyway, her episode on Ruby Rogues was really, really good and then the talk itself is just really, really good. So, I'll put a link in the show notes. And maybe Chuck, I'm not sure if you can help me on her name, but [chuckles].

**CHUCK:&nbsp;** Yeah, Nadia Odunayo.

**AIMEE:&nbsp;** Okay, thank you. Yeah. It was just really, really good.

**CHUCK:&nbsp;** Yeah, she was a lot of fun to talk to. So…

**AIMEE:&nbsp;** Yeah.

**CHUCK:** Yeah, definitely check that out. Jamison, what are your picks?

**JAMISON:&nbsp;** Yeah, I have three picks. The first one is both self-serving and not self-serving. React Rally is a conference. It's in Salt Lake City August 25<sup>th</sup> and 26<sup>th</sup>. We have some amazing people from the React community coming to talk to us about cool things they built. And we have a bunch of fun activities planned. So, if you go to ReactRally.com you can buy tickets. And I'll be happy because there'll be more people there and we can do more cool stuff. And you'll be happy because you'll learn cool things.

My other two picks, one of them is a blog post about, it shows refactoring a chunk of code from an imperative style to a functional style. And it's very detailed, almost too detailed in some places. Like yeah, okay you moved this function down there. But if you're interested in looking at what it might look like to do some of the things that we talked about today about incrementally adding a functional concept to a codebase this is a really interesting read on it. And I think the code is a lot easier to understand and feels a lot better at the end.

And my last pick is a site called PGExercises.com. It's kind of an interactive online SQL tutorial. So, they have this browser interface to a SQL database. And it's got a schema loaded with data in it already and everything. And then they just give you a bunch of tasks and explain how you might walk through those tasks. And I'm trying to brush up my SQL skills and this has been really helpful. So, those are my picks.

**CHUCK:&nbsp;** Nice. I'm going to jump in here next. I was at Podcast Movement last week which is a big conference for podcasters as you can imagine. I had a ton of fun, learned a ton of great things, going to be changing some things up as far as our process goes to make the shows hopefully better than they are. Though I know a lot of people really love them. So anyway, I just got some ideas I'm going to try out and we're going to see how they affect things. But while I was there I had to run to the Apple store three times because my iPhone broke. It was like a 10 or 15-minute walk from the hotel where the conference was so I just walked down Michigan Avenue and walked back.

But while I was there I was tempted and lured and bought the iPad Pro. And the iPad Pro is awesome. And there are a few things that I really like about it. I'm not going to give a full review here. I should probably do that though at some point. And I'm starting to do more Periscopes and video things. So, if you follow me on Twitter then I should be announcing when I'm doing those before I do them. So, just follow me, cmaxw or C-M-A-X-W. And I'm probably going to turn it into some kind of show, some video show or vlog or something. Anyway, not quite sure on that yet. But anyway, so the iPad Pro has a Smart Keyboard. And one of the things that were nice was that it fits really nicely on the tray table thing that you have on the back of the seat of the person in front of you on the airplane. My laptop is just slightly too big. I think it's a 13-inch screen and it just doesn't fit well there, especially if they lean the seat back. And the iPad Pro did.

The Smart Keyboard is really nice. It looks like a nice cover on the iPad if you're using it that way. And yeah, it just works really great. I love the way it folds out and it has a magnetic stopper, grabber thing that just works. But the thing that really got me with it was that I was using the Apple Pencil to take notes in an app called GoodNotes. And GoodNotes is a note taking app for iPad. You can type in it, sure. But the other thing that you can do is you can use the Apple Pencil and it just asks you what ruling you want on your paper. And then you can take your notes and it will actually do OCR on your handwriting and you can do full text search on your notes, your handwritten notes. So, I could just jot down the things that I really wanted to check out and it was good enough to actually go and pull that stuff off, which was awesome. So anyway, if you're looking for something that you can set on your lap and type on without it being as bulky as a laptop or something that travels well or something that you can take notes on like you would a piece of paper that is a piece of technology that you can take with you and blah, blah, blah, blah, then definitely check out the iPad Pro. And I super loved GoodNotes.

One other thing that I'll shout out about that is that yesterday I was at a café and while I was on the airplane where the Wi-Fi just wasn't great my laptop was hanging up trying to pull up the interface where I can write an email in Gmail. And by having the iPad Pro all of that interface work, it doesn't have to load it from a server anywhere. It doesn't have to talk to anything to make that work. So, I would just reply and type it and send it and then it would churn in the background sending that email and I could move onto the next thing. So, it was just a function of having a native interface or at least an interface that ran completely on the iPad and that worked out real nice, too. So, lots of stuff that I like about it and yeah, that's my pick this week.

John, what are your picks this week?

**JOHN:&nbsp;** Well, I've been actually so busy working on the release of my company's product [chuckles] I haven't had a chance to do a lot of outside reading or anything. But I'll throw one in there and that is a topic I have been spending some time on prior to this release. And that's Halogen which is a PureScript library for doing user interfaces. It's basically PureScript's version of React with a little stronger typing. And one of the things they've been working on for the next version of the library is also something I think is going to be important for the next generation of JavaScript libraries which is this notion of incremental computation. In fact right now, a lot of the libraries basically require you to transform your state into the UE and that happens all the time. It happens continuously. And what we really want to say is we have this small little change, this delta state if you will, this little change to our state which could be adding something to a list for example. How do we map that change in state, that addition of an item to a list, into a change in the user interface?

And I actually think that if that problem can be solved in a declarative fashion then that's going to be the next wave of JavaScript libraries. Like what happens after React? React is great, obviously. And we have the FRP stuff already. But what's after that? What's the stuff after that? And the work I've been doing on Halogen around incremental computation and mapping changes in state to changes in the DOM I think is possibly a way to scale up the functional approach to very, very large systems. Like for my company we do data visualization. And sticking a hundred thousand points inside your state and rendering that to a virtual DOM every time something changes just can't happen. So, we need a solution that can deal with those types of situations [inaudible] leak information into the environment. And the only approach that seems promising is one based on incremental computation. So, that will be my sole pick.

And obviously if companies or if people, users, want to check out the source code to a large scale application written in PureScript then that's on GitHub.com. Just type this in. GitHub.com/slamdata. And they can see what it's like to build a large application that has lots of animations and it's very responsive and that reuses a lot of JavaScript libraries in the PureScript language.

**CHUCK:&nbsp;** Sounds really cool. If people want to know what else you're working on or follow you on Twitter or anything like that, what do they do?

**JOHN:&nbsp;** Yeah. So, I'm on Twitter @jdegoes. And I also have a blog, DeGoes.net. And look for an upcoming blog post. I'll post by the end of the week on a successor to that modern FP architecture thing that some listeners might find interesting. Thanks.

**CHUCK:&nbsp;** Very cool. Alright, well we'll go ahead and wrap up the show. Thank you everyone for coming and we'll catch you all next week.

**_[Bandwidth for this segment is provided by CacheFly, the world’s fastest CDN. Deliver your content fast with CacheFly. Visit CacheFly.com to learn more.]_**

**_[Do you wish you could be part of the discussion on JavaScript Jabber? Do you have a burning question for one of our guests? Now you can join the action at our membership forum. You can sign up at JavaScriptJabber.com/Jabber and there you can join discussions with the regular panelists and our guests.]_**


