---
layout: layouts/post.njk
title: >
      042 AiA Dependency Injection and Change Detection with Victor Savkin
date: 2015-05-14 13:00:00
episode_number: 042
duration: 
audio_url: https://media.devchat.tv/adventures-in-angular/AiA042DIandChangeDetection.mp3
podcast: adv-in-angular
tags: 
  - adv_in_angular
  - podcast
---

&nbsp;02:07 - Victor Savkin Introduction

- [Twitter](https://twitter.com/victorsavkin) 
- [GitHub](https://github.com/vsavkin)
- [Blog](http://victorsavkin.com/)

02:30 - [Dependency Injection (DI)](http://en.wikipedia.org/wiki/Dependency_injection)

- “Inject By Type”
- Other Project Use
  - [di.js](https://github.com/angular/di.js/)

06:54 - How Angular Uses Dependency Injection

- Angular 1 vs Angular 2
- Annotations
- Decorating Classes to Become Injectables
- Example
  - [Injectable Class](https://angular.io/docs/js/latest/api/di_annotations/Injectable-class.html)
- Mechanisms in Angular 1

13:06 - Lazy Loading&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;

16:14 - Testing

18:02 - Change Detection

- [Victor](http://victorsavkin.com/post/110170125256/change-detection-in-angular-2)[Savkin](http://victorsavkin.com/post/110170125256/change-detection-in-angular-2)[: Change Detection in Angular 2](http://victorsavkin.com/post/110170125256/change-detection-in-angular-2)
- [[YouTube] Change Detection Reinvented by Victor ](https://www.youtube.com/watch?v=jvKGQSFQf10)[Savkin](https://www.youtube.com/watch?v=jvKGQSFQf10)[@ ng-conf 2015](https://www.youtube.com/watch?v=jvKGQSFQf10) 

24:33 - Components & Immutability

- [immutable-js](http://facebook.github.io/immutable-js/)

28:08 - Scope

- [zone.js](https://github.com/btford/zone.js/)
  - [[YouTube] Zones by Brian Ford @ ng-conf 2014](https://www.youtube.com/watch?v=3IqtmUscE_U) 
  - [angular/zone.js](https://github.com/angular/zone.js/)

30:28 - Binding

- Action Phase/Control Phase
- Production Mode/Dev Mode 
  - [Victor](http://victorsavkin.com/post/114168430846/two-phases-of-angular-2-applications)[Savkin](http://victorsavkin.com/post/114168430846/two-phases-of-angular-2-applications)[: Two Phases of Angular 2 Applications](http://victorsavkin.com/post/114168430846/two-phases-of-angular-2-applications)&nbsp;
Picks

[My Story by Elizabeth Smart](http://www.amazon.com/gp/product/1250055458/ref=as_li_qf_sp_asin_il_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=1250055458&linkCode=as2&tag=chamaxwoo-20&linkId=PJM2P3MKRYS372ZU) (Aaron)[Shawarma](http://en.wikipedia.org/wiki/Shawarma) (Joe)[Home](http://www.imdb.com/title/tt2224026/) (Katya)[Mulan](http://movies.disney.com/mulan) (Katya)[How to Win Friends & Influence People by Dale Carnegie](http://www.amazon.com/gp/product/0671027034/ref=as_li_qf_sp_asin_il_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=0671027034&linkCode=as2&tag=chamaxwoo-20&linkId=WDNUHBF76J7TC4DS) (Chuck)[WorkFlowy](https://workflowy.com/) (Chuck)[Habit Stacking: 97 Small Life Changes That Take Five Minutes or Less by S.J. Scott](http://www.amazon.com/gp/product/1499341474/ref=as_li_qf_sp_asin_il_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=1499341474&linkCode=as2&tag=chamaxwoo-20&linkId=3MLNVCV3VIJVD5AO) (Chuck)[Mini Habits: Smaller Habits, Bigger Results by Stephen Guise](http://www.amazon.com/gp/product/1494882272/ref=as_li_qf_sp_asin_il_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=1494882272&linkCode=as2&tag=chamaxwoo-20&linkId=B4LENVVTK6ERPEYP) (Chuck)[Android: Netrunner Card Game](https://www.fantasyflightgames.com/en/products/android-netrunner-the-card-game/) (Victor) Mechanical Keyboards (Victor)



### Transcript

 **CHUCK:** I'm getting heart palpitations.. But I can't leave!

_**[This episode is sponsored by Hired.com. Every week on Hired, they run an auction where over a thousand tech companies in San Francisco and New York and LA get on JavaScript developers providing to put the salary and equity upfront. The average JavaScript developer gets an average of 5-15 introductory offers and an average salary of over $130,000 a year. You just can either accept an offer and go right into interviewing with the company and neither with that any continuing obligations. It's totally free for users, and when you're hired, they'll also give you a $2,000 signing bonus as a "Thank You" for using them. But if you use the Adventures in Angular link, you'll get a $4,000 bonus instead. Finally, if you're not looking for a job but know someone who is, you can refer them to Hired to get a $1,337 bonus if they accept the job. Go sign up at Hired.com/AdventuresinAngular.]**_

_**[Does your team need to master AngularJS? Oasis Digital offers Angular Boot Camp, a three-day, in-person workshop class for individuals or teams. Bring us to your site or send developers to ours -- AngularBootCamp.com.]**_

_**[This episode is sponsored by Wijmo 5, a brand new generation of JavaScript Controls. A pretty amazing line of HTML5 and JavaScript products for enterprise application development. Wijmo 5 leverages ECMAScript 5 and each control ships with AngularJS directives. Check out the faster, lighter and more mobile Wijmo 5.]**_

_**[This episode is sponsored by Digital Ocean. Digital Ocean is the provider I use to host all of my creations. All the shows are hosted there, along with any other projects I come up with. Their user interface is simple and easy to use. Their support is excellent. And their VPSes are backed on solid-state drives and are fast and responsive. Check them out at DigitalOcean.com. If you use the code “** __**angularadventures**__ **” you'll get a $10 credit!]**_

**CHUCK:** Hey, everybody! And welcome to Episode 42 of the Adventures in Angular show. This week on our panel, we have Aaron Frost.

**AARON:** Hello!

**CHUCK:** Katya Eames.

**KATYA:** Hi!

**CHUCK:** Joe Eames.

**JOE:** What's up!

**CHUCK:** I'm Charles Maxwood from DevChat.tv. This week, we have a special guest and that's Victor Savkin.

**VICTOR:** Hello!

**CHUCK:** Do you want to introduce yourself really quickly?

**VICTOR:** Sure! I'm Victor, and I work on Angular 2 at Google. The Angular, of course, was very small so everyone sort of had a chance to work on pretty much every parts of the framework. But the two things I worked most are Dependency Injection and Change Detection.

**CHUCK:** Very cool. We're all pretty excited about Angular 2, so maybe, we should just jump right in!

**VICTOR:** Sure!

**CHUCK:** So, when we're talking about Dependency Injection, I mean, I know the pattern, right? You know, you pass in your sort of constructor or your object, your class, your factory, whatever you want to call it. And it does its thing to create instances or to act as a singleton to get work done.

**VICTOR:** Basically, yes. Dependency Injection is an overloaded -- tronic means to pattern -- and it also means, usually, some sort of framework or a library that allows you to implement its part and alloc easily.

In Angular, we embrace the pattern. We also provide the module that allows you to implement the pattern.

**CHUCK:** Alright. What are kind of the details to understand the library?

**VICTOR:** Okay, cool! First, I want to say why the patterns are important because, often, onto small applications, they sort of don't see the value in the pattern. But the value is that you can depend on interfaces on like abstract classes or abstract ideas rather than on concrete types. And because you can do that with Dependency Injection, it leads to more [incomprehensible] of code so you don't depend on concrete types which enables the stability and also the other great things. That's why we believe in it. We want to enable us to stability. And as a result, we are providing this module and sort of rely on this pattern.

In Angular 1, we have a few ways to inject dependencies into your directives or services. Some of the dependencies I injected, by name. If you want to inject the service into your directive, you do it by name. But some other dependencies I injected, by usually using some other mechanisms. For example, if you want to inject an element or attributes, you don't do it by name. It's like the sort of argument in a link function or whatever. So, we have like several mechanisms that allow you to inject dependencies into directives.

In Angular 2, we simplified it. The way we do it in Angular 2 is we have one single mechanism. Everything you want to inject any dependency, you always inject into your constructor and you inject it sort of by type. So, it doesn't matter whatever it is. It can be a global service like a singleton, or it can be an element, or some other information like other directives around you -- you always do it the same way, you inject it into your constructor. So the DI Module in Angular 2 provides its facility. And, you don't have to worry about it so you don't need to know how the module works. What you want to express to the developer, you just to say that you want to have that service injected into your constructor. And Angular 2, like magic, it will find the service and will give you one instance. Does it make sense?

**CHUCK:** Hmm-mmm..

**AARON:** Yeah!

**JOE:** But, when you say inject by a type, what do you mean by that?

**VICTOR:** Okay, the way it works in Angular 2 is, all injections is actually talking base. So, you can provide their value and say, "This object, I will give it a certain name or identity. And I will call it this." And then, next time I did somewhere else, I will ask for the same thing and I will be given that object.

But since we like classes and we like TypeScript and all those sort of things, usually the identity is also the same that you want to inject matches the type of that thing. Imagine that you come like a weather component and you want to inject the weather service, you would just say like, "I want to inject the weather service that functions/class/type," and it will be given to you.

So, this sort of the default behavior. But, you can overwrite it when this behavior is not sufficient or is not powerful enough.

**CHUCK:** I'm wondering with the Dependency Injection library in Angular, is this something that you could use in other projects?

**VICTOR:** Yep! Basically, currently, we have di.js, which is node to library because in Angular 2, it's a separate and extraordinary DI library. And we have a DI module in Angular 2 and the Angular/Angular repo.

So, we are going to extransit DI module from Angular/Angular repo and make it a separate, an independent project so you will be able to use it without Angular itself. But currently, it's inside the repo so you can try to do it but it requires some many of work.

**AARON:** So we got a company called Domo, and one of the guys on our front end, he's wicked sharp, his name is Merrick. He actually has our mobile web app running and he's got di.js running with React so it is something that's portal outside like the Angular sphere of things that you can use it with other libraries, too. He actually really, really likes it. He's written a couple of blog posts about it and they're very interesting. So, yeah.

**VICTOR:** Yeah, we understand the value of DI module being like external so people could use React or beg one or whatever. They should be able to use that, and will happen in the near future.

**CHUCK:** Do you want to talk a little bit about how Angular uses DI? I mean, we've talked a little bit about the patterns and things like that, but..

**VICTOR:** Sure! I can talk about that. The way Angular uses DI is as follows: when Angular see the component in &nbsp;your template, it will mind the selector of the component and it will know that it means to instantiate that you call type of component or that. Then Angular will check what kind of dependencies that component needs because the component is being instantiated by Angular so you're not in control, yes? The Angular will go through all constructor arguments of that component, will sort of identify all the dependencies. And those dependencies can be like an element or some other directly around that component or a service.

Angular go find all these objects for that component. If it's a directive, it will find its directive. If it's an element, it will give the element in which the component is positioned. And if it's a service, it will ask sort of like the injector object which DI provides for that service. So, it will collect all these objects and will instantiate that component to use all those objects.

**JOE:** So, these are things that are injected into constructor of the component, right?

**VICTOR:** Yup! The only way to inject stuff is into the constructor.

**JOE:** So, this isn't the same way that it worked into Angular 1? In Angular 1, it did the little magic of taking the function to stringing it, and then looking at the names of arguments, that was the most common way. Like you said before, there are some functions where stuff was just injected by a position like the link function, for example.

**VICTOR:** Yup!

**JOE:** So, it's not working that way, correct? That's not how the component detection go?

**VICTOR:** That is correct. Yeah, it is correct. We don't want to rely on that thing anymore because it's sort of fragile and if you minify stuff, it doesn't really work. They are all the problems with that approach.

So instead, if you unattained, basically, your components, we have types, and Angular use those types to figure out what to inject. The types, like the minification-friendly, you won't have any issues with minifications. The name of the argument, basically, doesn't affect what to be injected. It's the types of the arguments that affect what to be injected.

**JOE:** So, is this using the annotation specification that Angular sort of added and was doing in out script then merged into TypeScript, and now Babel has a little support for it and then they worked with the Ember for sort of the unified thing that they want to get into ES7, is that what we're talking about?

**VICTOR:** It is related, although it's not direct to that thing. It is related. Basically, the way it works currently is that every class or function, I will have an extra meta property, where we store information, that meta information about its constructor. So even in ES5, when you don't have annotations or just plain ES5 so there's nothing there, you can still define that property on that function and Angular will look at that property and it will figure out what the function needs.

So iif you have TypeScripts or if you have all these newer languages, then the syntax would be nice because these information will be in place. But, we don't depend on those annotations. Those just provide nicer syntax, but you can use same stuff in ES5 or in ES6.

**JOE:** Okay. So, if you are authoring in ES6, then you would use those annotation syntax, right? But, if you're authoring in ES5, then it's just a different property that you add to the function?

**VICTOR:** Yup!

**JOE:** Is it added to the constructor function? Or, is it added to the class?

**VICTOR:** If you're writing in ES5, you're probably just have constructor functions because you don't have classes so you added to that constructor function.

**JOE:** It's like a special property name?

**VICTOR:** Yup! I think, currently it's called "Parameters", or something like that.

**AARON:** Okay.

**VICTOR:** So, it's actually very easy to do. And you can provide like a syntax sugar to make it nicer looking. But, there is nothing that really debounce on ES6 or TypeScript. So it can work in ES5 very nicely.

**JOE:** Let's say I write in ES5 class, it's just a constructor function called Foo, how do I decorate my class to become an injectable? Because not all functions all want to have injectables, so what is the decoration look like?

**VICTOR:** Okay, cool! There are two concerns here. One is you want to go your class to become an injectable; and the second one, you want to inject stuff into it. So if you want you class to become an injectable, you need to register it in a DI system. It doesn't happen magically. You need to explicitly say you want this class to be injectable in your application. The way you do it in Angular 2 is, components allow to define what is injectable in that component in a few and all its children.

So basically, component will say that, in my subtree essentially is, I will provide the fallen injectables. Let's say you have, again, weather service and weather component, components can say, "In my subtree, any component can inject a weather service. This is a weather service, and this is the implementation of weather service. So if anyone asks, you'll get this one."

**JOE:** Okay. So, I looked up a few Angular 2 examples and played around with it a little bit, and I haven't seen yet the example of somebody registering a service like you're talking about. Is there examples that are out there on the web or people are doing this?

**VICTOR:** I think so. I think, even if you go to Angular/Angular examples, I think, we use [incomprehensible] as that. Because basically, every time you need to inject anything, you'll have to do it this way. This is the only way to do that. So, I'm sure, there is an example. I can provide a link, maybe, so we can attach it to show notes or something exist with an example.

**JOE:** Great!

**CHUCK:** I'm thinking about Angular 1 versus Angular 2, and I'm trying to decide if this makes things easier or not?

**VICTOR:** Let me put it this way, it makes things more flexible, that's for sure. And I can talk both issues with Angular 1 injections because there are a lot of issues when you go into like multiple keyings or Lazy Loading. I think, in my view, it simplifies it because you have a single mechanism to deal with all your injectables instead of having multiple mechanisms. Having a single mechanism, for me personally, is just easier to reason about.

**CHUCK:** So, what are your multiple mechanisms in Angular 1 then?

**VICTOR:** In Angular 1, like if you want to inject an element, you need to understand that it will go to a link function. And if you want to inject a service, it goes to a separate place. So when you're directly finishing objects, there are multiple places where injectables come like sort of being injected. So when you test, you need to be aware what's happening. What is now, when you instantiate a component, at least you need to know it just goes into the component if you don't need to know anything Angular specific like when exactly it's going to be provided or in what way. There's only one mechanism, one place, to put all injectables in place.

**AARON:** Cool! You actually said something that this show is not about, but I want to take a minute to ask you. You just said something about Lazy Loading, which that's not a real thing, you know. Can you talk about that story? Because that kind of sounds interesting.

**VICTOR:** Okay, I can talk about why Dependency Injection Angular 2 is better for Lazy Loading.

**AARON:** Okay.

**VICTOR:** Because in Angular 1, one of the problems with Lazy Loading is how Dependency Injection is implemented.

**AARON:** Okay.

**VICTOR:** And to understand that, let's start with this: DI, Dependency Injection, in Angular 2, is hierarchy call. What I mean by that is, that instinct time in one like both objects of injectables, you actually have a tree of injectors. So every component can say, "You know, like every in downstream, can get this extra object." So, basically, you're component tree, in a way, matches you injector tree, if that makes sense.

What happens, if you have an application, when you want to Lazy Load certain parts of that application -- let's say when &nbsp;you navigate around, because when you navigate around using a router, you want to Lazy Load certain parts of the application -- if you have one injector like in Angular 1, one global both objects, watch what will happen. You see, if I go to route A and then route B and then route C or whatever, let's say route A declares a bunch of services, should those services be just merged into my global one single injector? If it happens, then being on how I navigate my application, I might end up with a different set of services. So I may go like A B C and then A D C and C will behave differently depending if I went there through B or through G, and this because you have only one place to put all these services in Angular 1.

In Angular 2, that's not the case. In Angular 2, when you Lazy Load stuff, what happens is, you attach a child to the injector so you don't affect anything else in the application. So when you Lazy Load a route at certain parts of the application, you define service only for yourself inside that application, but not outside. So it means a Lazy Loading can be implemented in a safe way. Regardless of how you navigate around route C, the end result will always have the same set of injectables and will behave the same way.

**AARON:** Okay, cool! That's interesting. I'm excited to see that kind of support like majorly in Angular, that would be cool!

**VICTOR:** Yeah. One of the goals, actually, we have is that, for this type of injection [incomprehensible] injection is, Lazy Loading. We want to enable Lazy Load. And to do that, we need to be able to create a tree of injectors rather than a single injector.

**AARON:** But that's all transparent to us, to like the regular coder. It's all taken cared of inside of Angular. True?

**VICTOR:** Yeah, that is correct.

**AARON:** Okay.

**VICTOR:** So if you are the programmer, if you want to do it like Angular 1 way with a single injector against it, you'll do it. Then if you Lazy Load, you don't need to do anything special and, let's think about it -- I mean, it's probably a good idea to be aware what's happening, but there is no extra work required from the developer.

**AARON:** Okay, cool! That's good. I think, if you had to know about it, that would likely increase the buried entry. And I think, that's nice that you don't have to know about it, but it's good to eventually get in there and figure out what's going on. So, that's a cool addition to the platform. I like that.

**VICTOR:** Hmm-mmm.. Cool!

**CHUCK:** Now, one of the things that I've seen Dependency Injection used for is basically to provide a simple interface for injecting test classes or, essentially, mock objects that short-circuit certain things so that you can test behaviors without testing the entire stack.

**VICTOR:** Yup.

**CHUCK:** How does this Dependency Injection change or affect the testing story with Angular 2?

**VICTOR:** I think that this story go with what you mean, sort of the same in a sense that in Angular 1, it is possible to sort of replace anything in your application in the framework because it haven't realized Dependency Injection. In Angular 2, it will be the same. Meaning that, you can replace any part of your application, and your service in your application could use a different service when you test it. And that's actually what we do internally when we test Angular 2 itself; we use DI and we can swap like a template loader, for example, with a dummy template loader because we don't want to go all these network and fake some template. So, it will be the same.

**JOE:** One of the things that is nice in a compiled service side language when you're testing is using constructor injection. When you go and you test the class, you create the class mainly in your test; you just provide dependencies for it.

With Angular 1, testing it was not this similar, depending on the sort of like controllers, for example. You just had to create a little object that had properties, that had the right names, and then you tell that, "Hey, use this," and then that's what it will use. Is that pretty similar in Angular 2?

**VICTOR:** Oh, it is better in Angular 2. This part is better because all the dependencies go into a constructor. If you want to test that objects in like isolation, like in the View Isolation, it's that what Angular at all, yes? Then you can just mute, like instantiate an instance to that class, and you just pass all the dependencies directly into the constructor. So, it is better. It is the same as in Java or in many like service side language.

**JOE:** Cool! I'm really interested to start talking about Angular 2 Change Detection.

**VICTOR:** Alright.

**JOE:** Can you give us like an overview of what's different about it, new, and..

**VICTOR:** Cool, I can do that. Basically, the goal of Change Detection is to sort of power data bindings. When you have data bindings in your template, like something you should check if the value has changed, if the expression changed, and update directly some components and the DOM. That's what Change Direction does. It goes through everything and checks everything. If it detects changes, it updates the target -- the DOM or the directive.

What's different in Change Detection, in the Change Detection Module in Angular 2, there's a bunch of things. First toward, it's much faster because maybe [incomprehensible] with everything and it is faster for a couple of reasons. I can talk about it why it's faster, if you're curious.

**JOE:** Yeah, please.

**VICTOR:** Alright. It is faster for a few reasons. Basically, if you think about in Angular applications, there's lots of bindings in it, like thousand of bindings, that if you fall on Change Direction, it can be expressed as sort of the number of bindings in your application times the time it takes to check an individual binding. Because basically, Angular, every time a browser of that happens, it go though every single binding and it checks it, that's what happens.

And, there are good reasons why we have to do that. Because in Angular, we allow you to use any mutable simple JSON-like object, you can use it. And if you do that, then we don't have enough guarantees to be smart; we need to basically go and check everything. Because there are two ways to make this process faster. The first way is to say, "Let's just make, check, and binding faster". In figure B very smart, think of it very hard and make check on individual binding faster somehow. And the second one is to say, "Let's be smart about what we check. Let's not check every single binding every single time and trying to be smart about that." That actually works on both parts. So we may check an individual binding significantly faster in Angular 2 because B is sort of understood how virtual machines work. Mostly, [inaudible] how virtual machines work, and he told me and we sort of figured it out. And why faster is, if you imagine that binding in Angular 1 that looks like this, like person that name -- let's say we had person that named binding somewhere -- the way Angular 1 view a value of its binding, to get the value of it, is it will get a getter for person. So to get the person from some point, from school, a value to a getter for me, and it will involve that better to get the name of the person, which is pretty cool, basically, for you to be able to get a getter for every property. The issue with that is, virtual machines, they don't like this kind of call because those getters become polymorphic on occasions. There are different shapes of objects that go into those getters, virtual machines cannot optimize this kind of call very well.

In Angular 2, we do a completely different thing. What we do is we look at all the bindings in your component, we'll look at the template, we'll analyze it, and we generate the function at run time behind the scenes. That sort of checks your template on your component, but beside getting those getters. Basically, with generator, function that looks what you would write by hand if you go to implementation for that component, it would generate a function bare component. Every component has its own Change Detection function. It happens at runtime so you don't need to worry about it.

What it means is that, virtual machines can figure out what's going on because they know that this component will going to have a fewer person. They know that person is always of type person so they can be smart about it. It allows us to basically replace most of the polymorphic holes we have in Angular 1 with monomorphic holes which are extremely fast. And we're talking about like 5-10 like faster for every single binding your application regardless of what you write. So you're writing your application and become 5-10 like faster just because we are being more smart and more aware of how virtual machines actually work.

And the second thing we do is, we're trying to no check every single thing, every single time. To do that, we ask the developer to prepare us extra guarantee so you, as an application developer, can say something about the objects you use in your component. You can say, for example, that those objects don't change and like, "Oh, they don't change, nice! We don't need to check them". Unless you replace the whole object, you don't need to worry. And, we can say, "You know, those objects are like bag, one observable models". So, they will push you in notification to be changed. And Angular can be like, "That's great because I don't need to check the template again and kill one of those objects that changes."

That's the second part of what we do. The first part is, basically, we're being just passed for every single binding. The second part, we allow the developer to give us more information about what kind of guarantees their models provide, and then we use those guarantees to not check the same thing over and over again when it's not needed.

**JOE:** Let me see if I understand this, in order for me to help out Angular 2 to be faster, I need to either use an immutable in certain places, and then telling there, too, "Hey, this here is object, this is immutable." Or, I need to use some kind of an observable -- is it any kind of an observable object? Or, is it have to be just the observables that are in?

**VICTOR:** It is actually any kind. We provide a generic mechanism. So you write sort of a small adapter to tell Angular how observable works, but it can be any type of observable.

**JOE:** Doesn't a Rally have a very similar mechanism to it?

**VICTOR:** It is a similar mechanism, so the granularity is different. Our granularities per component, which is very similar to how, for example, React does it. And I think, the granularity in Rally is per binding, as far as I know.

**CHUCK:** One thing that I'm kind of gathering from this is that, in Angular 1, if I wanted the sort of Change Detection and update something else in my template, I had to set up an ng-model and then tell it that I had to care about before those places.

In this, it sounds like it's more automatic. Or, am I completely missing the point?

**VICTOR:** I think, there are two points here. The first one in Angular 1, you do use ng-model if you want to get the data sort of from the DOM back to your component. So, if you want to push data from the component to the DOM, then you want to get the data back.

**CHUCK:** Right.

**VICTOR:** So basically in Angular 1, those two concerns of sort of merged together, and it's hard to see like when you're pushing data to the DOM and then when you're getting the data back. In Angular 2, those two concerns sort of a lot more explicit.

So, there are ways to do with ng-model at Angular 2, but those ways both on top of Change Detection. So it's not the Change Detection itself, you have an extra module which you call forms. The goal of that module is to provide facilities like ng-model.

**CHUCK:** Okay.

**AARON:** Cool!

**JOE:** So, how do you tell Angular that a piece of data that you're using is immutable?

**VICTOR:** The way you do it is very similar to the way you do it, for example, in React. You're saying that this component depends only on immutable data. So in your components annotation, you can specify that in depends on immutable data and Angular knows that this component, all its models, at least all its models are immutable. So you can still update the component, you can either replace the model, but you provide the guarantee that the object you'll receive will not change..

**JOE:** And do you have to do that for all models within the component? You can't save some models within the component or, immutables or not, as be all models as in the component?

**VICTOR:** Yes. Currently, it has to be like the whole component becomes sort of immutable aware. So that's not like an individual model, but you're saying if I have a large application -- and because components are also [incomprehensible], components are supposed to be very small.

**JOE:** Right.

**VICTOR:** So the way your out components, you're supposed to put like a few lines of calls and, "Here you go and have a component". So, components granularity, that's actually not the bat and like the [incomprehensible] will actually show that. In their case, it works per component and it works nicely.

**JOE:** I want to clarify this. You said components used to be very small. But components can also be very large because they can collect up a whole bunch of other smaller components, right?

**VICTOR:** That is correct. Sort of the whole application is a giant tree of components.

**JOE:** Right.

**VICTOR:** You start with very small components, and on every single level, you're supposed to have small components in a sense that it doesn't do much except to delegate to other components, and so eventually, you have your application.

**AARON:** So, in any given component, you say, "This component's data is immutable". Now, in JavaScript, correct me if I'm wrong, there isn't really a way to actually force data to be immutable because it's just JavaScript object. So in that case, you just have to make sure that you'll never mutate the data incorrectly.

**VICTOR:** Yup! You provide this guarantee.

**AARON:** Right.

**VICTOR:** For example, let's say you receive an immutable at least from Immutable.js library, you can still mutate stuff around because the JavaScript language is so flexible. You can still do crazy stuff. But you're saying, the way the little [incomprehensible] and the way I use it is alright, yes? Trust me, you don't have to change. But if immutable at least, for example, provide an extra guarantee, which I think I'm going to do, the guy behind Immutable.js, is to provide a guarantee that the least constructed is truly, deeply mutable. We can detect those kinds of things automatically, and we can tell, "Well, we know that Immutable.js deeply mutable at least that good." If we do that, we would have to ask you to annotate your components.

**JOE:** Are you talking about Immutable.js that is done by the Facebook team?

**VICTOR:** Yup, yup.

**JOE:** You're talking about that one?

**VICTOR:** Yup.

**JOE:** Is that a library that you anticipate people will end up eventually using within Angular 2 for their data starts just that the one that make immutable?

**VICTOR:** I personally like its library a lot. How much it was going to happen because like I don't know what people will choose. But, if I was picking a library, I would pick its library.

**AARON:** Yeah. I've seen some blog posts recently where some people were kind of showing some performance they got by using Immutable.js, and a couple of things that have changed in order to use it. It was pretty awesome! The performance gains they're able to get out of it and like to explain, they went from like an n+x to like a zero-cost on a check for an entire list of a thousand things, you had a zero-cost check on it because you knew the list was immutable, the length all I had to check was the length at that point, which is super simple.

**VICTOR:** Yup, exactly. That's basically what we want with Angular, like, all the time.

**AARON:** I think you'll see a lot of projects come out with di.js and Immutable.js and all these separate things kind of coming into defaulting your app, which is cool! Which is very cool.

**JOE:** I have a different question. I know that the concept of $scope is disappearing. And in Angular 1, if I did something in a JQuery plugin or with like a WebSocket that was outside of Angular and I needed now Angular to apply that, I would call a $scope.$apply, right?

**VICTOR:** Yup.

**JOE:** How do you $apply without a $scope, how do you tell Angular to do its thing in Angular 2?

**VICTOR:** Angular 2 is good on top of Zone.js. It's basically a library that bring forth put together. What it does -- basically, let me prime you first. If you know what [incomprehensible] bindings are, in the least for thread locals and Java or domains in node, that's basically what's on their .js, it's just slightly different. What it allows you to do, they allow you to intercept when you enter or leave the zone. When it was strapped in Angular, Angular can say, "You know, I'm going to start a new zone - Angular Zone". So, every time [incomprehensible] any AsyncOperation from within the Angular, it will be [incomprehensible] into that zone. So when that AsyncOperation is done, Angular will know. So if you, for example, create message to pRequest from Angular using some sort of part of your library, Angular will know that you create that request. It will know that you scared with that callback, when that callback is done, at the end of that the intern, Angular will run digest and flourish the changes.

So in theory, you shouldn't do anything. Everything should just work sort of automatically for you. No one need to plan anymore, basically.

**AARON:** Okay. That's good because, at least, like the things that I've been in, people are really like irresponsible with the $scope.$apply. Like the other day, I saw this thing coming back from a WebSocket and it had like, let's say it had 20 things in it like it was an array, and they processed each of the 20 things. And in the processing that had an AsyncCall in it, and after AsyncCall they reapply it so that they would apply 20 times for this one array which was like crazy that they were doing something like that. But you're saying, Angular 2 is going to like manage that force so you're going to save us from ourselves a little bit, which is awesome.

**VICTOR:** Yeah, you shouldn't worry about it. Obviously, there might be some issues currently because it's still in the works. But the goal is that you should be able to integrate with any certain part of your library into AsyncOperations and it should just work.

**JOE:** The other thing I'm interested in, and it has to do with Change Detection a little bit is if you have a binding, and that binding is some kind of like a calculated value, like full name and it's composed of the first and last name, in Angular 1, you have that maximum 10 loop scope where you ran through and changed the first name, but the full name had changed and it had the text that you run through again and decide, "Oh, full name has just changed," so it goes to the second. And then it goes through a third thing, sees it as nothing has changed, that third digest, nothing has changed. How does that work in Angular 2 to deal with this calculated bindings?

**VICTOR:** Alright, it is a lot more explicit. The feels toward Angular 2, same as in Angular 1, change detection rounds at the end of the VM internal. This is the first important thing to understand.

**JOE:** Wait, say it again. Change detects rounds when?

**VICTOR:** At the end of the VM internal. So basically, all micro tasks are done when browser is almost ready to paint. Change detection rounds, flashes all the changes, and then the browser paints, like basically update a View. In Angular 2, what's also very important with that are two way bindings that you see in Angular 1. They look more explicit so it have the square brackets that indicates a data goes into a component, and then you have parenthesis in the template syntax that indicates the data comes out with component. So those two way bindings are a lot more explicit.

And the two phases in Angular 2 are actually like separate, so you still have to way binding behavior, but the two phases are separate. So it feels to be those with digest phase when we flash all your changes from your Model onto the View. So we go all through all square record bindings and we update all the dormant at the component. And then when an event happens, like for a example a click or a key app or what not, the second phase round, which is called an Action Phase. That Action Phase updates your Model. So if you have sort of this giant loop, you do the flash, then if something happens somewhere, it will beat your model then, and other flash will happen.

In Angular 1, it's not like that. In Angular 1, it's sort of interlift. You don't know what's been updated when stuff changes. What it means is that, when you have stuff like full name, the way it will happen is it will go through the template, it will see the full name, which was first name and last name. It will get the values like the current values of first name and last name, it will calculate the full name, it will set the full name, let's say in the DOM somewhere else or in the text node. Then if something changes, like the first name changes, it will be another event. It will be another browser event. So Angular 1 changed it implicitly, it will have to be another browser event. And when the browser event happens, it will apply change to its Model as in another flash phase or a digest phase, it will happen. They put it in here that the loop that are used to be in Angular 1, is not present anymore. So we don't run into every single stable because we assume, because we don't change the model ourselves, and we actually guarantees all through the things the way they change that the system gets stable after a single pass. So because we don't have the loops in our sort of change detection graph anymore, this isn't get stable after a single pass so it needs for this multiple iterations of the loop, it's not there. So we do it only once, and then if something changes, it will be another path through the tree, a change detection tree, but it's a separate VM turn as one part of the same loop.

And also, it's a bit confusing. It will be easier to draw on a whiteboard and show how it all interacts. The bottomline is, the loop is not there anymore.

**JOE:** I know you have a blog post on your blog about Change Detections in Angular, does that kind of go over this?

**VICTOR:** Yes, it does go over this. I have a bunch of blog post the covers this particular topic because I think, it's an interesting topic so I can link those. I actually gave a talk at ng-conf that covers this kind of another detail, but sort of touches in this.

**JOE:** So if you have some variable, you can still bind the output of a function to a text node, right?

**VICTOR:** Yup!

**JOE:** Can you have two different functions that you can shoot yourself on the foot as it calls one function to get the data to bind out and actually mutates some value that a different function depends on, and then when you call that function, it mutates the original value back or the value on your first keys. &nbsp;Can you set on a foot that way everything there with you?

**VICTOR:** That's a very good question. Basically, as I said, there are two phases in Angular 2: The Action Phase, when an event happens. And in Action Phase, you can do whatever. It's really like your application can update anything you want.

Then the next phase when Angular go through your component tree and update the DOM nodes and directives, that phase is Control. What we are trying to guarantee is that you can update your children in that tree. So our components can update the components that it contains, but it cannot update your parents. So what will happen into Dev Mode, because Angular rounds in two modes: Dev Mode and Production Mode, in Dev Mode, Angular will go through the tree and then it will go through a tree again, making sure you didn't change anything. Because if you change anything, Angular will know and it will tell you that it's like you're changing your parent basically; you're violating this contract we had with you.

In Production Mode, we don't go to the cheat wise because it's obviously slower. In the Dev Mode, you're going to see exceptions, you're probably good. But are trying to guarantee that because when you have this kind of model, first of all, it's much easier to reason about what changes during this automagical like phase. And also, it's a lot like performing.

**JOE:** Right. Two things interesting there: One is, in the Dev Mode, if you do go through the second time and see that something has changed, does it actually like throw an air?

**VICTOR:** It throws an exception.

**JOE:** It throws an exception. In Angular, it's like not working, and you see, "Oh, my site is broken," and you're going to look at your console and figure it out?

**VICTOR:** Yup. If you do it in your unit test or like when you're writing your end to end test, you should see an exception or at least a binding that will tell you that this bind, this component, something changed when I went like the Angular, when there's second time. Please make sure you don't change your parents.

**JOE:** Right. And then the other thing that I've -- this is news to me -- you said there's a Production Mode and Development Mode, so is there like a switch on Angular 2 as they are like, "Go ahead, act in Production Mode?"

**VICTOR:** Okay, the way it works, because we have those type annotations for TypeScript, we sort of have to have two modes. Because we refine those type annotations at runtime, it was actually pretty expensive. So we don't want to do it in production; you want to get their feedback while you go up, but you don't want to slow your application by a factor of like 5 when you're onto production. So because you have Dev and Production Modes just to support type annotations, we decided to use the side view of Dev and Production Modes when you allow for Change Detection for other things, too. So in Dev Mode, we give you more information. You got exceptions, long stack traces, and all sorts of things which you don't want to do in production because they're expensive. And the way you do it is you have two different Views because you actually need to go to Angular. Like when you do your application, you specify the right flat by specifically specifying, I want to build it in the Dev Mode, or I want to build it in Production Mode. And depending on how you build it, you will see all those extra stuff all you want to see. Does that makes sense?

**AARON:** Yeah.

**JOE:** That's very interesting.

**AARON:** It is very interesting.

**JOE:** I think it makes sense like dart has like a summer thing, right? You have this right time and Dev time type system and overhead, and then it compiles, and it's a different system for how many times to be optimized.

**VICTOR:** Yup, exactly.

**JOE:** That's cool! I like that a lot.

**VICTOR:** Yeah, I think it's a good idea because you want to give as you go for a lot of like help, but you don't want to slow down your application when in transit to production.

**JOE:** Yeah, but it's okay to slow them down during dev time...

**VICTOR:** Yep, exactly.

**JOE:** Actually, a really cool idea.

**VICTOR:** Yup.

**AARON:** Hmm-mmm..

**JOE:** Hmm, I like that.

**AARON:** It is awesome. I'm still curious like how exactly do you tell it now that I'm in Production Mode?

**VICTOR:** Basically, the way we do it currently is, we have a special help or function that will try to do an invalid type assertion. It will try to assert, basically, extreme to a number is. In Dev Mode, it will throw because the string is not a number. So we're like, "Okay, you're probably in the Dev Mode," just because type assertions don't work in Production Mode as those type assertions I made with by how we compile your obligations. So you can compile in two models.

**JOE:** That's cool. I like that. That's very cool.

**CHUCK:** Alright, well, anything else we should jump on before we get to picks?

**JOE:** This is a really deep episode like I was like struggling.

**CHUCK:** Yeah, I'm going to have to go back and like relisten and fiddle with stuff.

**JOE:** Victor, you did great like you did a lot of non-stop explaining. You did a really good job. Thank you for coming, man.

**AARON:** Yeah, thank you!

**VICTOR:** Yeah, I will provide with links so hopefully, if you like listen to the episode, then there is old links. You'll have enough information to be like, you know, to understand what's going on.

**JOE:** Yeah, that would be awesome.

**AARON:** Yeah.

**CHUCK:** Alright, Aaron, you got some picks for us?

**AARON:** Yeah, I'm assumed to a pick today. It's a book, I can't stop reading it. It's like one of the most intense books I've ever read. It's a book about a little girl who is kidnapped, her name is Elizabeth Smart, and it's called "My Story". I'm actually doing an audible book and it's very interesting. I've never read a book where it was a biography and the person who it was about was actually doing the audible in there and reading. So she narrates her own book and her experience is horrifying. As a father of a daughter, it's just like... I can't... It's like one of the most intense scenarios ever, like it's really crazy. But it's a really good book. She's got a lot of heart and the way she comes through it all is just kind of inspiring. It's called My Story by Elizabeth Smart. That's my pick.

**CHUCK:** Yeah, I read that book, too. It's pretty heart-wrenching. And I hate thinking that I wish ill on anyone, but that one got me pretty close.

**AARON:** Yeah.

**CHUCK:** Yeah, but at the same time, I mean she's a well-adjusted adult, she's married, she served a Mormon mission so it sounds like she has dealt with what happened, and so it's inspiring in that way. But, yeah...

**AARON:** Yeah.

**CHUCK:** Joe, do you have some picks for us?

**JOE:** You bet! So I just spent the week end in New York, and I ate a lot of delicious food. One of the foods that I ate, which I sometimes eat here locally and Utah was a various place you can get it -- but in New York, it's just 10 times better with "Shawarma". And I will admit, the only reason I ever tried Shawarma was after the first Avengers Movie.

**KATYA:** Did you go to that actual shop where they filmed Francine, or?

**JOE:** No, no. It's like in Birkwood or something. The scene in the shop is not filmed in like actual location in Manhattan, I think. Anyway, Shawarma is awesome. When I had Shawarma, it was delicious. So if you've never had Shawarma before, find a place near you and go eat Shawarma because it's awesome. That's my pick.

**CHUCK:** I don't even know how to spell that.

**JOE:** S-H-A-W-A-R-M-A

**KATYA:** [Laughs]

**CHUCK:** Just like it sounds, huh?

**JOE:** Kind of like it sounds. It just strip me with one thing, it was being a foreign food that would actually be spelled like it sounds, but that spells how it sounds, Shawarma.

**CHUCK:** Got it. Katya, what are your picks?

**KATYA:** I have two, both of them are Disney. One is the movie "Home"...

**JOE:** That's not Disney.

**KATYA:** That's not Disney?

**JOE:** No.

**CHUCK:** It's Dreamworks.

**JOE:** No, Dreamworks [laughs].

**KATYA:** That's Dreamworks? They're like the same thing if they're all animated.

**CHUCK:** [Laughs] There you go.

**KATYA:** It will have to do with animation. One is the movie Home because we went saw it yesterday, it was the most horrible thing that I've ever seen. And then the other is "Mulan" because they're making a live action Mulan movie.

**CHUCK:** They are?

**AARON:** Oh, cool!

**KATYA:** Yeah, they are.

**JOE:** Like after the Cinderella, it's like next year or the year after.

**KATYA:** I'm really excited. I hope that they actually cast a Chinese actress to play a Chinese character, but...

**JOE:** [Laughs]

**AARON:** Never going to happen...

**KATYA:** My hopes aren't high.

**CHUCK:** That's a stretch.

**KATYA:** My hopes aren't high, but, I'm hoping.

**JOE:** This is Hollywood, come on.

**CHUCK:** Yeah, let's get down to business to defeat the hunt.

[Laughter]

**JOE:** So visiting is Donny Osmond.

**CHUCK:** That's right.

[Laughter]

**CHUCK:** You can call me Donny.

**JOE:** [Chuckles] Yeah.

**CHUCK:** Alright. I've got a few picks here. The first one is a book that I've finished, it's "How to Win Friends & Influence People" by Dale Carnegie. This is kind of a classic and I don't know why I had never gotten around to reading it before, but it was really good. I need to go back and re-read it, pay a little closer attention to some of the points in there, but it was terrific.

**JOE:** Yeah, because you're kind of a jerk. So, good idea.

**CHUCK:** I know. Nobody likes me. Everybody hates me.

**JOE:** [Chuckles]

**CHUCK:** Another pick that I have is "WorkFlowy". It's kind of the new task management thing that I'm using these days. The thing that I like about it is this mostly free form. I tried using Omnifocus. In fact, I've used it off and on for years. The issue is it's just that I never really stick to it and I don't know if that's just a habit issue for me or an actual issue with Omnifocus. But I've used several others off and on over the years and none of them really stuck, so I'm trying this one and I'm liking it so far.

And related to that, I have a couple of books that I'm going to pick, and I've read both of these while I was in Las Vegas for MicroConf. The first one is "Habit Stacking", and the idea is that instead of trying to just build one habit, you can build multiple habits by building the habit of having a routine. So you start your routine in the morning and then you just work through all of the habits that you stacked up. He recommends that you keep your stack shorter than a half hour, and that you start with one. So then what you can do is, you can have a routine in the morning, maybe a routine in the evening, and possibly routine at lunch or whenever makes sense for you to go and do things that you need to regularly work on or get done. Just to give you an example, my morning routine starts out with me waking up, I brush my teeth, I have a drink of water, and then I go downstairs and get something to eat. And then I usually wind up feeding my kids breakfast so I set out the dishes for breakfast and pour the cereal, I just don't pour milk on it. And then I go to the gym. That last bit is just driving to the gym. And that leads to the other book that I'm going to recommend, and that is "Mini Habits".

Mini Habits, the idea is that you do the smallest possible thing to basically start whatever habit you want to start. So the idea there is I just have to drive to the gym. I don't actually have to go in, I don't have to work out, but I have to drive there. Of course, realizing that I just "once I get there, I'm going to go in", and I know that in my head, but the idea is that if you set your habits to be something really small, really low energy, low impedance, then you meet less resistance in your head to do it. So some of the other ones that they recommend are things like doing one push-up, or writing 50 words, or anything else that you can do in just like half a minute. So if you set your goal to be something ridiculously small like doing a push-up, then you can just do the push up. And then while you're already in push up position, you may find yourself doing 20 push ups or a hundred push ups, but...

**JOE:** Or, a thousand!

**CHUCK:** Right. But your goal is to do one, so it's like, "Okay, why am I agonizing over doing one push up?" And then if you do one push up and that's all you do, great! You met your goal, you've done your habit that day, but if you do more than that, then bonus, right? So it's just kind of a mental hack to get into whatever habit you want to build.

**JOE:** In two weeks, I'm going to yell at you because I drove to the gym everyday and didn't work out.

[Laughter]

**CHUCK:** Yeah, so...

**AARON:** I made it in the parking lot, that's good enough.

**CHUCK:** Yup, there we go. But yeah, those are my picks. Victor, what are your picks?

**VICTOR:** Alright, I have two picks. The first one is, I recently started playing board games and card games. And one of the games I really enjoyed, the card game called "Android Netrunner". It's a two-player game from the creator of Magic Gathering. The game is basically, it's asymmetrical game so one player plays the hacker and the other one plays a corporation and they sort of fight like hack and build servers and whatever. I really like it. And if you like board games and card games and you like William Gibson and Cycle Pack in general, I think you should check it out.

My second and last pick is "Mechanical Keyboards". Everyone these days are into Mechanical Keyboards, and I think it's for a good reason. I think every programmer should give it a try and try to using Mechanical Keyboard at least for a week or so. And if you're looking to buy one, you should check it out on micejob.com. They have a lot of really cheap keyboards.

And, I'm done!

**CHUCK:** Alright!

**JOE:** Cool!

**CHUCK:** If people want to know more about where you're working on with Angular, where do they go to check that out?

**VICTOR:** They can follow me on Twitter and they can go to my blog, VictorSavkin.com.

**CHUCK:** Alright! Well, I think that's all we've got. So we'll go and wrap up the show. Thanks for coming, Victor. It was terrific to talk, and this is one of those episodes where I'm going to have to go and deepen my technical knowledge a little bit.

**VICTOR:** It was very exciting to be here! I'm actually a big fan of DevChat.tv podcast in general, and this one in particular, so it was really cool!

**CHUCK:** Oh, thanks!

**JOE:** Awesome!

**AARON:** Thanks, Vic!

**CHUCK:** Alright, we'll catch you all next week!

_**[This episode is sponsored by Mad Glory. You’ve been building software for a long time and sometimes it gets a little overwhelming; work piles up, hiring sucks, and it's hard to get projects out the door. Check out Mad Glory. They are a small shop with experience shipping big products. They're smart, dedicated, will augment your team, and work as hard as you do. Find them online at madglory.com or on Twitter at @madglory.]**_

_**[Hosting and bandwidth provided by The Blue Box Group. Check them out at bluebox.net]**_

_**[Bandwidth for this segment is provided by Cache Fly, the world’s fastest CDN. Deliver your content fast with Cache Fly. Visit cachefly.com to learn more.]**_


