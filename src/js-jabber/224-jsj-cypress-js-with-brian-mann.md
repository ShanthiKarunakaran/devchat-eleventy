---
layout: layouts/post.njk
title: >
      224 JSJ Cypress.js with Brian Mann
date: 2016-08-10 07:00:34
episode_number: 224
duration: 45:42
audio_url: https://media.devchat.tv/js-jabber/JSJ224Cypress.mp3
podcast: js-jabber
tags: 
  - js_jabber
  - podcast
---

## [Angular Remote Conf](https://allremoteconfs.com/angular-2016) and [React Remote Conf](https://allremoteconfs.com/react-2016)
&nbsp;03:18 - Brian Mann Introduction
- [Twitter](https://twitter.com/be_mann)
- [GitHub](https://github.com/brian-mann)
03:33 - [Cypress.io](https://www.cypress.io/)04:09 - [Selenium](http://www.seleniumhq.org/)08:56 - Cypress vs Selenium16:54 - Similarities: Cypress and [Protractor](http://www.protractortest.org/#/)18:22 - Mocking API Data20:40 - Getting Started with Cypress and The Migration Process21:54 - Testing30:31 - Handling Data on the Backend34:16 - What’s coming next in Cypress?

### Transcript

 **JOE:&nbsp;** Are you talking about the dogs or the aliens?

**_[This episode is sponsored by Frontend Masters. They have a terrific lineup of live courses you can attend either online or in person. They also have a terrific backlog of courses you can watch including JavaScript the Good Parts, Build Web Applications with Node.js, AngularJS In-Depth, and Advanced JavaScript. You can go check them out at FrontEndMasters.com.]_**

**_[This episode is sponsored by Hired.com. Every week on Hired, they run an auction where over a thousand tech companies in San Francisco, New York, and L.A. bid on JavaScript developers, providing them with salary and equity upfront. The average JavaScript developer gets an average of 5 to 15 introductory offers and an average salary offer of $130,000 a year. Users can either accept an offer and go right into interviewing with the company or deny them without any continuing obligations. It’s totally free for users. And when you’re hired, they also give you a $1,000 bonus as a thank you for using them. But if you use the JavaScript Jabber link, you’ll get a $2,000 bonus instead. Finally, if you’re not looking for a job and know someone who is, you can refer them to Hired and get a $1,337 bonus if they accept a job. Go sign up at Hired.com/JavaScriptJabber.]_**

**_[Let's face it. Bookkeeping is hard and it's not really what you're good at anyway. Bench.co is the online bookkeeping service that pairs you with a team of dedicated bookkeepers who use simple, elegant software to do your bookkeeping for you. Check it out and get your free trial today at Bench.co/JavaScriptJabber for 20% off today. They focus on what matters most and that's why they're there. Once again that's Bench.co/JavaScriptJabber.]_**

**_[This episode is sponsored by Rangle.io. Rangle's been working with Angular 2 for a long time and they are now putting together an eight-hour, 2-day course designed to help Angular developers learn how to write apps in Angular 2. If you're looking to level up your JavaScript and Angular 2 skills then go to Rangle.io/training and click on the link for Angular 2 training. If you're looking for other training in React or JavaScript, they also have that available at Rangle.io/training.]_**

**_[This episode is sponsored by Rollbar. One of the frustrating things about being a developer is dealing with errors. Ugh. Relying on users to report errors, digging through log files to try debugging issues, or a million alerts flooding your inbox ruining your day. With Rollbar's full-stack error monitoring, you get the context and insights and control you need to find and fix bugs faster. It's easy to install and you could start tracking production errors and deployments in eight minutes or less. We have a special offer for JavaScript Jabber listeners. Go to Rollbar.com/JSJabber and sign up and get the bootstrap plan free for 90 days. That's 300,000 errors tracked for free. Loved by developers at awesome companies like Heroku, Twilio, Kayak, Instacart, Zendesk, Twitch, and more. Give Rollbar a try today. Go to Rollbar.com/JSJabber.]_**

**CHUCK:&nbsp;** Hey everybody and welcome to episode 224 of the JavaScript Jabber Show. This week on our panel we have Joe Eames.

**JOE:&nbsp;** Hey everybody.

**CHUCK:&nbsp;** Dave Smith.

**DAVE:&nbsp;** Well, hello.

**CHUCK:&nbsp;** Aimee Knight.

**AIMEE:&nbsp;** Hello.

**CHUCK:&nbsp;** I'm Charles Max Wood from DevChat.tv. And I just want to shout out about Angular Remote Conf and React Remote Conf. You can check them out at their domains. It's just the conference dot com. Anyway, we have a special guest this week and that's Brian Mann.

**BRIAN:&nbsp;** Hey, everyone. Thanks for having me.

**CHUCK:&nbsp;** Do you want to introduce yourself really quickly?

**BRIAN:&nbsp;** Sure. I'm Brian Mann. I'm from Atlanta, Georgia. And I am the founder and CEO of Cypress.io.

**CHUCK:&nbsp;** Cool. Do you want to give us a quick overview of what Cypress is?

**BRIAN:&nbsp;** Sure. Cypress is both a locally installed desktop application and it's a service that helps web developers write automated tests for the web. We believe that the current ecosystem of testing tools that handle integration and end-to-end tooling specifically that are centered around Selenium just don't really work anymore. It's too hard to write those tests. And so, we have sort of re-envisioned what testing can really be like from a developer's perspective. Cypress's sweet spot is it helps you test modern-day JavaScript applications.

**CHUCK:&nbsp;** So, I've used Selenium before and it seems to work pretty well for me. Where does it fall down? Where are you finding that it just doesn't quite add up to what people need?

**BRIAN:&nbsp;** Sure. I would say there's like a number of different problems along the way with Selenium. It has been around a long time, since I think 2004. And it's morphed over that period of time with the last big revision coming out with WebDriver. But basically the way that it is architected is that it is always going to be outside of the browser and basically sending commands remotely, sort of like slinging stuff over the fence. And so, when you're writing your Selenium scripts you're driving the browser. But it's not really aware of anything that's going on in the browser. And therefore when it has to do waiting and stuff you basically have to constantly ping the browser to figure out what the state of everything is. And what ends up happening is just that tests can become really, really flaky based on network conditions or other situations that cause intermittent failures. Like maybe you're testing locally and it's really fast but then when you run it in CI and it's driving different browsers, you suddenly have a problem.

And so, I would say that's really the biggest cause, especially when you have modern-day frameworks like React or Angular where DOM elements are constantly being blown away and re-rendered and you don't really necessarily know or have control of exactly when that's going to happen. You just have this constant problem of stale references. I would say architecture is probably its biggest problem. But really, developers everywhere echo the fact that it's very difficult to set up. Sometimes it takes a really long time to…

**DAVE:&nbsp;** Mmhmm.

**BRIAN:&nbsp;** Install the drivers and then you have to go through all this configuration step. Once that's done, actually working inside of Selenium just doesn't really feel like the normal development process. It's prohibitively slow. You would never TDD a Selenium session. You would generally always iterate and develop locally. And then once something is done you would probably spend time running the feature. And that's really just because the feedback loop is too slow to spawn a browser for every single separate test and reset the state of things.

**CHUCK:&nbsp;** I'll back you up on that. That's absolutely true. The companies that I've used Selenium at, it was exactly that. It would run on the CI server and when we'd run our tests locally doing TDD we would just run the unit tests and anything else that was fast.

**BRIAN:&nbsp;** Sure, sure. And just like when there actually is a problem, which is all the time, I would say that what we've heard from developers is that it often takes longer to write a passing test than it did just to actually write the feature in the code. And…

[Laughter]

**BRIAN:&nbsp;** That's often just because when something does go wrong which is all the time, that debugging that, there's not really any transparency as to what the browser's doing or really when the step failed. Getting stack traces inside of a terminal is basically useless because you have a rich GUI application that has lots and lots of state to it. And yet, when something fails it will just say something like, “Could not find element,” and you're like, “I have no idea why and I had no idea what this thing looked like at the time that it actually did fail.”

**CHUCK:&nbsp;** Yeah, that's fair, too. I run into that where just with jQuery, let alone with Angular or React or something, it was a timing issue. And it would try and go and hit a button that wasn't there yet.

**BRIAN:&nbsp;** Sure. Right, that kind of goes back to my first point. It doesn't really understand what's going on in the page. And so, synchronizing that your app is in the correct state and that it is ready to perform an action is incredibly difficult, made even more challenging by modern JavaScript frameworks.

**CHUCK:&nbsp;** Yeah.

**DAVE:** So, my team's got about a thousand test cases that are powered by Selenium. And we run them frequently. And we have about, I don't know, I like a 95% pass rate on any given run because at any given run, five percent of the tests would fail intermittently. And it sucks and I've never actually seen a codebase with good Selenium coverage where the developers are like, “Yeah, these tests are rock solid and they're really helpful and I don't know what I'd do without them.” So, why do so many people use something like Selenium today if that's the case?

**BRIAN:&nbsp;** Sure. The whole ecosystem has been built around it. And I think it's really just the case that it came out in 2004 and it's the biggest major player. All the other frameworks and DSLs sit on top of it. And it's really just the only option. And that's why really we started creating Cypress was to give an alternative that's very much different than Selenium.

**DAVE:&nbsp;** So, before we jump into that a little bit I wanted to respond to one of your comments a few minutes ago where you were saying that your code when you're using Selenium WebDriver, you can't really know what the application state is or you can't be notified when that state changes. Instead, test writers tend to poll the DOM, right? They're like, “I want to click this button but don't try to click it until it's there. So, go into a loop, sleep for 10 milliseconds, check to see if it's there, sleep for 10 milliseconds, check. And do this and don't wait for longer than five seconds,” things like that. There seems to be well-established patterns for dealing with those kinds of issues. Is there like a deeper issue here where just waiting for a button to appear, that's no big deal. We can work around that. But what is the deeper issue that you're hoping to really fix with Cypress?

**BRIAN:&nbsp;** The deeper issue is that instead of being outside of the browser, Cypress is the exact inverse of Selenium's architecture which is that it is inside the same exact run loop that your application is executing. Because of that when you write your specs, Cypress is conscious of everything. It has access to the window. It has access to the document. It can synchronously query the DOM as opposed to asynchronously and it would know. It can react to an event in the same run loop in order to perform an action. And therefore it's able to just more accurately predict and manage the state of the application. Basically describe what desired state you want your application to be in prior to performing an action or after it. And it will automatically just know to wait until it reaches that state. And the moment that it does, it continues on. So, you get the benefit of Cypress's, all the commands are completely asynchronously and they can all resolve sometimes seconds, sometimes a minute later after issuing them. But basically the queuing mechanism inside of it is in the same run loop and therefore it's synchronous alongside the browser.

**DAVE:&nbsp;** Do you mean alongside the JavaScript application?

**BRIAN:&nbsp;** Well, right. Yes, yes. Like it is the run loop of the browser is going to be shared between Cypress and the application itself.

**DAVE:&nbsp;** Would that be in much the same way that a Chrome Extension works?

**BRIAN:&nbsp;** When you're working inside of Cypress you boot Cypress as the primary application in the browser. And then from inside of Cypress you will actually pull in your application. So, it's like you're actually running Cypress as the web app and then it pulls in your application and then just executes commands against that application. Does that make sense? [Chuckles]

**DAVE:&nbsp;** How does it host you application in that way?

**BRIAN:&nbsp;** Well, so when you download and install Cypress, it's a desktop application. A fully-blown desktop application that you'll install. It has a GUI that you go in and add your project and then you launch Cypress for that specific project. Then that launches a web browser just like any other web application. It lists off your spec files. And then you can go and navigate to the spec file. And then that will actually run the specs that you wrote on your computer. And as part of the specs you might have issued a command like 'site dot visit'. And you might have visited localhost:8080 or you might have visited a remote URL. And that would have actually pulled in your application and then your application becomes the application under test that all the subsequent commands run against. So, you got visit and then you ask what the title is or you query for a DOM element or you click it or do whatever you want. It's going to do it against the application under test.

**CHUCK:** So, one thing that I can see here is that there are going to be trade-offs between the approach that Selenium has and the approach that Cypress has. And one of the things that I'm seeing here is that Cypress, because it's running within the context or actually executing the context of your JavaScript application, it will be able to directly observe and directly manipulate things that are in the DOM and in the browser and in your application. But the flip-side of it is, is that I find that if you have these kinds of harnesses on your application sometimes you run into things where because it is managing and manipulating the context of the application it actually in some cases changes the state of the application as it observes it or as it executes it so that tiny issues and certain contextual issues get changed by the fact that it's being run by a system like this. Are there certain instances where you wouldn't want to use Cypress because it does have these trade-offs? Or have you not run into those?

**BRIAN:&nbsp;** Yeah. That's a great question. I think there are trade-offs with everything. And yes, I would say that Selenium is like the purest… it's going to run the browser pretty close to exactly how a user does. It doesn't modify any of the host objects that come built into the browser. And you're going to have to automate this browser exactly like a real user would, pretty much exactly like a robot, right? And if you think of the testing pyramid and you think of unit tests at the bottom and then integration then end-to-end, Selenium is great at the very tippity-top little part of the triangle. Whereas with Cypress yes, it's definitely, it's got its hands in all of the hosts objects so it can understand exactly what's going on.

But it's just different. It doesn't try to be a hundred percent equivalent to Selenium where you just do end-to-end tests. You can really do all the way down to even unit tests within Cypress itself. Some of our users are using it where they basically add a build process around their spec files and they're able to just require React components and then basically mount those as the application under test. And then they're able to then use all the typical commands, even spying, stubbing, things like that. Like much more down the line, like all the way down to unit tests. From within Cypress itself you can do things like automatically stub out XHR requests and response. So, you have a lot finer control. You have access to everything.

When you're doing things like logging in with OAuth you could just hypothetically stub out those methods that act as if a real user's been logged in so you can isolate and not have to go all the way out to talk to GitHub or talk to Google or what have you. So, I think it's really just, it's just down to where do you find the most value out of testing your application? I would still say it's good to have a few smoke tests that are pure end-to-end that still use Selenium that maybe can test in different environments and whatnot. But what we see is most users of Cypress are using it in the development cycle where they're probably handling their JavaScript files in a different way than when it would go into production anyway. Like they're using it alongside of their development process. And they can pick what part of the triangle they would like to test.

**CHUCK:&nbsp;** So, what you're saying is instead of testing my application from an end-to-end standpoint like Selenium does I also have the option of say with Angular I can load in a directive or a component and just test that without having to test the entire application in full context.

**BRIAN:&nbsp;** That's right. You have the ability to do it both ways. And that's what's I guess really different about this. We've never really had an option. It's like unit tests and then trying to do jsdom in Node has always been clunky. And you can't actually see anything and it doesn't behave exactly the same way. Or you have all the way up to end-to-end tests and not really anything in the middle. And Cypress is definitely that middle part and then it also extends into both unit tests and end-to-end tests.

**JOE:&nbsp;** I was curious about the similarities between this and something like Protractor, if you're familiar with Protractor which sits on top of Selenium, right? [Inaudible]…

**DAVE:&nbsp;** Oh yeah, good question.

**JOE:&nbsp;** What's going on more underneath than Selenium kind of does. So, yeah. If you could cover that.

**BRIAN:&nbsp;** Sure, sure. Yeah, I've certainly used Protractor. Yeah, it's built on top of Selenium so architecturally it's going to have all the same issues. And yes, it does basically just checks the Angular object on window and it does tap into Angular's internal queuing. So, that's advantageous because you're kind of using the way that Angular synchronizes async or how it queues async actions. So, you're basically saying that there's that method that says wait for Angular to be ready. I can't quite remember but it taps into that. So, if you had queued XHRs or whatever it'll wait ‘til all of those are flushed before issuing commands. I would just say that whereas that's really specific to the way that Angular works, Cypress will work just as well but on anything, irrespective of Angular. And we have, I can't even tell you how many Protractor users, a healthy amount. Probably 20, 25% of our early adopters have used Protractor in the past. And because it's still Selenium it's still going to have all those same problems.

**AIMEE:&nbsp;** One thing that I used to do that I thought was pretty cool, at my prior job we again were using Protractor. But we started using a library that would mock out the backend. Now I guess some people would say, “Well, that's not a true end-to-end test then.” But because we were working, this was an application team and some of the APIs were not managed by our team we did want to isolate and mock out that. So, is there a way to do something like that with Cypress?

**BRIAN:&nbsp;** Oh yeah, absolutely. That's built first class into Cypress. I would, I highly recommend stubbing or mocking as much as possible. You can still have your true end-to-end tests, like maybe around the critical paths of your application. Like you wouldn't want to mock logging in or just something that has to be working. But for the vast majority of your endpoints, I recommend mocking all of those. And so, inside of Cypress it has built-in support for fixtures where there's a fixtures directory. You can create a JavaScript file, JSON, you can add zip files or images or anything else like that. And then from within Cypress there are all these connections between all the different commands that help get you those fixtures out of there and you can automatically set fixtures to stub responses.

So, in Cypress you can basically do stuff like you can start an internal server which handles the stubbing. And then you basically give it a regular expression to match against the URL. And then you can give it either directly a fixture as a response or you could write your own hypothetical object or array or what have you. And then you can specifically wait for that route to resolve. And so, Cypress will wait for a request to go out that matches that URL and then subsequently a response to that. And therefore you can basically test all the various conditions of your application without having to fuss around with seeding the database. So, if you want to test the empty view, it's trivial to basically respond with an empty array. If you wanted to test pagination you could easily simulate that. It's really simple to do this inside of Cypress. It's supported first class.

**CHUCK:&nbsp;** So, my question then is let's say that I decide, “You know what? I really like Cypress. I want to use it in my stuff. I take my I heart Selenium t-shirt and I torch it and I get an I heart Cypress t-shirt,” where do I go?

**AIMEE:&nbsp;** [Laughs]

**CHUCK:** I've got these end-to-end tests that are written in Selenium. Maybe I have hundreds of them like Dave pointed out. Where do I go from there? Can I still keep my Selenium test suite while I'm migrating stuff over?

**BRIAN:&nbsp;** Well, yeah. I think that's just like anything else. If you're migrating half your application from Angular to React or whatever it's going to be different. They're completely different commands and they're going to work very differently. They're not really compatible per se. but I would just say as you're… I wouldn't even recommend migrating it over. I would just say start writing new tests in Cypress. And then in your CI server just run two different commands, the command to runs Cypress tests, the command to run Selenium tests. And if anything exits with an exit code other than zero then it's going to fail. So, I don't think it needs to be any more complicated than that.

**CHUCK:&nbsp;** So, if you buy into the Cypress system though, because it looks like there's a backend CI component to Cypress. If I'm running it there, I can still run Selenium and everything else over there?

**BRIAN:** Yeah. Well, I guess let me talk a little bit about that. So, to really solve testing I guess we believe that you really have to do it in three different ways. And really, this mirrors the struggles that we have seen other developers have with testing is that really, they all struggle with the initial setup of the testing suite just to get going, just to write that first test. And that's why we chose the route of packaging it as like a native application and creating an interface that helps you get into writing the tests as quickly as possible. And then the second thing that people struggle with is actually just writing the tests. That experience is just not good for a modern-day developer. And so, we wanted to improve that.

But then really, the third part is the biggest to really solve which is that after you build up a suite of tests and you start going from dozens of tests to hundreds of tests to even thousands of tests, well then you need to run them across one or more browsers. You need to be able to respond to the failures and handle flake and decipher exactly what happened when that test failed and recreate that locally. That's actually where our service comes in. So, one and two are going to happen on your local computer. And then when you go to run us in CI what happens is that you just call into, there's just a command, Cypress CI. And what that's going to do is that's actually going to spin up a browser on our infrastructure and we're automatically going to handle the connection tunnel back to where it's running in CI.

So, whether it's Travis or whether it's Circle or something, Jenkins that you're hosting yourself, that's where the Cypress server and that's where your codebase lives. And so, all we are is we're just the headed remote browser. And then we synchronize basically the Cypress commands over the network. And it drives the browser and feeds all that data back to you. So, we'll record a video. We'll take screenshots of failures. And then we'll also handle all the logs and pipe those back to the desktop app. So, after a run completes you can go to the desktop app and basically see just the failures by themselves and review exactly what failed on a particular test.

**CHUCK:** Now, how much of this is free and how much do you have to pay for?

**BRIAN:&nbsp;** So, we're in private beta right now. So, everything is free. You have to basically get an invitation. The plan is just to basically be just like every other SaaS company out there, a typical SaaS pricing model. They'll be free to run source projects and then for private projects there'll be likely a usage model based on how many instance hours, similar to what you find with Sauce Labs or BrowserStack for that matter. Spinning up instances and handling all the bandwidth and everything else obviously isn't free. But that's where the service component comes in. If you don't want all that you can still always run Cypress purely in headless mode where it will still record things and dump those assets to you, but it won't synchronize those up. It's like you basically get what you get right now, an exit code with a number of failures and then a bunch of assets that are sitting on the server.

**DAVE:&nbsp;** So, I want to go back a little bit to what Aimee was asking about with the mocking of API data and stuff. Is that okay?

**BRIAN:&nbsp;** Sure.

**DAVE:&nbsp;** Based on the way you described that it sounds like if someone were to ask you, “Is Cypress a unit testing framework or an end-to-end testing framework?” it sounds like you would say both. Is that right?

**BRIAN:&nbsp;** Yeah, absolutely. It can change and modify things in your application or it gives you the power to create the state that you desire to test. And your application has no idea. And that's what I was saying, like whereas with Selenium you only get the tip of the triangle and there's no mocking. You have to manually manage all of that and your application is going to do what it does no matter what because you don't really have direct access to anything. But with Cypress you have access to everything and therefore we can modify and control the state. So, you can write tests that look and perform exactly like unit tests or you can write tests that look and perform exactly like Selenium end-to-end tests where you don't mock or stub anything. Or you can kind of just write tests in the middle where you do a little bit of mocking and stubbing like maybe you just want to stub out the OAuth service. Or you want to mostly use real endpoints but then for those few edge cases where you don't want to necessarily have to synchronize the state of the database on the backend you can just simply stub out responses to create that desired situation that you're [looking] for.

**DAVE:&nbsp;** So, in an ideal world could I use Cypress to replace all of my tests including those that are built with like Mocha and Karma?

**BRIAN:&nbsp;** Yeah, that's kind of what we're going for. You can basically run all types of tests in Cypress as long as the code… because it's being executed inside of a browser there's a few things that it will never be able to do, like parallelization. There's only one DOM. There can only ever be one DOM in a browser. So for instance, if you wanted to parallelize things that had access to a DOM you'd have to still do that in Node. But for really everything else, yeah. As long as the code can run inside of a browser you will be able to test it with Cypress.

**DAVE:&nbsp;** Is there a runtime penalty there because of that? I know you mentioned you can't run in parallel. But just comparing single-threaded to single-thread, are Cypress unit tests going to run a little bit more slowly than Mocha and Karma tests?

**BRIAN:&nbsp;** No. Cypress is built on top of Mocha and Chai. We've just extended Mocha and we've created our own interface on top of it. So, when it runs in unit testing mode it's basically just a GUI replacement for Mocha. And the only penalty there would just be the tiny rendering penalty because we give you a lot more feedback, a lot more… every command is broken down and gives you a visual representation of when it ran that command and the arguments and the data and the return value and all that stuff. So, there's just tiny performance penalty. I think when we did initial tests, and we basically just took the unit tests from various frameworks like Ember, React, Backbone Marionette, and it was, I don't know, I think anywhere between 10 and 15% slower. So, it's just doing that because there's more of a rendering penalty inside the browser. But it's not much.

**DAVE:&nbsp;** So, do I have to build my app fully and have it deployable and ready to go in order to actually run it in a browser and then run the tests on it?

**BRIAN:&nbsp;** Well, hypothetically you're testing an application that's running in a browser. So, maybe I'm not understanding. Like if you're…

**DAVE:&nbsp;** Well let me [be] more specific. So, when I run a Mocha test on the command line with npm I can just import the module, run some tests on it. I don't necessarily have to have my whole app be ready for a [inaudible]…

**BRIAN:&nbsp;** Oh, right.

**DAVID:&nbsp;** Bundle.

**BRIAN:&nbsp;** Sure. No, you could do the same thing in Cypress. We don't have a lot of examples of that because our focus really has been on the integration and the end-to-end. But we have example projects and I've seen users do that where what they do is, you still have to add a build process around your spec files themselves to get them ready to be sent to a browser. So, they would import the component the same way they would build the spec files. And then they would render the component out to the application under test, which is basically just a blank page. So yes, you can essentially achieve the same thing. Does that make sense?

**DAVE:&nbsp;** Mmhmm.

**BRIAN:&nbsp;** And for pure unit tests where you're just calling functions and checking return values you don't need to render anything. You just import those functions and then call them straight up. I guess I'm more or less describing like if you have React components that require a DOM you would render them into the application area. So that way, you can see them and they look exactly how they're going to look by themselves outside of your application. But for standard functions and stuff you just import them and call them. And it would really be identical to the way that a Mocha test would be running in Node.

**JOE:&nbsp;** And you said you got a few examples of that. So, is that they typical? Or is it more like, the typical usage of more like Selenium. You run the app and you run tests against it.

**BRIAN:&nbsp;** No. The more typical example is you go out and visit a page that is then obviously hosting your app and hosting all the JavaScript bundle. That's the most typical example.

**JOE:&nbsp;** Okay. So, what about database and data on the backend and handling all that?

**BRIAN:&nbsp;** Great question. So…

**JOE:&nbsp;** Maybe it might be a good idea to give a little bit of context here. We haven't really talked about this yet, have we? But if you're going to test and you've got a live database, you make a test and it changes the data, the backend, then the next test might be screwed up because the data is now changed and it's expecting, “Hey, you only have four users. I'm expecting…”

**BRIAN:&nbsp;** Sure.

**JOE:&nbsp;** “You to have four users,” but in the last test you created a fifth user. So now when I check and say, “Do I have four users there's actually five,” so the test fails.

**BRIAN:&nbsp;** Sure.

**JOE:&nbsp;** With unit tests, it's really easy to deal with because you just set up your state in code and then you test one little tiny piece. But with a whole running application you've got the whole database. And so, you've got the Rails way where they were constantly resetting the state of the database. And how do you deal with that sort of thing? Do you trust that certain tests run in order? Or let's talk about that.

**BRIAN:&nbsp;** Sure, sure. Yes, so I wouldn't really say this is a disadvantage but it's more like I guess a trade-off. So, in the Selenium world how would you handle this? Well, it's not like doing Selenium suddenly makes this any easier or harder. The difference is that when you're executing Selenium you're generally in the context of your backend. So, you've got your scripts or whether you're using Mocha or anything else it doesn't really matter. You've got your tests. And then you would generally have, you would set a before each or an after each or something like that. A hook that goes and resets the state of the database so that between each test you're automatically clearing stuff out. So, really in Cypress there's no getting around that. If you're not stubbing or mocking… and this is actually where I come back to stubbing and mocking.

If you just stubbed and mocked everything you would never have to deal with this problem. And you would never really even have to rely that much on your server and you can bypass all those stuff. But let's assume that you're really calling through and then yes, you changing the state of your database and you have to get that back. Well, all we need to do inside of Cypress is basically just create an escape hatch that lets you go out of the browser and lets you talk to external resources.

And so, there are a few different commands that we have to do this. There's 'cy dot exec' which can simply just execute a script on the backend. So, you could just have your reset or your seed script written in Node or whatever and then you would do the same thing. You would set a before each that calls into that. We execute that. The database gets reset. Same thing as if you're running Selenium. We have a command called 'cy dot request' which basically can just make RESTful requests except it is not core susceptible. So, you can just make a request to anything and anywhere. And then finally there's also a 'cy dot message' command.

And this hasn't been finished yet but what you're describing is basically the problem of, “Well, if things are running in the browser how do you get data back into the context of the backend?” And the best way to do that is basically to create an adapter for every single language that when you're in test mode in your server you basically just import the Cypress adapter and therefore the frontend can then talk directly to the backend without having to expose a RESTful route or without having to write a script. And then you can just pass messages back and forth. So you'd say, “cy dot message create user” and you're passing an object literal. And then that generates the user on the backend. Or you could just say, “Count all users.” And then you continually implement those messages in the backend. That's not done yet but we have a few proofs of concept that that works.

Honestly people, because we have the other commands and because there's all the stubbing and mocking, people have just not really needed it that much. They've basically found other ways to get around it. But that is the long-term plan.

**JOE:&nbsp;** Gotcha.

**CHUCK:&nbsp;** So, what's coming next in Cypress?

**BRIAN:&nbsp;** So, we have been in private beta now for, well really, for a long time. I've been working on this project now for two years. And we have five full-time team members. And so, little by little we've just incrementally improved it and added features. We have about 200 active beta users that are using it all the time. And we need to release our platform. That's something that has been in development a long time, which is basically all the things that are going to record all of the browser videos and the screenshots and the logs and piping that back to you. We need to open source the whole thing. Like we have basically broken Cypress into nearly two dozen small repos and microservices. We've open sourced about half of them but because we're in private beta we haven't open sourced the rest of them. So, I think for us it's just getting out the platform, fiddling in the bugs and the features requests and then ultimately open sourcing it and making Cypress extensible.

**CHUCK:&nbsp;** Alright. Well, let's go ahead and head to picks then. Dave, do you have some picks for us?

**DAVE:&nbsp;** I certainly do. I would like to pick an article that was written by our missing host, Jamison Dance, this week called 'How to Learn Technical Things'. And this article is a really, really cool perspective, I think especially for people new to the industry on what makes experienced people seem to be able to learn things faster. And he has half a dozen really good things that will help. They definitely help me to learn things better and faster. And some of the things that I think many of us are afraid to do but that are absolutely necessary to do when learning new stuff. So, I'll share that with my show notes. I'll link to that. But it's called 'How to Learn Technical Things' by Jamison Dance. And that is my one and only pick. Jamison, I wish you were with us today.

**CHUCK:&nbsp;** Alright. Aimee, what are your picks?

**AIMEE:** So, I have one this week and it is not very complicated. But I feel like it's a really big time saver. But it is just a Git repo that Paul Irish put out and it's… you just type 'git open' and this is an npm module and it will open whatever Git project you're in it'll actually open the URL in your browser. So, I don't know. For me I get tired of having to click around and find exactly where I'm at. So, this seemed like a quick little time saver. And that's it for me.

**CHUCK:** Awesome. Joe, what are your picks?

**JOE:&nbsp;** I want to pick the movie 'Warcraft'. Went and saw that the other night with my kids. It was surprisingly enjoyable to watch.

[Laughter]

**JOE:&nbsp;** I would be really surprised if it won any academy awards for best picture. But it was…

**DAVE:&nbsp;** Best depiction of an orc.

**JOE:&nbsp;** [Laughs] It was actually a somewhat complicated plot given that it's video game turned into a movie. It was actually really… it got horrible reviews by critics or certain… and I think, I'm not sure how the audience [inaudible] but I keep talking to people who have been saying oh, they really enjoyed watching it.

**DAVE:&nbsp;** [Chuckles]

**JOE:&nbsp;** So, I took my three kids and went and saw 'Warcraft' and I was really surprised that I liked it as much as I did. It was really actually a really fun movie to watch. And…

**DAVE:&nbsp;** Do you have to be a 'Warcraft' game player?

**JOE:&nbsp;** No, not at all. In fact, if you are a 'Warcraft' game player you'll recognize the names and even some of the cities look a little bit similar to cities in the game. But mostly they kind of meshed a bunch of stuff together so it doesn't really follow the true storylines from the actual game. So, you might even find yourself being a little bit confused now and then. But overall, I don't know, it was just a fun movie. Really fun movie. So, I'm going to pick the 'Warcraft' movie for my pick this week.

And then I've got one more pick which is spending time with your kids. I went to scout camp for a week with my 11-year-old son. And I didn't even have any kind of internet access at all for six straight days, which is probably the longest I've even gone with internet for, I don't know, a year.

**DAVE:&nbsp;** [Chuckles] Oh yeah.

**JOE:&nbsp;** At least [inaudible] some kind. And just hang out with my son for six days. Scout camp is like five and a half. And had a great time. Watched him. I got, bought him a new pocketknife for his birthday and then he subsequently proceeded to chop a small portion of his finger off.

**DAVE:&nbsp;** Oh, oh.

[Laughter]

**CHUCK:&nbsp;** Typical.

**JOE:&nbsp;** Yeah. Yeah, he like shaved just a little tiny bit. It was bleeding a lot. It's nothing serious but it was pretty funny right after a while.

[Laughter]

**JOE:&nbsp;** But I had a good time. So, spending time with your kids is my other pick. There you go.

**CHUCK:&nbsp;** Awesome. I've got a couple of picks I'm going to put out there. The first one is I'm traveling. I'm actually flying to Chicago tonight to go to Podcast Movement. By the time you listen to this I will probably have been and gone and be off doing other things. But there are a couple of things that make the travel a lot more pleasant.

The first one is the TSA pre-check. If you're going to go through security you may as well go through security with your belt and shoes on. And you don't have to pull your laptop out of your bag. And it's super nice. So, I'm going to recommend that. The process for getting it isn't terrible. Basically you fill out a form, you go get interviewed, and then you have to agree to certain terms. Or no, I think it was, anyway I had to sign something and I think what it was, was that all the information I gave them was accurate. And then you just get to go through the metal detector. And…

**DAVE:&nbsp;** [Laughs] You get to go through the metal detector. Yay. [Chuckles]

**CHUCK:&nbsp;** It's sad that it's moved that it's moved that way, right? You know, instead of the body scanned.

**DAVE:&nbsp;** Mmhmm.

**CHUCK:&nbsp;** So, I have stuff in my pockets as long as it's not metal, can just walk through a security check with it. So yeah, so that all works out nicely. I don't have to take off my shoes. And…

**DAVE:&nbsp;** I just want to make sure I understood here. You just picked the TSA, right?

**CHUCK:&nbsp;** I know. I picked…

**DAVE:&nbsp;** [Laughs]

**CHUCK:&nbsp;** I picked a way of not having to deal with the long lines created by the TSA.

**DAVE:&nbsp;** Oh, okay. Okay.

**CHUCK:&nbsp;** Because that's the other thing is that the TSA pre-check line is always much shorter.

The other picks that I have related to travel, I have some Bose noise canceling headphones. I've had them for four or five years and they still work great. And that's always nice when I'm traveling, just to not have to hear all of the extra noise and stuff especially on the airplane. It just seems to help me get into whatever groove I'm trying to get into whether that's watching a movie or listening to a book or actually trying to get work done. It kind of mutes everything way, way, way, way down. And that's always nice.

And then I've got a couple of books I want to pick. One of them I just finished on Saturday. It's called 'The Overton Window' by Glenn Beck. And it's a really interesting kind of a thriller book. It's got government conspiracy and stuff in it. And the characters are very interesting. It does get into a little bit of the beliefs of people who strongly support the constitution and things like that. So, you're going to get some of his political philosophy in the book. But the overall story is really, really good. And it's a lot of fun to kind of listen to and hear the characters interact in the way that they do. So, I'm going to pick that.

And then finally I'm going to pick one other book and this one's also sort of political but it's mostly historical. It's called 'The Jefferson Lies' by David Barton. And basically it's just an interesting view into history around Thomas Jefferson. And in particular there have been a lot of misinformation put out there about Thomas Jefferson. For example, I think the biggest one that I've heard over and over again is that he fathered children through one of his slaves. And it turns out that that's not the case. And there's all this evidence that people brought up that it turns out the DNA evidence and other evidence strongly refutes. So anyway, it's really interesting just seeing okay, this is why this information came out. This is kind of the context around when it came out. And this is why it's incorrect. So anyway, I think history and in particular the way that certain people tend to try and revise history is very interesting. And then figuring out, “Okay, so what proof do we actually have of some of these things?” And there are a lot of other things in history that both sides have tried to obscure or change. And if you go look at original documentation you'll find out that, “Oh, it's actually this way and not that way.”

But anyway, those are my picks. Sorry to wax…

**DAVE:&nbsp;** Hey, Chuck.

**CHUCK:&nbsp;** Philosophical. Yes?

**DAVE:&nbsp;** Hey, Chuck. I just remembered something…

**AIMEE:&nbsp;** [Chuckles]

**DAVE:&nbsp;** That I want to pick that is so good.

**CHUCK:&nbsp;** Okay.

**DAVE:&nbsp;** Can I amend my picks?

**CHUCK:&nbsp;** Yes. Go ahead.

**DAVE:&nbsp;** Okay. So, I have picked the 'Hardcore History' podcast on this show before. It's probably been over a year since I picked it. But I just learned this week that there are more episodes than what you can access in your podcasting app. But you do have to buy them. They're like two bucks a show. And if you go to the 'Hardcore History' website, just google 'Hardcore History', there's a bunch of awesome stuff there that I did not know existed. So, if you've been wondering where you can get your hands on more 18-hour series on different wars and historical events, now you know. Go there. So, I just couldn't… I just had to share that. It's so good. Anyway, that's all.&nbsp; Thank you for letting me [inaudible].

**CHUCK:&nbsp;** Yeah, that one's on my list. It's all good. Brian, what are your picks?

**BRIAN:&nbsp;** Well, I was going to say since we work as a team completely in JavaScript one of the issues that we had was just synchronizing all the different Node versions. We have specific requirements that [cause this app to] use different versions of Node. And what we found, so we use nm which is probably what most people use. And we use a plugin called avn which is automatic version switching for Node. So, you just drop in a 'dot node' version file in your project root and then anytime you cd into it, it will automatically swap the Node version to that, which is highly useful.

**CHUCK:&nbsp;** When you said that I was thinking bird-like, A-V-N. Sorry, never mind.

**BRIAN:&nbsp;** [Chuckles]

**DAVE:&nbsp;** That was a good one. I'll give you a chuckle for that on, Chuck.

**CHUCK:&nbsp;** Yay, a Chuck chuckle. Alright, well let's go…

**JOE:&nbsp;** Oh my.

**CHUCK:&nbsp;** Let's go ahead and wrap up the show.

**AIMEE:&nbsp;** [Inaudible] today. [Laughs]

**CHUCK:&nbsp;** I know. We'll go ahead and wrap up the show. Thanks for coming, Brian.

**BRIAN:&nbsp;** Sure. Thanks for having me.

**CHUCK:&nbsp;** If people want to find out more about what you're doing, follow you on Twitter, check out Cypress, what do they do?

**BRIAN:&nbsp;** They can just go to Cypress.io. We're always looking for more early adopters so you can subscribe to our mailing list. And then after doing that you'll get a link to fill out an early adopter form. Probably in another two months it's all going to be open source and likely out of beta anyway. So, you can also just sit tight and eventually you'll be able to use it.

**CHUCK:&nbsp;** Very cool. Well, thank you for coming on the show. We'll wrap this up and we'll catch everyone next week.

**_[Bandwidth for this segment is provided by CacheFly, the world’s fastest CDN. Deliver your content fast with CacheFly. Visit CacheFly.com to learn more.]_**

**_[Do you wish you could be part of the discussion on JavaScript Jabber? Do you have a burning question for one of our guests? Now you can join the action at our membership forum. You can sign up at JavaScriptJabber.com/Jabber and there you can join discussions with the regular panelists and our guests.]_**


