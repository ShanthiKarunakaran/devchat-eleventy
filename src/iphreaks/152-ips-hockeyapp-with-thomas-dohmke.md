---
layout: layouts/post.njk
title: >
      152 iPS HockeyApp with Thomas Dohmke
date: 2016-05-12 07:00:03
episode_number: 152
duration: 47:18
audio_url: https://media.devchat.tv/iphreaks/IPS152BUILDHockeyApp.mp3?rss=true 
podcast: iphreaks
tags: 
  - iphreaks
  - podcast
---

This episode was recorded live from The [Microsoft Build Conference](https://build.microsoft.com/) 2016. In this episode we chatted with Thomas Dohmke of [HockeyApp](http://hockeyapp.net/features) and the evolution of Interactive C#. You can follow him on [Twitter](https://twitter.com/ashtom), or see what he’s done over on [GitHub](https://github.com/ashtom).Picks[Tesla Model 3](https://www.teslamotors.com/model3) (Thomas)

### Transcript

**_[This episode is sponsored by Hired.com. Every week on Hired, they run an auction where over a thousand tech companies in San Francisco, New York and L.A. bid on iOS developers, providing them with salary and equity upfront. The average iOS developer gets an average of 5-15 introductory offers and an average salary offer of $130,000 a year. Users can either accept an offer and go right into interviewing with a company or deny them without any continuing obligations. It’s totally free for users, and when you're hired they also give you a $1,000 bonus as a thank you for using them. But if you use the iPhreaks link, you’ll get a $2,000 bonus instead. Finally, if you're not looking for a job but know someone who is, you can refer them to Hired and get a $1,337 bonus if they accept the job. Go sign up at Hired.com/iphreaks]_**

**CHUCK:** Alright. Hey everybody and welcome to the iPhreaks Show. We’re recording live at the Build Conference.

**JAIM:** Oh man, I wanted to say ‘Hello from San Francisco’ and like everyone say it.

**ANDREW:** Yeah, you got to let us do it.

**CHUCK:** Alright. Well, we have Andrew Madsen.

**ANDREW:** Hello from San Francisco.

**CHUCK:** We have Jaim Zuber.

**JAIM:** Hello from San Francisco.

**CHUCK:** And I’m Charles Max Wood. We have a special guest and that is Tomas [chuckles] and you’re from Hockey App, correct?

**THOMAS:** Yes. Hello from San Francisco. [Chuckles]

**JAIM:** Wait a minute; we’ve never been from San Francisco before. What’s going on?

**ANDREW:** What’s going on, Chuck? Why are we all here?

**CHUCK:** I thought I already said that? We’re at the Build Conference.

**ANDREW:** Okay.

**CHUCK:** We have Microsoft people that we’re talking to, which is cool.

**JAIM:** Awesome.

**CHUCK:** Do you want to give an introduction, Thomas?

**THOMAS:** Yeah. I am Thomas and I am one of the Hockey App founders. I used to be a Hockey App CEO and now I work for Microsoft as a program manager and a sponsor for Hockey App.

**CHUCK:** Cool. Do you want to give a brief overview of what the Hockey App is?

**THOMAS:** Sure! The Hockey App is an online service for app developers, mobile or desktop – doesn’t matter. Platform doesn’t matter – iOS, Android, Windows, OS X. it gives you four [inaudible] features. The first one, and it’s really like what we always think; it’s the first step in your development cycle. You create a prototype, you have an idea and you want to share it with your friends, with your podcast buddies. So you upload the build. You distribute it to [inaudible] so they can install it and try it out.

Then, while they have it, now we don’t know are they really testing it? Do they like it or not? So we integrate our SDK, you would crash the [inaudible], get the feedback and you get now [inaudible].

**CHUCK:** Okay.

**JAIM:** So this solves the problem way back when where you build something, you want to [inaudible] try it out, you had to go through a whole weird process. [Inaudible] through revisioning. You have to make – you have to tell these people how to go to iTunes connect and down – not iTunes, connect to iTunes and download it and drag it here. It was a nightmare having setup. Test Flight solved this way back when Hockey App’s another thing that does a similar thing.

**THOMAS:** Well, we both started at the same time.

**JAIM:** Okay.

**THOMAS:** So it was like – what happened was in 2010, Apple showed iOS 4 at WWDC and they had this – a talk about revisioning over the air. Basically, they saw – we saw one of our founders basically saw the session and had the same idea as the buddies from Test Flight. And so we created this open source project called Hockey – just Hockey, no “App” – and it was like a [inaudible] piece of an SDK. Hockey comes from “Ad Hoc” plus “Key”. So we started – yeah, before iOS 4, you had to connect to iTunes and your whole media library was on that PC or Mac. So if you add [inaudible], you couldn’t actually install an app that some agency contract or whatever, sent you because your Mac was at home and you couldn’t [inaudible] with that Mac at work because it would basically clean up your whole [inaudible] library. So that was the old ages basically.

**JAIM:** Yeah, it was a nightmare just trying to get an app – just try this out. And yeah, services like Hockey App really helped out. You could crank it out, send it to some people and quickly. You’re not wasting a lot of time setting everything up.

**ANDREW:** The thing I’ve known Hockey App for I think since the beginning, I knew you did beta distribution, but you also do crash report.

**THOMAS:** Yeah.

**ANDREW:** And I’ve had the impression that Hockey App is really good at crash reporting. I’m curious to know how you got started with that and particularly, what some of the challenges around getting crash reports from iOS.

**THOMAS:** Yeah. So I think they actually started this crash reporting before we did Hockey App. So one of our founders, Andreas, he was working at [inaudible] Code and [inaudible] which is the company that does things for iPhone and Mac. They just wanted to figure out what app is crashing and why it is crashing and that was an open source project called Peer Crash Reporter. So they took the Peer Crash Reporter and put it into the Apps to collect crash reports. But then the challenge is you get something that’s not actually readable; you just get memory regresses. So you have to symbolicate those crash reports.

So Andreas thought it to create also an open source project and call it Quincy like the TV show. What was it? The guy who’s like looking at dead bodies, figuring out what the crime was.

**ANDREW:** Like forensics?

**THOMAS:** Yeah. [Chuckles] And so – then we started working on Hockey App with beta distribution and crash reporting. They both worked well together because we have the betas. They obviously crashed because they’re still developing the app. And the added symbolication as a core feature which basically takes your memory regresses, combines them as your symbol files and gives you method names, line numbers, file names and so on. So you can actually read the [inaudible].

Then this also allows the backend to combine those together and actually show you which crashes are similar so you don’t get a million crashes in a list but you get just maybe ten or fifteen crash course.

**ANDREW:** So in the old days, before Hockey and some other services [inaudible], I remember, Hockey was the first one I really knew about. You might get a crash report from a user if you ask them to send it to you.

**THOMAS:** Yeah.

**ANDREW:** And then you’d symbolicate it manually but you didn’t have any of these aggregation and symbolication. I mean Xcode’s supposed to do it and it sometimes worked and it sometimes didn’t.

**THOMAS:** Well, it was a really tedious manual process. You would basically tell the user how to get the file, which also included iTunes. So we had to sync your devices and them find the crash report in the library, whatever mobile device’s folder; take that file, send it via email. Then on your Mac, you had to find the right symbol files because you have no archive of symbols so I could just set to find that file, and then on a post script that Apple gave you in some subfolder of Xcode to symbolicate. So it’s most likely the golden – the old ages. Then we took, basically, that process and said whenever you do a [inaudible], upload that symbol file to Hockey App, sort of an archive for all your symbol files. Then we match that against the crash report coming in to get all the [inaudible], symbolicate it to crash files.

**ANDREW:** Okay, new question. Symbolication.

**THOMAS:** Yeah.

**ANDREW:** What is it?

**THOMAS:** It’s really mapping and memory regress against a [inaudible] file.

**ANDREW:** Okay.

**THOMAS:** It’s the mapping file on iOS and Mac is what’s called a Dwarf file and it includes a [inaudible] description of – on which memory regress is rich in line number in you code, in which file, in which method. Then similar things on [inaudible] or in Windows that’s something called [inaudible] which is essentially the debug information for both.

So you both [inaudible] out of the information about how the method is called and which line number [inaudible], and its symbol file brings it back. To combine those two files into one report [crosstalk].

**CHUCK:** Then you can figure out where things went wrong. Yeah.

**ANDREW:** If you look at an unsymbolicate crash report, you basically see a bunch of hex, hex memory addresses, and it’s not something you can really decide on.

**JAIM:** Unless you’re an expert developer.

**THOMAS:** But even then, it’s kind of hard because your binary is not always at the same start address so you then have to do Math in addition to just [inaudible] the hex symbols. Then obviously, the [inaudible] is not only on your code, it’s also the runtime, the [inaudible] and so on and you don’t have even – maybe the experts in Apple can do that but a normal developer cannot read the symbols from Apple my memory, I guess. [Crosstalk]

**CHUCK:** Yeah. I read hacks over breakfast but I can’t do Math at the same time. [Chuckles]

**ANDREW:** I think we’ve talked a little about the old days and why Hockey started. One of you [inaudible] that. So you started out doing beta distribution and crash reporting on iOS; I know now you support other platforms.

**THOMAS:** Well [inaudible] not out on iOS, Mac and Android, only one. So we had those three from day one. We edit Windows phone back then in 2012 so it wasn’t – it had nothing to do with the acquisition. Then over the years, we supported Swift; we supported [inaudible] iOS 6, 7 and 8. We started to put supporting the [inaudible] or the NDK. So we edit all those platforms and then we build up also features on Hockey App like feedback for example and the user [inaudible]. Then we got acquired by Microsoft.

**CHUCK:** Another new question.

**THOMAS:** Yeah.

**CHUCK:** So I think there’s an assumption here that everybody knows what Hockey App actually is. I mean you’re talking about beta distribution but is that through an app that you already have on your phone that’s Hockey App, or is it another system on the web that allows distribution?

**THOMAS:** Yeah, it’s a combination of both [inaudible] you as a developer so there’s two person with us on Hockey App. One is a developer and one is a tester and tester can really mean your mom, your friend, your idea buddy and our team.

**CHUCK:** But how does mom get the app?

**THOMAS:** So you as a developer start the process by uploading your build. And as a next step, you say, “You know, I want to show that build to somebody,” and you have two options. One is just take the link and send that link out to whoever you want to share it with. It works really well for everything except iOS because on every – like in every order in the Mac, you can just share. Even on Windows, you can just share the build right there. No provisioning, no UDIDs or anything.

Or you can invite somebody and the system sends somebody an email. The email asks you to accept the invite and also install Hockey App on the phone. And on iOS, that means you – what you really do is install a dev clip which is essentially a [inaudible] and you do that configuration process in setting this app. This has the advantage that the UDID is sent back to the Hockey App.

So you as a developer, basically you have a back channel that gives you all the UDIDs and then you add those UDIDs into the Apple provisioning model to actually create the [inaudible] provisioning profile.

**CHUCK:** Okay, and then they can [crosstalk].

**THOMAS:** Then they get another notification saying, “Hey, Chuck provisioned a build for you,” and then they can install the [inaudible]

**JAIM:** So the tester does not have to know what your UDID is. You added [crosstalk].

**THOMAS:** And really before Hockey App and Test Flight, we had to explain to somebody to go to iTunes, find that screen. And it wasn’t actually obvious so that you can select that thing and copy it, you have to know that you have to press Cmd + C and then copy the thing that you couldn’t actually select.

**JAIM:** You have to type it in. Yeah, it was a pain.

**THOMAS:** Well [inaudible], I thought you used that [inaudible] screenshot and then you as a developer would have to keep that thing from the screenshot.

**ANDREW:** Yeah.

**THOMAS:** And then on [inaudible], it’s a native app so you install a native app. You can also install everything from the browser if you don’t need the native app, but it gives you some convenience features like [inaudible] downloads, notifications [inaudible].

**CHUCK:** Gotcha.

**ANDREW:** I’m curious to know if you still use – this is sort of an aside but do you still use PLCrashReporter?

**THOMAS:** Yes.

**ANDREW:** Okay. I think [crosstalk].

**THOMAS:** And we still contribute. And Microsoft talks a little bit of open source. Just today, we announced that Xamarin will be open sourced looking forward.

**ANDREW:** Yeah, it’s fun to see. And I just – I think you guys have contributed a lot to PLCrashReporter but it’s – people who work on that are so smart, I’ve learned a lot.

**THOMAS:** Yeah.

**ANDREW:** So Apple acquired Test Flight and you can do this – some of the same stuff you’re talking about, particularly with the beta distribution is now part of iTunes Connect for Test Flight. It’s of course, iOS only. Beyond that, what does Hockey offer that’s – why should I use Hockey instead of Test Flight?

**THOMAS:** Yeah, and you could – [inaudible] also asked the same question about Google Play which has an alpha, beta [inaudible] feature. Or the Windows [inaudible] which has a flighting feature – they call it flighting. It’s all the same and they all have the same fundamental problem is if you want to iterate quickly back to daily builds, so a build on every commit, and push that to an API back to the test lab, you really can’t go to the public stocks. Apple for example has no API on the first place. There’s some private API tools that Fastlane use so it can [inaudible]. Then the – specifically was test by the other [inaudible] is if you want to do external testing, that means more than 25 people, you have to do reviews. So that’s a seven day review like when you submit to the real store, and that’s just not acceptable for the agile work that you really have to push.

So think about – even at Microsoft, we have many teams that are developing iOS and [inaudible] apps and they’re pushing builds in an insane speed. We’re talking here of 10,000 builds a week. So do we really push those 10,000 builds a week on iTunes or do we really need a system like Hockey App and your build server that work together and allow you to continuously deliver apps to your audience. And that’s really in every Microsoft employee can test those apps.

**ANDREW:** Tell us a little bit about how you can set up a build server. So say I have a continuous integration or a continuous deployment set up, what does it take to make sending builds to Hockey App happen?

**THOMAS:** Yeah. For iOS, you still need a Mac so there’s no way around having a Mac.

**ANDREW:** Sure.

**THOMAS:** So you can use something like Mac on Cloud or MacStadium to host your agents. So your build server needs an agent. One product that Microsoft offers is called Visual Studio Team Services which is really has nothing to do with Visual Studio the box product, it’s an online service that lets you track your [inaudible] items and offers you to get repositories and then build. So to configure build steps that basically push your code to the [inaudible] agent and then compile it, then we have a build step for the Hockey App that uploads the .ipa file to Hockey App.

**ANDREW:** Okay. So personally, we use Jenkins Network and it’s just a – you just have an API end point unless you upload [crosstalk].

**THOMAS:** So you have an API end point, it’s public API. We have an API that [inaudible] to upload builds and we also have API end points for reading data. But for Jenkins, we need the API end point, but in fact for Jenkins, we have to have a plugin. So just install the Hockey App plugin in Jenkins and the build step to your whatever – how many build steps you have, and then say, “This is my API token; you copy that over to Hockey App. And this is my binary and my Jenkins environment, and then use safe and you run your own Jenkins [inaudible].

**ANDREW:** Cool.

**THOMAS:** And it also, again, gives you the advantage. You’re only uploading your builds but you just add the configuration file for the symbol file, and so you get all that symbol files. So even if you haven’t thought about that Chuck could crash your builds [crosstalk].

**CHUCK:** Chuck’s always doing that stuff.

**THOMAS:** Chuck is always doing that stuff, yeah. But it’s really there, the power of continuous integration is that you don’t have to think about it and you don’t forget it. And it’s not limited to Jenkins obviously as the API works with everything that basically can do an HTTP request, so we have [inaudible] users; we have Travis CI users [crosstalk].

**ANDREW:** Right at a [inaudible] or something at the very least. Cool.

**JAIM:** I’m more familiar with Test Flight. That’s what I’d used before it was required by Apple. One thing that I like about Test Flight was it was very low friction. I’m a consultant so I deal with clients, do some work and then I’ll throw out a version of a [inaudible] test within a day or two. Is this what you’re thinking? So that I can quickly invite them. And with the acquisition of Apple, that became too hard to do. We had to go through iTunes Connect, get people signed up there. It’s got too high friction versus what was built on Test Flight.

Does Hockey App allow you to do that sort of thing?

**THOMAS:** Yeah. The process between Test Flight and Hockey App was almost the same I would say. There might be some differences for different target audience or a different taste, but the process is more or less the same as the old test flight. Upload the build, invite your testers, they give you an email, they tap the [inaudible] on the phone, they install the build.

**JAIM:** Okay, low friction wave getting your app out to your users if you’re just starting on a project.

**THOMAS:** Because the users have one big advantage, right? You no longer have to deal with UDIDs. So you don’t have to collect UDIDs and you can target too close and test so it really because – they both now complement each other. If your early stage testing, your internal team, you’re – whatever – 100 UDIDs that you have [inaudible] provisioning, or in the company you’re used and in-house provisioning. You distribute to an internal team and then you decide your close enough to going into production so with that public beta with users and testers, maybe some [inaudible] podcasters and then you submit to those [inaudible]. It also allows you to check for the – Apple allows your build in the app store because you go through a seven-day review so you know whether Apple likes it or not.

**JAIM:** So you get a mini review with a static analysis?

**THOMAS:** Yeah.

**ANDREW:** I don’t think the Test Flight external review is the full App Store review. In my experience it’s not but you at least know that it’s not completely out there. They’re not going to just reject it the second they see it.

**CHUCK:** I have to ask, too, it’s an iOS show and wants to talk about Objective-C and Swift but I’m assuming that this works well for React Native or NativeScript or any Cordova. Then it’s just the same process essentially, because it’s just – it’s a binary and just works a little bit of [inaudible].

**THOMAS:** And Unity and Xamarin, so whatever creates an API can be useful for the [inaudible] plugins for all of them.

**CHUCK:** Right.

**THOMAS:** We actually have another product at Microsoft called CodePush specifically for Cordova and Native developers to update the app without actually submitting a new build. You basically replace the JavaScript under the hood. And so we announced today that we’ve integrated CodePush into Hockey App so you can use the same app ID using API token that you used for Hockey App for your CodePush setup, can directly provision the CodePush app from the Hockey App UI and then all you have to do is in your CLI or in your Jenkins build server called the CodePush CLI and I’ll push your Cordova stuff in addition to what you already pushed for the Hockey App.

**CHUCK:** Right, and that works because Apple has designated JavaScript files among other things to be basically static assets can be replaced.

**THOMAS:** Yeah, kind of. I would say as long as you don’t change the [crosstalk].

**CHUCK:** Yeah, don’t do bad stuff.

**THOMAS:** Well don’t do bad stuff and don’t do stuff that will change the theme of your app.

**CHUCK:** We used to be a gardening app, now it’s rock and roll.

**JAIM:** [Crosstalk] It’s like one bad egg away from [crosstalk]

**CHUCK:** It really does feel that way to me, yeah.

**ANDREW:** [Crosstalk] Abuse it. I think we’re going to talk to somebody from the Cordova tools team tomorrow and I definitely want to talk to them about this whole CodePush thing

**THOMAS:** And you know, you cannot do it anyway because you have to think about any new user still install a [inaudible] app in the App Store.

**CHUCK:** Right.

**THOMAS:** They would always get an update first, so it’s really like a – you found a serious spot [crosstalk].

**CHUCK:** That’s true. That’s the downside, yeah.

**THOMAS:** You cannot wait seven days for the review so you push the hot fix and then you, at the same time, also submit to Apple to get that out for every new user because they have a bad experience that’s telling them, “Oh here’s your new app, and here’s the first update for you.”

**CHUCK:** Yeah, that’s a bad user experience. Yeah, you’re looking forward to using my new app. But wait! You have to wait five minutes for it to update.

**THOMAS:** Yeah.

**ANDREW:** What’s the pricing like for Hockey App?

**THOMAS:** So we have no [inaudible] of two apps that are completely free. All features included; no restrictions whatsoever. And then the next pricing stage is just $10 for five apps, so effectively $2 per app. Then it goes up all the way to $30 for 15 apps and so on. Then the price basically is if you have 500 apps, it’s $500 so the pricing goes down to $1 per app.

**ANDREW:** Per month.

**THOMAS:** Per month, yeah.

**CHUCK:** It seems to me – how many people write one app versus five apps versus ten apps? I know some developers that are fairly prolific, but I know other app developers that they wrote the one app, they want to write so you’d never make any money on them.

**THOMAS:** Well, that might be but then you have the one app and then you’d think about the B2, so you’re already getting into the second app unless you put the B2 on top of your first app. Lots of app developers in the app store these days, that the B2’s actually a separate project, right? It’s a separate bundle identifier and separately charged because there’s an update pricing [crosstalk].

**CHUCK:** Yeah, that always makes me happy when I have to pay for the new version of the app I already paid for.

**ANDREW:** I think another smart thing about that kind of pricing is that if I write an app on my own just for fun in my spare time and I can release it, I can use Hockey App and it’s free because I don’t think I’m going to make any money and I love Hockey App, then next time that I’m at work and we have ten apps on the store and we’re looking for a solution, I’m going to think Hockey App because it works so well for my own projects.

**JAIM:** Yeah. If you’re going to make money of indie developers, you’ve got a really hard road ahead of you. That’s some of the cheapest people on the planet just because they –.

**CHUCK:** But people just want to try it, too. That makes a lot of sense.

**JAIM:** If you want to make a lot of money, you sell it to bigger companies who have a lot of apps. Now one thing I do or some of my clients do with bigger companies, they got four or five apps, but they’ve got CI running for different branches. So they’ve got a ton of apps [inaudible]. Is that covered? Is it by bundle ID or if you have [crosstalk].

**THOMAS:** No, it’s a separate app. So that’s because you gave – the trick behind the pricing model, if you’re really doing 50 versions of the same app, that counts as 50 apps, not as one app. But the indie developer wouldn’t do that so it’s kind of like a fair share. It’s like you buy an AT&T contract, it’s kind of like flat pricing unless you go into a certain limit and then they – [inaudible] you are asked to update to a bigger plan.

**JAIM:** So if it’s a CI system, you’ve got five apps, you’ve got 50 features in [inaudible] branches. They’re going to CI, posting it; people are downloading and testing then that’s how you can [crosstalk].

**CHUCK:** So if they merge it all back to master and they all go out under Zuber app one then it’s one app and then when you get around the Zuber app two or Zuber app with extra features, then it’s.

**THOMAS:** If you feel the need that you only need five or ten branches at the same time, then you pay for the [inaudible] apps.

**CHUCK:** You need to pay for each one.

**ANDREW:** How long ago did Microsoft require Hockey App?

**THOMAS:** December 2014 so that’s like 15 months now.

**JAIM:** What was that process like? It is very interesting; they are two independent companies doing similar things – Test Flight and Hockey App – and within some strange turn of events, Test Flight now owned by Apple, Hockey App now with Microsoft. What was that like from your perspective? It is interesting to me.

**THOMAS:** So the Test Flight getting acquired was actually awesome because within a month, Apple shut down [inaudible] so all the [inaudible] developers on Test Flight had to find a new home.

**JAIM:** Okay.

**THOMAS:** Some went to the competitions, some went to us to so we got source [inaudible] uptake. Same thing happened when apple shut down the old Test Flight. That was like the after our acquisition, early 2015. Apple shut down the old Test Flight and we pretty had to move to the new Test Flight, we saw another uptake. And because there are still users using the old Test Flight because they love the convenience about this. And so that was a positive effect. You always hear about getting [inaudible] or anything but the reality is that it’s no longer happening because Apple provides really just the basic solution. Then you can differentiate yourself from that solution and get customers.

**JAIM:** So how does Microsoft go about acquiring a company? Do they send you an email? [Inaudible] has Hockey App?

**THOMAS:** No. [Chuckles] No, but other companies, you do a demo. So we do like an innocent demo. It’s basically ‘can we see the [inaudible]?’ And we thought it’s another team in Microsoft that wants to use us.

We had Microsoft [inaudible] was in 2011. Skype team was using the Hockey App since we did the [inaudible] so we didn’t think really about [inaudible]. So if you do a demo and somebody from the demo pings your Skype or chat and says, “Hey, would you be interested in discussing a deeper relationship?” That’s just really an open discussion about becoming a partner, contractor or maybe getting acquired. Then eventually, the legal team and these developers get involved and so they negotiate an LOI. You sign an LOI [crosstalk].

**CHUCK:** LOI?

**THOMAS:** LOI, also an acronym talk – a letter of interest. So it’s basically the offer that [inaudible].

**CHUCK:** Right.

**THOMAS:** You sign that then you do a [inaudible] process and you sign the deal. It’s like – I would say it’s probably pretty common in the industry how that works.

**CHUCK:** I warned you that I ask the dumb questions.

**THOMAS:** Yeah, that’s fine. The bigger the company, the more acronyms exists.

**CHUCK:** Yeah.

**ANDREW:** For people who are using Hockey App, what has changed? Why is it good that Microsoft bought Hockey for those of us who are potential customers?

**THOMAS:** We actually had a lunch with these customers today and one of the customers said, “Well, it’s much easier now.” He’s a contractor, to recommend Hockey App to his customers because it’s Microsoft Hockey App. So Microsoft gives them confidence that the product is actually there in a couple of years and it works. And so that’s much easier in a way.

The same time, if you look into the indie scene, it became a little bit harder because if you’re [inaudible] startup and you start up without any funding or anything, maybe just have four guys founding a company, then you have the sympathy of the indie developers. And so they might support you just because you’re on the same boat as they are. So that became harder so it’s harder to speak to the indie developers; it’s easier to speak to the enterprise developers.

**ANDREW:** I think Jaim mentioned – we were talking yesterday and he mentioned he had a client that was like, “Oh, I don’t want to use Hockey because they’re Microsoft.” I think there’s a feeling – Parse for example is a situation where this was a service that a lot of people use and then Facebook bought Parse and then two years later, they shut Parse down. It’s a little silly because if Facebook had not bought Parse, maybe they would’ve shut down earlier because they wouldn’t have the money to keep going or whatever. You never know.

**CHUCK:** The other thing about that though is when they shut down Parse, they open sourced Parse. So you at least had that much going for it where, okay, I can spit on my own Parse. It’s not as ideal because I don’t want to have to do that.

**THOMAS:** I would argue. Customers who have been using Parse, who are using Parse because they didn’t have to handle their own service and have to maintain them. That’s always a danger; nobody knows what is in five years.

We have paid products so we have customer commitments. We have offered yearly plans; we have always had confidence and in a year, we will for sure be there because we have that commitment.

And we’ve adjust in a process where we consolidate other services into our Hockey App. A couple of weeks ago, we announced that application and sites in the Microsoft product – all the mobile features there go away and they move over to Hockey App.

Today, we announced that the Xamarin insights team will join the Hockey App team and brought together on Hockey App. We set everything on Hockey App so that gives customers a little bit of confidence. But sure, there’s this uncertainty and you never know what will happen.

**ANDREW:** Yeah, it’s true. Any product, right? You can’t guarantee any [inaudible].

**THOMAS:** We’re investing in it and we’re launching new features almost every week.

**ANDREW:** Sounds like you feel like joining Microsoft has given you more resources and the ability to – you’ve got more people coming into the team.

**THOMAS:** Yeah, the team is now almost three times the size as it was before. They [inaudible] even though the Xamarin acquisition. You sure have more resources and you have more confidence. You don’t have to be scared. What happens if Apple really [inaudible] me and we are going out of business because we can no longer afford to pay for ourselves and [inaudible]. At the same time though, big company also means things are slower or less agile. You have longer decision process. It’s just the way companies work.

It’s a little bit good and bad. I’d say overall, we did a good job and we are here 15 months after the acquisition. The product is almost the same as it was in terms of pricing, in terms of offerings so we didn’t take away the open source SDKs, we didn’t neglect iOS and Android or Mac OS for that matter. And we are investing in adding new features.

**ANDREW:** That actually leads me into something else I want to ask you about which is one thing that’s attracted me about Hockey App, I’m a Mac develop first and foremost and I also do iOS and you’ve always had great support for the Mac which is cool, but you support these other platforms, too – Android, Windows and Xamarin, Unity and whatever. What’s the mix of your customers? Are they mostly – I think your strong roots are probably kind of iOS and you still have mostly iOS developers. There’s a pretty even split between iOS and Android and Windows.

**THOMAS:** Yeah, I would say it’s – we have the [inaudible] in iOS. We are all iOS guys by heart. I was actually doing [inaudible] when the iOS comes at us [inaudible] when we started the Hockey App. So we were doing some Android.

It is about – not about the market share because Android would need its more – profit shares. So iOS has the biggest – bigger share. Android is a close second. Those other platforms are like Windows and Mac because Windows, you can put a .zip file into [inaudible] everywhere so distribution’s kind of easy. You don’t need to [inaudible] your interface or the [inaudible] to install the build or a provisioning.

**CHUCK:** Is that true of Windows mobile or Windows phone apps?

**THOMAS:** I mean it’s not true of Windows mobile. It’s no secret that Windows mobile has no market share.

**CHUCK:** Right.

**THOMAS:** So that’s the answer to the customers that love to have all the three platforms like the mobile platforms iOS, Android and Windows on Hockey App because they’re big enterprise customers, specifically agencies, that require them to deliver a solution for all three, so they don’t have to look for a separate solution for the Windows phone.

**ANDREW:** Well, I can’t speak for the other platforms but crash reporting for Mac apps is probably even worse for crash reporting for iOS apps in some ways because – Apple symbolication for Mac crashes, Apple does – Xcode doesn’t know how to symbolicate Mac crashes as all. Apple has no iTunes connect crash reporting. People think they crash when they hit send to Apple, [inaudible] to the developer early because it’s in a garbage bin at Apple somewhere. [Chuckles] So that’s something that you still have an advantage for desktop software.

**THOMAS:** Well even in iOS we have that advantage because getting it from iTunes Connect is not all the crash reports.

**ANDREW:** Oh right.

**THOMAS:** You get just the subset and that is really driven by legal concerns on Apple’s side because if you would get every single crash report, right then you would be able to identify user of that crash report as very specific to the device type of the country or whatever. So they filter very high and all they get really is a subset of the crash reports. If it’s a one-off, you would never see it because it never appears on iTunes Connect.

Then Mac, I don’t know why Apple is doing this. It’s like the same sad story of the Mac App Store, why there’s no Test Flight for Mac. I don’t know.

**ANDREW:** We’re all used to it now, us Mac users.

**CHUCK:** So with the crash reporting, is that just an SDK or a framework you can pull into your application?

**THOMAS:** It’s basically [inaudible] of CocoaPods or whatever to the application, you initialize your SDK with that app ID that you get from our portal. You compile and run. That’s really it.

**CHUCK:** Right before you die horribly, send the information over.

**THOMAS:** On the app itself when the app crashes and the only thing the crash reporter does, and that’s true for everybody in the industry, not only for the Hockey App. The SDK only store [inaudible] part on the device.

**CHUCK:** Oh really?

**THOMAS:** There’s no sending because what happens if the crash is happening, a signal handler is called and that’s really a low level UNIX concept. That signal has to be async safe so it means it can be called multiple times. And you only have 50 methods from the C library available that are truly async safe. So really, the only thing that you can safely do is to start a [inaudible] on the disk.

**JAIM:** Okay.

**THOMAS:** So next time you launch the app, you have a dialogue asking you whether you are to support the [inaudible] part or not because then you support the [inaudible] part. You can hide the dialogue and then automatically send from the developer’s perspective if you want that. And it probably depends on your target audience. If you have a game that’s for kids, you probably want to ask and make sure they are not violating any proper laws or something, child protection’s act.

**CHUCK:** Right.

**THOMAS:** If it’s not [inaudible] or you have to collect any personal data, you can auto-sync [inaudible].

**ANDREW:** And this is one – I mentioned I really liked the – I find PLCrashReporter a really fascinating project. Part of that is because you have to write code that runs signal handlers; so difficult to get right and so easy to do something really wrong. So the way they’ve been able – that you guys have been able to make that work so well is really impressive to me. It’s not an easy problem to solve.

**THOMAS:** Yeah. And it’s not specific to iOS [inaudible]. On Mac, we also have PLCrashReporter and then on Android – so Android, there’s two platforms [inaudible] the SDK and the NDK and NDK stands for Native Developing Kit and you [inaudible] writing C and C++ apps there. So we need something similar to PLCrashReporter and there’s a Google open source project called [inaudible] that does this similar thing that people [inaudible].

**CHUCK:** This is really interesting. It’s like another end of the iOS development that I just never – I think I would’ve gotten into a [inaudible] if I did more apps.

**THOMAS:** Yeah. Isn’t it kind of – if you think about it, if you had asked me two years ago, “Could Microsoft be the company that offers you open source crash reporting in iOS?” You would’ve thought, “No way. That’s not happening.” So that’s kind of like a challenge but also cool that Microsoft is now on that space, the same as the [inaudible] on Windows and other stuff that Microsoft is presenting here at Build.

**CHUCK:** It’s funny because I’ve talked to so many people in this conference that have said basically the same thing. If you would ask me two years ago or five years ago or whatever, if I would ever be doing blah at Microsoft, I would’ve told you there’s no way.

**ANDREW:** If you’d asked me five years ago if I would be at Microsoft Build recording iOS podcasts, I would’ve said, “Maybe in [inaudible] world, maybe.” [Crosstalk]

**CHUCK:** Whatever you’re smoking, it must be really good. [Chuckles]

**ANDREW:** It’s been fun to be here though.

**CHUCK:** Yeah.

**ANDREW:** And see this new [crosstalk] Microsoft.

**JAIM:** Yeah. What’s next for Hockey App? So you got this big stuff behind you, you’re a product manager. What’s next?

**THOMAS:** We are currently having the investing into usage data, so collection of custom events, how many users and [inaudible] we have. Kind of like Google Analytics of [inaudible] but as part of the Hockey App offer, it was the same premise that it’s your data. We’re using the data for any advertisement purposes, for any – and mining anything. It’s really giving the developer the toolset to see what’s happening in the apps. I think those – we just launched custom events today so you do a simple tracking [inaudible] in the app and then you see on the Hockey App UI, how many users – unique users have [inaudible] that event in the last seven days, in the last 24 hours and so on.

**CHUCK:** Okay. With that, there’s all kinds of ways that you can segment the data and look at the data and decide what matters and what doesn’t. So I’m curious, do you expect the developers to put together all the metadata on that or do you have other analysis tools that are going to be built into that? For example, if I decided I wanted cohorts or version to the app or build to the app or any of those that I can say, “Okay, well I’m only interested in this segment right now or whatever.”

**THOMAS:** I would say there’s tons of ideas in the team of what we can do in the future, but now we are really focused on delivering the basic story in a way that’s scalable, sustainable and then still open source and available to everyone. Once we have that, we would probably go down that road that you have outlined. But right now, there’s no announcement on that.

In the same fashion, you can talk about auto-instrumentation that the SDK does some logic itself, like [inaudible] a page view but just really like a view [inaudible] transition on iOS or tracking a network event on measuring how long the [inaudible] for the API took. We call that dependency tracking. There’s all kinds of directions you can go and they can improve such a basic system that could [inaudible] from the app.

**CHUCK:** So one other thing that I’d just want to ask and we talked our way around some of this but let’s say that somebody’s listening and they’re going, “Well, that sounds like what I need. I really want to get started with Hockey App. I want to go use this in the app so that I’ve got it out there already. Or I’m going to write a new app and I’m just going to get going with Hockey App.” What do they do? They just go to hockeyapp.com and sign up or is there more to it than that?

**THOMAS:** You go to hockeyapp.com or hockeyapp.net – doesn’t really matter. You get to sign up for free; you put in your email and password, that’s all we need. You can also use your Twitter account, your Google account and Microsoft account to sign up. Very simple. We don’t collect any data from you; we don’t need the credit card or anything like that. You confirm your email address – it’s the only thing we ask you, that you’re really you and not somebody else. Then you – if you already have a build then that’s really as simple as taking that build and dragging the [inaudible] to the browser [inaudible], it uploads. We don’t ask you to ask – to integrate the SDK or do any other requirements and you send the build to your testers. Then of course, you want to collect data so we show you how to integrate the SDK. That’s really like downloading the [inaudible], putting it into a project, initializing the SDK. 10 to 15 minutes, you’re done.

**CHUCK:** Okay!

**THOMAS:** After months that you have [inaudible] your first apps, so we actually – don’t stop the trial when you sign up. [Inaudible] when you create your first app. After a month we’ll tell you know, if you have more than two apps, you need to sign up for a paid plan. If it’s less than two apps less or equal than two apps, then you just stay on the free plan. Ten if you use Jenkins, you install the Hockey App plugin. On VSTS, you can actually private repositories for free, [inaudible] for free. Five users are completely free so you get everything on Microsoft that you really need for the development cycle.

You don’t get the max. So for the Mac, you either have to have your own Mac under your desk and that mac under your desk could connect to the Cloud, to rebuild stuff. Or you buy something for Mac and Cloud [inaudible] like $30 a month.

**JAIM:** The crowd’s excited.

**ANDREW:** Yeah, they had like applauses [crosstalk].

**JAIM:** We’ve got this on our presentation right next to us so we get some random clapping every once in a while.

**CHUCK:** Yay!

**JAIM:** I’m really excited about the Hockey App. I should ask one thing before – because I know some of our listeners are thinking about his. And we talked about my client last year who’s like no Microsoft. I don’t know if they’re going to do it with the data. Do you do it with the data? Do you upload?

**THOMAS:** Hockey App is as part of a group in Microsoft that’s called C&E which means Cloud and Enterprise that all [inaudible] Azure. And Azure and Hockey App and other services in that space, they all have the same premise. It’s the customer’s data but full trust in us so we don’t use it for anything except for [inaudible] the service. If you see that you have an issue, for example, crash reports. For example – whatever, [inaudible] comes out and you get weird arrows like our services are pulling [inaudible], we will of course improve our service and remove those exceptions. If you’re not looking into it, we’re not installing your builds. We’re not seeing your builds unless you ask us to look into things and see.

A common problem is if somebody says, “Hey, I’ve edit that UDID to my provisioning profile and it still don’t work,” we might look into their account and check the provisioning profile and figure out all the [inaudible] that’s missing because why he [inaudible] the ID has newly download the new profile and imported it to Xcode. Xcode is [inaudible], it’s [inaudible] and not using their profile. Things happen. Kind of like the secondary Apple support in some [inaudible].

**JAIM:** Did you see the Xcode dance when you updated the provisioning profile?

**THOMAS:** What do you mean the Xcode dance?

**JAIM:** Just like [inaudible] whatever you have to do, [crosstalk].

**THOMAS:** Yeah. I mean it’s [inaudible] and you import them and stuff like that. [Crosstalk] The way to understand Microsoft is not using their data. It’s your data and you have full control over the data. If you delete the data, the data’s gone. We actually have [inaudible] where you can actually delete your data and your full account. So there’s really no – there’s no hidden agenda what we do with the data other than providing the service.

**CHUCK:** So what you’re saying is you might look at some of the data to figure out why something broke or crashed, or if you’re seeing widespread problems across multiple accounts, what do these accounts have in common, but other than that you’re not?

**THOMAS:** Yeah, it’s not the way like they are not looking to the Facebook at Yahoo have the same problem, it’s more like now we have our own internal crash reporting on our service.

**CHUCK:** Yeah.

**THOMAS:** So if you see the exception, you try to figure out what the exception cost then we might see some of the data as part of the exception. But it’s not like somebody has a list or dashboard where they can see [crosstalk].

**CHUCK:** All of Andrew’s users. We should go email those people. [Crosstalk]

**THOMAS:** And we also go through the dance where we publish something like iOS 9 is more stable than iOS 8 by looking at the crash data that we get from developers. We don’t do that. We are not interested in that kind of intelligence.

**ANDREW:** Okay.

**THOMAS:** We’re not in that business. We’re in the business of – we are part of Microsoft and C&E and what’s called the developer division. [Inaudible] Visual Studio’s the main supporter. I can be interested in providing a service and a product and developers. That’s it.

**CHUCK:** Cool.

**ANDREW:** Anything else we should talk about before we wrap it up? I think we’ve covered a lot.

**JAIM:** Yeah, it’s good stuff.

**CHUCK:** We should just start skating to where the puck is going to be.

**ANDREW:** Yeah.

**CHUCK:** I read that right off of Thomas’ shirt. It’s kind of funny with this in person.

There are two things that I’ve been doing at the end of these interviews that I want to make sure that we do here. The first one is to thank Richard and Carl from the .NET Rocks. We teamed up with them to make this happened. We’re actually recording on their equipment and it’s been awesome. They really did make the arrangements so that we could come up and do this.

**ANDREW:** And they’ve been really good to us and fun to be around.

**CHUCK:** Yeah.

**ANDREW:** They’ve made it a fun time for us.

**JAIM:** They fed us well.

**CHUCK:** Yes.

**JAIM:** [Inaudible] Steakhouse meal last night.

**CHUCK:** The other thing is, on our shows, we do what we call picks. Since we’re going to be doing several of these shows over the next few days, I haven’t been having to host to do the picks, but I have been having our guests do the picks. So what picks are are just things that you’re into at the moment. Some people pick TV shows or movies or music or books or something like that. Then other folks are like – my favourite code tool is this thing or this framework or library really makes my life better. So what are one or two things that you’re into at the moment?

**THOMAS:** my pick for today is a Tesla Model 3 because it races – it’s a car company from Silicon Valley that is able to raise the same level of excitement that Apple used to raise [inaudible] to a product. So you probably have seen all the videos, how people lined up for a model [inaudible] without even seeing it, putting down a thousand dollars to reserve a car that’s not launching for another year a and a half. That’s really a new world that we’re living in where an electric car can raise a level of excitement and it excites me and I’m looking forward to see the presentation tonight.

**CHUCK:** I was going to say the presentations tonight [inaudible].

**ANDREW:** Yeah, 8:30.

**THOMAS:** 8:30.

**CHUCK:** When this goes live, old news but it’s cool.

**THOMAS:** It’s like [inaudible]. It’s now almost 10 years ago that the iPhone was shown. That was the first time that we had phones that would auto-update themselves. We are no longer locked into an ecosystem – well, you’re locked in the Apple ecosystem but not like [inaudible] stuck on an OS version forever until your contract ended. And now Tesla’s doing the same with cars where the car updates itself every other week. If they have a new feature, they just push software to the car. That’s like – that’s all an electric car so feels like the future’s very exciting.

**ANDREW:** Well in Apple, one of the things about the iPhone is it was this idea that the device was almost nothing more than a screen, and so the device can be anything you wanted it to be through software. And it’s pretty cool to see Tesla – the Teslas that are already out there, they’ve already rolled out features – huge, new features that are just software features. You don’t have to buy a new car. You get some self-driving feature.

**THOMAS:** And for free, right? It’s new features for free. You don’t have to go to the dealer and get a new navi DVD for fifty bucks. Why don’t you just get a new map data? You just get the map data from your car and they have Bluetooth and LTE and everything. So it’s like super cool and super exciting.

**CHUCK:** Yeah, and you don’t have to plug it into your Mac so that you can [chuckles] – iTunes 6 on the [inaudible], right?

**THOMAS:** Right. It’s the same kind of – it’s the iPhone. You just have a screen and your Tesla just have a screen like this. No more buttons except the steering wheel and the turn signal. So it’s like the same approach and the same kind of – it’s a close ecosystem so it can [inaudible] but it’s kind of open because you have the custom [inaudible] very high by getting updates, by getting new features and stuff like that for free.

**ANDREW:** It’s exciting times.

**CHUCK:** Yup. Tons of new stuff coming out. Alright, well thank you Thomas for coming. We’ll go ahead and wrap this up and forward to more interviews here at Built.

**THOMAS:** Thanks for having me and may be for one last word, it’s awesome to talk to you guys. It’s great that you’re here. One premise we always have in the Hockey App team is that we love to talk to developers, we love to see what they’re doing and so even now that we are at Microsoft, it’s still my team, everybody in the engineering team doing all the customer support and we love just talking to the community.

**CHUCK:** Yeah. If people do run into questions or anything, do they just go to hockeyapp.com?

**THOMAS:** Yeah, they can go to hockeyapp.com. They can go to at hockeyapp.net, @hockeyapp on Twitter or support@hockeyapp.net.

**CHUCK:** And are you on Twitter or Github with a handle for people to [crosstalk].

**THOMAS:** Yeah, it’s ashtom like an anagram of Thomas. But otherwise, I’m also responding on Hockey App.

**CHUCK:** Awesome.

**ANDREW:** Thanks Thomas.

**THOMAS:** Yeah, thank you guys.

**JAIM:** Yeah, great.

**_[Hosting and bandwidth provided by the Blue Box Group. Check them out at BlueBox.net.]_**

**_[Bandwidth for this segment is provided by CacheFly, the world’s fastest CDN. Deliver your content fast with CacheFly. Visit cachefly.com to learn more]_**


