---
layout: layouts/post.njk
title: >
      260 RR Training with Reuven Lerner
date: 2016-05-18 07:00:05
episode_number: 260
duration: 52:58
audio_url: https://media.devchat.tv/ruby-rogues/RR260TrainingReuvenLerner.mp3?rss=true
podcast: ruby-rogues
tags: 
  - ruby_rogues
  - podcast
---

### Want to be a Ruby Rogue? Apply at [https://rubyrogues.com/ruby-nuby](https://rubyrogues.com/ruby-nuby)
&nbsp;01:47 - Reuven Lerner Introduction
- [Twitter](https://twitter.com/reuvenmlerner)
- [GitHub](https://github.com/reuven)
- [Blog](http://lerner.co.il/)
- [The Freelancers’ Show Podcast](https://devchat.tv/freelancers)
- [Practice Makes Python by Reuven Lerner](http://practicemakespython.com/)
- [Practice Makes Regexp by Reuven Lerner](http://practicemakesregexp.com/)
- [Daily Tech Video](http://dailytechvideo.com/)
03:49 - Training
- [Pedagogy](https://en.wikipedia.org/wiki/Pedagogy)
07:54 - Approaching Teaching
- [Mental Model](https://en.wikipedia.org/wiki/Mental_model)
09:33 - Pairing People Up
- [Metacognition](https://en.wikipedia.org/wiki/Metacognition)
10:57 - Example: Reuven’s Training Sessions19:59 - Moving Up The Ladder24:06 - Company Goals25:56 - Hostile Learners28:00 - Breaking Into the Big Company Market
- [LinkedIn](https://www.linkedin.com/)
- [Devchat.tv Interest Survey](http://goo.gl/forms/RAjGRT8Ia6)
35:03 - Offerings37:53 - Cultural Differences&nbsp;Picks
- [Society Of Mind By Marvin Minsky](http://www.amazon.com/Society-Mind-Marvin-Minsky/dp/0671657135) (Reuven)
- [Peter Hessler's Books](http://www.amazon.com/Peter-Hessler/e/B001ILMA1C) (Reuven)
- [Regexp Crash Course](http://regexpcrashcourse.com) (Reuven)
- [rspec-given](https://github.com/rspec-given/rspec-given) (Sam)
- [Katrina Owen on Confreaks](http://confreaks.tv/presenters/katrina-owen) (Sam)
- [github-shoutouts](https://github.com/finnp/github-shoutouts) (Coraline)
- [Ruby Together](http://rubytogether.org) (Coraline)
- [Ruby Rogues Episode #224: Ruby Together with André Arko](https://devchat.tv/ruby-rogues/224-rr-ruby-together-with-andr-arko) (Chuck)
- [Ruby Remote Conf](https://allremoteconfs.com/ruby-2016) (Chuck)
- [FitBit One](https://www.fitbit.com/one) (Chuck)


### Transcript

**_[This episode is sponsored by Hired.com. Every week on hired they run an auction where over a thousand tech companies in San Francisco, New York, and L.A. bid on Ruby developers providing them with salary and equity upfront. The average Ruby developer gets an average of 5 to 15 introductory offers and an average salary offer of $130,000 a year. Users can either accept an offer and go right into interviewing with a company or deny them without any continuing obligations. It's totally free for users. And when you're hired, they give you a $1,000 signing bonus as a thank you for using them. But if you use the Ruby Rogues link, you'll get a $2,000 instead. Finally, if you're not looking for a job but know someone who is, you can refer them to Hired and get a $1,337 bonus if they accept the job. Go sign up at Hired.com/RubyRogues.]_**

**_[I'm excited to tell you about a new sponsor to the show, Rollbar. One of the frustrating things about being a developer is dealing with errors. Ugh. Relying on users to report errors, digging through log files to debug issues, or a million alerts flooding your inbox ruining your day. With Rollbar's full-stack error monitoring, you get the context and insights and control you need to find and fix bugs faster. It's easy to install. You could start tracking production errors and deployments in eight minutes or less, or automatically create new issues in GitHub, JIRA, Pivotal Tracker, et cetera. They have a special offer for Ruby Rogues listeners. Go to Rollbar.com/RubyRogues to sign up and get the bootstrap plan free for 90 days. That's 300,000 errors tracked free. Give Rollbar a try today. Go to Rollbar.com/RubyRogues.]_**

**CHUCK:&nbsp;** Hey everybody and welcome to episode 260 of the Ruby Rogues Podcast. Today on our panel we have Sam Livingston-Gray.

**SAM:&nbsp;** All we are is dust in the wind, dude.

**CHUCK:&nbsp;** Coraline Ada Ehmke.

**CORALINE:&nbsp;** Hi.

**CHUCK:&nbsp;** I'm Charles Max Wood from DevChat.tv. We have a special guest this week and that's Reuven Lerner.

**REUVEN:&nbsp;** Hi everyone.

**CHUCK:&nbsp;** I'm going to go ahead and take a stab and do a little bit of a personal introduction for Reuven because I know him rather well. We talk every week on The Freelancers' Show which is a show that we do with Jonathan Stark and Philip Morgan about freelancing.

**REUVEN:&nbsp;** We have much more boring introductions too, I must say.

**CHUCK:&nbsp;** Yeah. And Reuven, he's written a couple of books. He's written 'Practice Makes Python' and 'Practice Makes Regexp'. Have you actually released the regex book yet?

**REUVEN:&nbsp;** Yeah, yeah. Both of that. I'm working on the videos for the regex book still.

**CHUCK:&nbsp;** Okay. And then he also does some corporate training for some rather large companies that you've probably heard of. And yeah, so anyway I've gotten to know Reuven over the last few years. And it's a lot of fun to talk to him every week. I also, before we get going too far, I want to remind everybody about the Ruby newbie dealio that we've got going on. If you want to be a member or a Ruby Rogue, then that's the way to do it. We're looking for somebody with a newbie voice to add to the show since we're looking for different perspectives, something that will add to the show. And we felt like Saron really added that to the show but she is no longer able to do the show. So, if you're interested in that, go to RubyRogues.com/ruby-nuby, nuby spelled N-U-B-Y. And that will give you a chance to get the guidelines and we're looking for you to submit a YouTube video that we can watch and put in a playlist. And then we'll bring the finalists on to the show and then we'll choose somebody to join us.

**CORALINE:&nbsp;** I met a lot of early career developers at RailsConf this past week and I'm hopeful that some of them at least will apply, because I think there are some really amazing people who are just getting started in their Ruby careers and it would be great to have their voices heard.

**CHUCK:&nbsp;** Yeah, I have to agree. I wasn't at RailsConf but just being out there in the community and having people for example call in and do, I do 15-minute chats with podcast listeners and I've had a lot of new people call in. there are a lot of tremendous people out there who really do interesting stuff even though they're really new. And so yeah, don't let being new stop you. Please apply.

So Reuven, we're going to be talking today about training. And in particular you've been doing this training in larger corporations. Do you want to briefly tell us how you got started with that?

**REUVEN:&nbsp;** Yeah. So, I've been a developer now for more than 20 years, as my increasingly gray hair makes it clear. And I've been a consultant also for 20 years, since 1995. And at some point early on, my consultant clients started to say, “Well it's really great that you can do this programming for us. But maybe you can show us how to do what you're doing. Can you give us a lecture?” And so, it started being once a year. And then it was twice a year. And then I started doing it more and more. And I did a PhD a few years ago. And when I came back to Israel after doing that, of doing the course work, I decided to hook up with a training company here in Israel. And then it started to be a real torrent. Lots and lots and lots of training. Until I realized well, we constantly give people advice on The Freelancers' Show that they should find a niche and stick with it. I really enjoy it. There are tons of demand for it. It pays well. Why am I fighting this? Why am I still looking for development jobs?

So, I guess about a year, a year and a half ago, I decided that the overwhelming majority of my time would be spent doing training. And I've been doing that. I still do some consulting and programming on the side for clients and elsewhere. But that's the bulk of what I do and I haven't looked back. And I'm very happy with it.

**CHUCK:&nbsp;** That's really cool. And I think a lot of times people get it in their heads that, “Oh wow. I have to be like this massive guru in order to go do training.” And it sounds like you just made the decision then it worked out that way.

**REUVEN:&nbsp;** Yeah. Look, the more you know certainly the better. But that knowledge comes over time. And it's actually two kinds of knowledge. So, I'll put on my PhD egghead hat here for a moment. So, in the education biz you talk about content knowledge which means knowing the domain and you talk about pedagogical content knowledge, which means knowing how to explain the domain. And these are two…

**SAM:&nbsp;** Yeah.

**REUVEN:&nbsp;** Different skills. And so, I'll just [inaudible]. One of my favorite stories when I was being interviewed for undergrad studies in the US, so the [guys] interviewing me told a story about how during World War II all the seniors professors were teaching undergrad introductory courses because all the junior professors were off in the army doing war stuff. And so, the story is the senior math professor comes out to the class. And he says, “Does anyone have any questions about the homework?” like intro math 101. And someone says, “Yeah, could you do problem number five?” And he says, “Uhuh, uhuh, uhuh,” and writes the answer on the blackboard. And the students are like, “Is there another way to do that?” And he goes, “Uhuh, uhuh, uhuh,” and writes the same answer and says, “But that way is harder.” And…

[Laughter]

**REUVEN:&nbsp;** We know plenty of professors who work that way because for them it's so obvious how to get from A to B. And so, part of training means not only knowing the subject well but knowing how to break it down to the steps. And if I were to go back in time even I'd say two or three years and look at myself teaching, I'm sure I would be aghast at some of the gaps in what I was describing in training. And easily, easily half to two-thirds of what I teach now is based on questions I get from my students who help me to fill in those gaps.

**CORALINE:&nbsp;** I really wish that pedagogy was something that you could teach people like bootcamp instructors.

**SAM:&nbsp;** Oh my, yes.

**REUVEN:&nbsp;** [Laughs] I've never been exposed to bootcamps. But my impression was they were good at this. I guess from the two of you I'm learning that is not the case.

**CORALINE:&nbsp;** It is… expertise is unevenly distributed.

**SAM:&nbsp;** Yes.

**CHUCK:&nbsp;** I was going to say, I think it depends on the bootcamp and the instructor. But yeah.

**REUVEN:&nbsp;** Mmhmm.

**SAM:&nbsp;** Definitely. I've seen some amazing people in bootcamps and I also know some people that I'm like, “I'm not sure I would trust you with a codebase let alone students.” So, there's a range.

**CHUCK:&nbsp;** Yeah. I do think it's interesting though. I remember having professors and some of the professors explained things really, really well and some of the professors didn't explain things really well. And some of the professors, it didn't matter because after about five minutes of hearing them speak I was asleep.

**REUVEN:&nbsp;** [Laughs]

**CHUCK:&nbsp;** And so, I think…

**SAM:&nbsp;** That's when it really, really matters, Chuck.

**CHUCK:&nbsp;** [Laughs] It didn't matter how good they were because oh my gosh, I can't stay awake.

**CORALINE:&nbsp;** You wake up and suddenly World War II is over.

**CHUCK:&nbsp;** Yeah, exactly.

**REUVEN:&nbsp;** [Laughs]

**SAM:&nbsp;** [Inaudible]

**CHUCK:&nbsp;** So, it's interesting. How do you… it's one thing to be able to explain this stuff to students and I think we can talk about how to run a training session or a few days of training. I'd also like to get into how you get in the door with some of these companies that do the training. But so, you talked about pedagogy. I'm curious though. Are there particular techniques or particular ways that you approach teaching so that it makes sense to people?

**REUVEN:&nbsp;** So, I'm big on the whole idea of mental models. I'm [inaudible] big on if you understand how something works, then you understand first of all the documentation that was written by the people who understand how it works and don't realize how to write for people who don't know how it works. But you can also then sort of play with it in different ways. So, it's not necessarily enough to know, “Oh, this is a string.” You want to know, how does a string work? And what does it contain? And what does it do quickly and what does it do slowly? And if you have a model of how it works behind the scenes, and I'm not at all talking about diving into the [C] code because believe me I would be the last person to do that, but getting a sense of… a good feel, an internalized feel for it.

I often describe even learning programming languages as like learning a natural language, that it takes a lot of time and a lot of practice to internalize it. So, you can talk about it until you're blue in the face. But it's only when they really try things and fail and realize where they've got mistakes in their mental models and they need to fix them that things really happen. So, having lots of exercises and demos and exercises that are sort of evil and purposely will trip them up if they are not thinking in the right way. So over time, my exercises have I think improved a lot because I see what was too easy for people and I make it just a little bit of a sharper edge that the people who really get it will have no problem and the people who don't will have to get it.

**CORALINE:&nbsp;** What's your feeling about pairing people up in exercises? I've taught some Ruby classes to beginning programmers. I find that some people seem to get it really quickly and others need a lot more work. And I've tried various things. I've tried having people work independently. I've tried letting them pair on their own. And I've tried deliberately pairing up a person who's struggling with someone who gets it. Do you have any opinions on what works best in a situation like that?

**REUVEN:&nbsp;** So, I've never tried deliberately pairing people up like saying, “You are with you and you are with you.” Every so often someone raises a question I'm like, “Oh, that's a really good idea. I should really try that.” So, that's a really good idea. I should really try that.

[Chuckles]

**REUVEN:&nbsp;** But I will very, very often, I would say in every class I will tell people, “Listen folks. I've been doing this a while. If you do these exercises in pairs, and it doesn't matter what the level of the other person is, the mere fact that you're discussing it, that communication forces,” again to pull out a nice buzzword from the education biz, “it forces what's called metacognition.” The fact that you're thinking about what you're thinking and you're forced to communicate about it, it enhances the learning dramatically. And I've seen this. The people who work on their own inevitably learn less and have less high quality solutions to the exercises than the people who pair up. The thing is, I'm not enough of a bully to tell people, “You must pair.” So, I'll say to them, “I really strongly encourage you to do this. I think you'll have better results.” And then what happens, maybe a third of the people will pair up and they clearly know it better at the end.

**SAM:&nbsp;** Hmm.

**CHUCK:&nbsp;** So, we've talked about pairing up. We've talked about using examples and helping people modify their mental model. Can you walk us through what a day in the life of sitting in one of Reuven's training sessions looks like so we can follow along as far as how much… so I lecture on it for 10 minutes and then I make them do an exercise for 30 minutes. Or, how do you set that up so that there's this flow and follow through, through a day's worth of instruction?

**REUVEN:&nbsp;** Yeah. So, I do use slides but less and less. So, what I'll do is I'll send then the PDFs of the slides so they can follow along. And if I'm really attentive I'll say, “Okay, we're now on slide deck 3 or slide deck 4.” And over time I've split them up into smaller and smaller pieces, both so that I can see where the wholes are and so they can have a better handle on it. Because to send them a slide deck of 500 slides is ridiculous. But to say, “We're now on the functional programming slide deck. We're on slide number 20,” that's helpful for them. So, I'll say where we are and then I'll go through a whole… basically I will describe things while doing live coding. There's almost nothing that I'll just describe without live coding. And we'll do that for somewhere between half an hour and 45 minutes probably. And I really try to encourage questions as much as possible. That's a very cultural thing. So in Israel, I don't have to encourage questions. People will attack me with questions.

[Chuckles]

**REUVEN:&nbsp;** Or just attack me. That really comes with the territory. By contrast when I teach in China I really have to… it's like pulling teeth sometimes. I really need to go all out to encourage them to ask me questions because culturally that's just not done. And then after going through this and having some interactions and a lot of demos I'll say, “Okay, here's an exercise.” And the exercise will typically by 15 to 40 minutes long depending on where we are in the course. So, I usually have two or three big exercises during a course which are like 45 minutes long, an hour long. And the rest are probably close to 20, 25 minutes is probably a good guess. And during that time I invite them to ask me if they need me to come up to them and help. And that's a very personal thing. Some people are all over me and asking me for help from the get go. And some of them will just struggle through and not ask me for help at all. And it's hard for me to force myself upon them. And so, we'll just sort of lather, rinse, repeat. So, we'll do that a bunch of times.

And typically a training day is eight hours long, plus/minus. Usually it's a little less than that because I see the glazy eye look in my [chuckles] participants’ eyes. And there's a limit as to how much I can torture people. I do try to push lunch. So, we take an hour-long break for lunch. I try to push that as late as possible not just because I'm cruel and nasty but because I know that after lunch everyone gets sleepy. Indeed it's not unusual that someone sleep after lunch in my classes. I don't take it personally anymore. And I want them to be as alert as possible. So, we'll go from I don't know, 9:30 to 1. And then 1 to 2 we'll take a break for lunch. And then 2 to 4:30, 5-ish.

**CORALINE:** With the exercises that you have them do, do you go around and evaluate those exercises? Do they submit them somewhere? Or are they left to decide if they have done it satisfactorily or not?

**REUVEN:&nbsp;** Oh right. That's an important part of it. Sorry. So, after they do the exercise I go over it. That is to say, I've always thought it would be a smart, fun thing to do to have them submit them or demonstrate them to other people. I just feel like I'm always under such a time crunch that I don't. But it is a very important part of the class as far as I'm concerned that I then go and solve the exercise in front of them. And I purposely do it with mistakes. So, I go through and I say, “Okay, folks. You might have noticed there's a bug or two here. Let's run it. Let's see what the problem is. Oh, this is because such and such was wrong.” And so, even a simple exercise, the solution might take 10 or 15 minutes to go over because I'm pointing out either where they might have problems.

And inevitably if I hit a raw nerve or I hit something that people did all the time you'll hear from the people, “Oh, yeah.” [Chuckles] which is always satisfying like, “Aha, I read your mind.” And then I'll go over the solution. And then at the end of the day, every day I send them a zip file with all the solutions that I came up with plus all the slides. Because almost certainly I will have updated the slides during the day, thanks to bugs that I found in them or expansions that I wanted to do.

**CORALINE:&nbsp;** A couple of interesting things in there, Reuven. Making mistakes on purpose, that's something I do when I am pairing with early career developers because I want them to see that omnipotence is not something that comes with seniority. That I still have to google stuff. I make mistakes. I don't think about things correctly sometimes. So, at least once I day I'm making a mistake. [Laughs] No, I make mistakes all the time. And I think being honest about that sort of thing is really important for setting people's expectations for themselves in a realistic manner. But one of the other things that came to mind when you were describing that process is with code there's always more than one way to do it. So, are you letting them know this is Reuven's solution but there are other solutions that are equally valid?

**REUVEN:&nbsp;** Yeah. Yeah, absolutely. I say, “This is a solution.” Sometimes I'll even solve it twice or three times so that they can see the differences then we can evaluate them. So, in my intro Python class for instance I used to do an address book program. I do this in my Ruby classes also. I basically steal exercises from one language when I teach one and use them in the other because actually it's really easy to do that in most cases.

So, I have this address book program. And I used to say to them, “I want you to choose whether to do it using a list of lists or a list of dictionaries,” which in the Ruby world would be an array of arrays or array of hashes. And I realized that was a mistake. And now what I have them do is I have them solve it each way because I want them to see the trade-offs and I want them to get more fluency with each of the data structures and the complexities associated with them. And I found that that has worked really, really well. So, I no longer have to solve it twice for them, they solve it once and we solve it twice. Instead they solve it twice and I can go over it and then find some of the pitfalls as well in that way.

**SAM:&nbsp;** Oh, that's nice because that way, maybe if they get to choose they flip a coin, they get lucky and they find the one that doesn't work as well. And I deliberately say that that's when they get lucky. Because then they learn how it…

**REUVEN:&nbsp;** [Laughs]

**SAM:&nbsp;** How that thing falls down, right? So, this way you guarantee that they're going to experience that, right?

**REUVEN:&nbsp;** Right, right, absolutely.

**SAM:&nbsp;** Nice. I was also going to say that I like the idea of making mistakes on purpose because it lets you demonstrate what to do with those weird error messages that come up. Because that's often a very off-putting thing for newcomers, right?

**REUVEN:&nbsp;** [Inaudible]

**CORALINE:&nbsp;** I think we could do an entire class on reading stack traces.

**SAM:&nbsp;** Oh my, yes.

**REUVEN:&nbsp;** You know, that's the thing. I try to point out [inaudible] just today. Today I taught a Git class. And I go over the last few days. I've been showing the people who participated in it that Git will tell you what to do. You just have to learn how to read the messages. Git status is your best friend. Okay, maybe I'm weird for having that for a best friend. But fine. But the thing is, you have to pay attention to status messages. You have to pay attention to error messages because inevitably it makes sense in some way, somehow. And that's part of again learning a language and absorbing its idiosyncrasies. It's figuring out, what does this message mean? What is it trying to tell me? And sometimes when the message is totally goofy, to understand why it's goofy or why it seems that way. What part of the language is acting in a strange way?

**SAM:&nbsp;** Right. That's where the mental model, especially of Git which you mentioned, comes in really handy. Like I struggled for a yeah and a half, two years, with Git before it finally clicked and I understood why it was telling me all those strange things. So…

**REUVEN:&nbsp;** [Laughs]

**SAM:&nbsp;** You can get people over that in three days, right?

**REUVEN:&nbsp;** Well, [inaudible] right. So, the class started in one day. The Git class started as a one-day class. At the end of eight very, very long hours people were like collapsing. So, I said, “Okay, I think we need to make this a two-day class.” And the two-day class actually works pretty well. And this one particular client insisted I throw in some extra stuff. So then, it became a three-day class. But then for all sorts of corporate weirdness reasons, two people actually signed up. So, I took three days to teach two people Git. You can imagine we finished after lunch today and that was with a lot of breaks. [Laughs]

**SAM:&nbsp;** Right, yeah.

**CHUCK:&nbsp;** So, I just want to point out as we've talked about a lot of this stuff, there's no reason why you as a person in a company couldn't do this for the company you work for as well. And a lot of this stuff applies there. So, you can gain expertise in some area that the company needs people trained in. and then you can go ahead and take the steps to do this for your own company and help your coworkers learn this stuff by putting on a workshop or doing a brown bag of lunch or something like that. And all of the techniques that Reuven has shared so far will help you get this stuff across so that you can be more effective.

**SAM:&nbsp;** You can also use that as a springboard for a public speaking career if that's what you're interested in. I started out with my think like a git website. It started as a lunch and learn presentation for 10 people that I worked with. And then it turned into an impromptu conference talk. And then from there I was like, “Wait. Maybe I can actually do this.” And then I started actually submitting talks. So, that's another path you can take even if you aren't necessarily interested in training per se.

**REUVEN:&nbsp;** Right. And companies, they're always interested in people who can communicate well and communicate tough technical ideas clearly. Because it seems to be a rare skill. I think it's something that obviously people have it in different proportions. But it's something that you can work on. And so, if you can communicate these ideas clearly, you'll be in demand in your company and other companies. And you can then get sent to all sorts of conferences or just apply as Sam said.

**CHUCK:&nbsp;** Definitely. So, I kind of want to move it a little bit into how do you get from the person who's doing this kind of training in your own company or somebody, even if you feel a little bit new, how do you go from, “I know this stuff,” to, “I'm going to teach this stuff to other people?” and get into actually doing training at companies that are not the company you work for?

**REUVEN:&nbsp;** So, well the first thing is right. To start in your own company or maybe going to meetups, start with something small and short where you also are guaranteed to get [inaudible] a loving but constructive criticism. And so, people will attack you but attack you nicely and say, “Hey, what about this and this and this?” and they'll find holes both in your style and in what you're doing. And it will allow you to realize where you need to flesh things out. Where do you need a longer explanation? Where do you need a different analogy? I'm big on stories. So, if I find a story that… and it doesn't have to do with programming necessarily. A good story that will help people to understand what's going on, then I'm always on the lookout for those. Because I find that really does a great job of bridging the gap between the technical material and people's thought process. So, if you try it once, twice, and so forth, you'll see where the issues are.

And then you can start trying to submit it. And there are all sorts of… especially in the US, for crying out loud. There are all these regional conferences that I'm sure if you have an interesting topic, and by the way if it's interesting to you it is probably interesting to many other people too. Interesting topic doesn't need to mean, “Oh by the way, I've created a new operating system.” It can be something on a slightly smaller scale or a much smaller scale. And so, try it. Even if you have experience it can take some time to put together a new course and to just get the right feel for it. So, I just started doing courses in data science and machine learning. And the second time was better than the first. And the first time was better than my practices at home. And over time you'll just practice. And I say it takes five to 10 times for one of my classes to truly be good.

**SAM:&nbsp;** So, does that make…

**CHUCK:&nbsp;** Yeah, I've found that as well with my training or with talks or any of that. The more time that I spend practicing or giving it in front of people or doing it in front of the users group, the better it gets. And that makes total sense to me, just from my own experience.

**SAM:&nbsp;** Does that make you feel guilty about charging money for the first four?

**REUVEN:&nbsp;** [Laughs] If you're one of my clients, the answer is no.

[Laughter]

**CHUCK:&nbsp;** Nice.

**REUVEN:&nbsp;** So, look I work really hard even before the first time that I give a course to make sure it will at least be good or I think very good. My family knows that for the month and a half, two months before I gave this data science course, I was just crazed reading everything I could, trying everything I could. And again, it was good. The scores I got. And that's part of the corporate training deal as well where you'll get a questionnaire at the end or you'll get the results of a questionnaire saying how well you did. That's your score. So, the scores were certainly good. But they weren't amazing. But my clients say, “Okay. This was a good start. Let's make it better for next time.” So, if you have nice clients then they will be understanding.

Again, I still think I gave them good value the first time. I think I gave them better value the second time. But you know what? The first time I taught Ruby, the first time I taught Python, the first time I taught Git, looking back, “Oh my god, what was I thinking?” [Laughs] Right? I didn't give them nearly as good value as I do now. So, it's always going to be a process. It's always going to be improving. And that's just the nature of the beast.

**CHUCK:&nbsp;** Yeah, but…

**SAM:&nbsp;** You were doing the best that you could with what you had. And it was enough that they felt it was worth paying for. And that's really why I brought that up.

**REUVEN:&nbsp;** Right. Right.

**CHUCK:&nbsp;** Yeah. I just want to pile on this. At lot of my clients, I've done training for I think two companies over the last two years. So, not to the extent that Reuven has but I've also done other kinds of consulting with companies. And I get better every time. But the thing is that the companies that are paying me are getting the outcome they want when I work for them. And so, even though yeah, they're not getting as much value as the next client that pays the same amount for the same consulting, they are getting their money's worth. They're getting that value out of it. And that's ultimately what makes me feel good about charging them for it.

**REUVEN:** Absolutely, yeah. It doesn't have to be perfect either in your eyes or in their eyes for it to be worthwhile and to be worth paying for.

**CORALINE:&nbsp;** I'm curious. What is the goal that most of these companies have going in when they're bringing you in as a trainer? Are they trying to get people an introduction to the topic? Are they trying to make them productive in a language for example? Or what's the end goal for them?

**REUVEN:&nbsp;** So, in most cases it's because they have adopted technology and they have developers who don't know the technology or don't know it well enough to work with it. And so, they're looking for a speed boost. They're looking for an accelerant to ensure that their people can get to speed as fast as possible, faster than giving all of them books and videos and having them learn on their own. But sometimes, some companies will set up an open marketplace for courses. And [chuckles] maybe they'll have an open marketplace for courses and so people can sign up for whatever they want. And then it's a combination of what the company needs and just trying to give a nice perk to their employees to keep them around.

**CORALINE:&nbsp;** Like a professional development kind of situation basically.

**REUVEN:&nbsp;** Right, right. Like we want our people to stick around and we want them to be educated and we want them to learn as many technologies as possible. So, we will either give them a budget or give them a number, either a money budget or a day budget or just ask their manager. And so, they can sign up for more or less what they want whether it's relevant to their immediate job or not. And you have some sneaky people [chuckles] who will then say to me about the course, “Oh yeah, the reason I'm taking this course is I'm planning to leave in a month or two and I want to be better on the job market by having such and such under my belt.”

**CORALINE:&nbsp;** Wow.

**REUVEN:&nbsp;** [Laughs] It's not my place really to talk about the morality of that. But it's nice that they fill up my classes. But clearly that's not the reason why these companies are pulling people in. Now, there are some companies also that will bring me in for training when they have new employees who know nothing about the subject and they need to bring them up to speed so they can be effective.

**CORALINE:&nbsp;** So, I had a job a couple of years back where the company was a .NET company. And they made a decision at the executive level to embrace open source. And as part of that they wanted to rewrite everything in Ruby and Rails. So, part of my job…

**REUVEN:&nbsp;** [Inaudible]

**CORALINE:&nbsp;** Was shifting the culture and shifting the technology. And a lot of that involved training a bunch of .NET developers in Ruby. And I had a lot of hostile learners. Have you had a situation where there are people at your training classes who just did not to be there?

**REUVEN:&nbsp;** Well, I have three kids, so I have experience with hostile learners.

[Laughter]

**SAM:&nbsp;** Ba-dum-tss.

**REUVEN:&nbsp;** [Chuckles] That's the level of humor you get in my courses, folks. So, the most extreme example of that was I was, well I guess two extreme examples. One was I was in a similar situation to what you just described. I was brought in to do some consulting at a big company where most of the people have used either PHP or .NET. And they brought me in to train people and accompany them as they move to Rails. And there was incredible venom, not toward me, but for the platform. And the Senior Vice President who had brought me in kept saying to them, “Listen, folks. You're not going to work for us forever. I'm giving you a gift here by teaching a new technology and a new ecosystem. It doesn't matter what it is. This is big and you should appreciate it.” And that went over like a lead balloon. But the other thing is…

**SAM:&nbsp;** [Laughs]

**REUVEN:&nbsp;** [Chuckles] Right? They still hated it.

**SAM:&nbsp;** You'll eat your vegetables and like it. [Chuckles]

**REUVEN:&nbsp;** The other thing is I had a guy in my intro to Python class, probably about a year or so ago where I open my mouth and I more or less said, “Hi. I'm Reuven. Welcome to intro to Python.” And the guy said, “What is this crap? What kind of language is this?” I was like, “What?” [Chuckles] And he said basically like, “This is a ridiculous kind of language. And it doesn't mean anything. And it's not worth anything.” Anyway, it was great bring able to use him as a foil the entire time for my jokes and so forth. By the end of the course he was like, “Wow, this is really cool. I shouldn't have thought about it that way before.” So, I felt somewhat vindicated.

**CHUCK:&nbsp;** So, my next question is you've done training for some rather large companies. I don't know if you want to say on the air which ones.

**REUVEN:&nbsp;** Oh sure, sure. I'm happy to show off. Or may it clear that I'm a corporate slave.

**CHUCK:&nbsp;** Yeah, I know you've done some for Cisco for example. I'm not sure what other companies you have done it for. But how do you break into that market? Let's say that we have somebody on this show or somebody listening to this show that is thinking, “You know, I've been doing Ruby on Rails for a long time,” or, “I've been dealing with PostgreSQL for a long time. And I know enough to go in and do some of this training. So, if somebody needs help with geolocation in PostgreSQL or something like that, I could go in and I could do that workshop.” How do they get in front of these companies so that those companies will hire them and say, “Come and teach our people how awesome this stuff is and how to do it so that we can make a ton more money”?

**REUVEN:&nbsp;** So, if your client in the training biz is not the student in your class, clearly you want them to learn. Clearly you want them to enjoy. You want them to want to come back for additional courses and you want them to give you a high score. But at the end of the day the person who both hires and decides to keep you on is the training manager. And so, that's your initial point of contact. That's the person you have to convince to hand over some of their budget and their time to you. And so, I tend to not contact these companies so much as they contact me because I've got a lot of stuff online and I speak at conferences. So, what will typically happen is I'll speak at a conference and someone will be there and say, “Oh, this might be an interesting guy to have come train us.” And of course, I mentioned when I'm speaking at the conference that I do training. Don't assume that people will figure this out because they won't. And so, some engineer will go to their boss or the training manager and say, “Hey, I think we should bring this person in for training.” So, that's fantastic when you can do it.

The other way to do it though is to call a training manager. And there are a few different strategies for doing that. One is just to call them up and say, “Hey, I understand that you use such and such technology. I offer training in that. Can I talk to you about it? Do you have a need for that?” Another way to do it, and this I attribute to Jonathan Stark on The Freelancers' Show, he suggested basically doing a survey. This is [inaudible] and said that he suggested to his coachees I guess where he says call up 10 of them and say, “I'm interested in getting into this market. And I'm interested in hearing from you what you're interested in, like in Ruby training say. Can you give me 15 minutes of your time to tell me what you're looking for?” And he says most of them will ignore you. And two, three, four of them will actually give you answers. And then you have something that you know what matches up with their needs.

And then today, literally today at lunch another trainer was telling me that he had heard another technique which I thought was brilliant where you call up the company and you do something similar. Like, “Tell me what your needs are.” And you don't try to sell anything at all. And after a few minutes of conversation they'll probably say, “Oh, so what are you selling?” And they will basically then be asking you, “What can you give me?” and you go, “Well, I happen to be offering this sort of course.” But it's definitely a lot of trying from all angles. You want the engineers to be suggesting in their company, “We want training in X. Let's bring in an expert. Oh, we know that person Y is an expert. Bring them in.” And you want them to be funneling it up to the training manager. But it's not bad to contact the training managers and they're always looking for good training. They're always looking for it and they have the budgets to spend. It's just a matter of convincing them that you're the person to spend it on.

**SAM:&nbsp;** So, how do you find those people? I ask as somebody who's never even considered consulting and I'm just curious about how that would work, because I have no idea. [Chuckles]

**REUVEN:&nbsp;** So, I'm actually thinking of doing this a bit. And so, I was actually talking to this other trainer today at lunch who happened to be at the same company where I was and I said to him, “Well, I'll just call up a bunch of training managers.” So, if I call a company they're going to have a directory of some sort. If I call up the operator and say, “Hi, I'd like to speak with your head of training,” presumably there will be such a person. You could also try to use LinkedIn to find such a person. And their job is basically to match up trainers with trainees, and the trainees are in their company. And so, they might very well say, “We're not interested. We don't use that technology,” or, “We have someone teaching that already.” But if you manage to get them to talk for a bit maybe you can find a niche.

So, I know that there's a company where I don't do Python training because there's someone else who's there who's their guy. But they called me a few months ago and said, “Hey, could you give us training in data science?” Because from their perspective that's a wildly different thing, right? But I know it's… training in Python, obviously it's a different use of the language. But yeah, so trying to offer something specific rather than general or generic might give you a leg up also trying to get in there.

**CHUCK:&nbsp;** One thing that you mentioned was from Jonathan, doing that survey. I'm just going to put a link in the show notes for a survey that I put out that's rather similar to what you were talking about. And basically the questions are… it's like three questions. And then it's, “Can I contact you?” The questions are what's the single most important thing that we could cover or answer that would impact your career? This is for DevChat.tv. Then next one is, why would it make a difference in your life to get a good answer or a discussion about the solution to that thing? And then the last one is, how difficult has it been for you to find a good answer to that thing again to date? And the reason that you go there is because again, all these people that you have reach to will give you the ideas that you need.

So, and the responses all just tell you, I've looked through some of them. I've had 165 responses so far. And some of it's getting clients and some of it is JavaScript stuff. I see a lot of testing in here and I see a lot of, how do I get better at what I do? And so, you can turn that into, “Okay, I've got a whole bunch of these people who are having the same problem,” and then from there what you wind up doing is you wind up reaching out to them because you asked them for their contact information. And by getting that information, by understanding where they're at and seeing the ones that are saying this stuff is impossible to find, you can really get that value proposition right where it's impossible to find, well unless you hire me to come do the training for you. And I know that this is going to impact you because you told me why. And so, you get a lot of these answers.

If you want to look at the survey like I said, I'll put a link up so you can go and look at it. You're also welcome to fill it in if you want. But I think this is the kind of survey that Jonathan is pushing toward because it's completely open-ended. And it gives people the opportunity to really tell you what they need.

**REUVEN:&nbsp;** Excellent. Yeah, I've sometimes done that with corporate training clients where they'll say… especially with advanced classes. Because advanced classes, everyone knows what a beginner is. But what does it mean to have an advanced class? No one really can give a straight answer on that. So, what I'll do is I'll send a survey to the participants or potential participants and I'll say, “Here are a bunch of skills. Rate yourself from 1 to 5.” And then even if we call it an advanced class I know that it might not be [chuckles] because of the answers that I got. But we can all just live in our little illusions. They in theirs and me in mine. And then I just can do the class and everyone's happy because what do you know? The people all learn something they hadn't learned before.

**CHUCK:&nbsp;** So, one other thing that I'm wondering about is when you go and you offer training to a company, you said that you talk to them and ask them what things they want to know. But do you also offer them a standard offering? So, I have a course already prepared for introduction to Python or advanced Python or whatever the heck you call it. Do you offer that to them as well? Or do you generally talk to them and find out what they need and then make the appropriate offering based on what you have?

**REUVEN:&nbsp;** So usually, when companies call me I can give them my standard courses. I would say that's 75, 80% of the time. And so, I'll say, “Oh, what you're talking about sounds like an intro to Python course or it sounds like an advanced Python course.” And sometimes they'll say, “Yeah, but we need something specific for this and this and this.” I'll say, “Oh, okay. Well, I happen to have a bunch of modules because I've modularized my slides from before. So, I can swap things in and out as necessary.” So, oh, you want to talk about less about functional programming and more about deep objects? Sure. Let's do that. You want to talk about databases? Sure, let's do that. Where I'm bad at, and this of course indicates that I'm a good software developer I hope is I'm terrible at estimating time. So…

**SAM:&nbsp;** [Laughs]

**REUVEN:&nbsp;** If they say, “Well, how long will it take to do this subject?” I'll be like, “Oh, that will be two hours.” And three hours in I'm like, “Uh-oh. I got that one wrong.” But other than that, it seems to work okay.

**SAM:&nbsp;** I would imagine that the estimate varies by the class as well, right? Some people are going to ask more questions or be further ahead.

**REUVEN:&nbsp;** Yeah.

**CHUCK:&nbsp;** Yeah, but if you're not off by a factor of at least five, then you're not a good programmer.

**SAM:&nbsp;** Nailed it.

**REUVEN:&nbsp;** [Chuckles] So first of all, the same class that I do in Israel in four days I do in China in three days because they ask way fewer questions. And I don't necessarily think that's better educationally. I encourage people to interact and ask questions and so forth. But that's just the nature of the beast, right? That's just what I need to deal with. So, fine. But yeah, sometimes you'll have more and less. And then sometimes I'll realize, “Okay, I've got to speed head on such and such a topic.” But it's also true that from the classes, not only do they give me ideas as to what to teach and how to teach, but I get a sense of why people are coming. And then I can try to upsell their companies on either something more specific or something different.

So, I had a lot of people coming to my intro Python classes who were woefully unprepared. Because it's meant for people who know have to develop software already in another language. So, most then would come in knowing C, C++, Java, .NET, C# and so forth. And then you have the handful of people who had never programmed before or who had done some shell scripting and they were amazingly lost. So, I went to one of my clients and say, “How would you like to have a class in Python for non-programmers?” And I think I was the first person in their training history to suggest a programming class for non-programmers. So, this is like the ultimate upsell because they were like, “Great. Sure. Go for it.”

**SAM:&nbsp;** [Chuckles]

**REUVEN:&nbsp;** And so far, the first time I did it, I put in way too much. It was way too hard, not what I wanted. Second time better. Third time great. So, each time it keeps improving.

**CORALINE:&nbsp;** I'm really curious Reuven. You talked about the cultural differences between the students in Israel versus the students in China. Do you notice the same sort of differences among gender lines?

**REUVEN:&nbsp;** Not so much in China. But I'll tell you first of all in Israel it's sad but true, the number of women in high tech is similar I think to what I've seen to Europe and the US which is much, much lower. It's a clear gender imbalance. And in China that does not exist at all. It's clearly 50/50 or close to it. So that I think is first of all a positive thing, that culturally they're encouraging everyone to go into high tech. But I don't think that there's a difference in terms of the interactions. There may be… if I had to guess I'd say it's probably the females asking more questions. But that's just a gut instinct. I'm not sure if it's necessarily true.

**CORALINE:&nbsp;** I've found the opposite to be true in mixed gender learning situations where women are more hesitant to ask questions because they don't want to appear dumb. But there are cues they give off when they are confused or need an answer to a question. And it's much different in an all-female learning environment as well, because the number of questions that I get goes up exponentially.

**REUVEN:&nbsp;** Yeah, so my girls, I have three kids. Two girls and a boy. My girls are 15 and 13 and they go to a single-sex school. And they clearly get a lot out of that because the girls there are all being told, be aggressive. Ask questions. And do something. And my impression is basically single-sex education is better for girls and worse for boys. So, we're joking about sending my boy there surreptitiously when he gets old enough. Look, I would say in Israel at least the culture is so strong in terms of asking questions and speaking out. It's also true that many of the women in high tech are Russian background, either born there or their parents were born there. And they tend to have a very aggressive questioning culture. So, that might be the reason for that disparity.

**CORALINE:&nbsp;** Those cultural differences are really fascinating to me.

**CHUCK:&nbsp;** Yeah.

**REUVEN:&nbsp;** Yeah, it's been amazing to see.

**CHUCK:&nbsp;** I'll chime in with one of the trainings that I did. There were probably I would say a quarter of the people in the training, I was teaching them how to test Rails, were women. And it was really interesting. I didn't want to single them out but I did want to make sure that they were understanding things. And one of the things that I did while I was there was during the exercises I would deliberately walk to each pair of people programming because I'd have them pair up during their exercises and make sure that they were getting it. And the reason was because like you said, Coraline, I found that the men were much more likely to raise their hand and ask a question. And I don't know how much of that was conscious or subconscious. But by going around and making sure that I talked to each group that was working on the problem I was able to answer any questions and help them get unstuck without having to single anybody out. And…

**CORALINE:&nbsp;** I think it comes down to having empathy as a teacher, honestly.

**CHUCK:&nbsp;** Yeah, yeah.

**REUVEN:&nbsp;** Yeah, it's so important when someone asks a question to take it seriously. They're not asking a question because… they're asking a question because they want to know. They're not asking a question because they're dumb. They're not asking a question because they want to annoy people. And so, yes, realizing this is a good question, this is an important question, taking it seriously and being patient as you answer it is crucial.

**CHUCK:&nbsp;** Yup. But yeah, it's definitely a cultural thing and sometimes it's tricky. So, any other bits of this that we should talk about before we go to picks?

**REUVEN:&nbsp;** I'll just add that people often think that I've got, the work that I do is somehow going to be boring or, “How can you do that same course so many times?” And…

**SAM:&nbsp;** That was my question. [Chuckles]

**REUVEN:&nbsp;** Oh, okay.

**CHUCK:&nbsp;** [Chuckles]

**REUVEN:&nbsp;** And so, first of all I sometimes make the analogy to a one-person play. So, I'm going and I'm playing this character and doing it again and again. And every night I have a different interpretation. But that's a very simplistic sort of way of thinking about it. I really love the look of excitement and joy on people's faces when they get it. Where like, “Wow, I've written this software and I understand how it works and I now am coming out with greater skills.” And especially since I do a lot of training at Cisco so I see people in the cafeteria there all the time. And they're like, “Oh, you know that course that you gave me two weeks ago,” or a month ago, or six months ago, “I was able to solve such and such a problem faster because of what you taught me.” And that just totally makes my week or month or year. That's why I do what I do. And that sort of reaction and response from people makes it all totally worthwhile. The fact that it's also a fun interesting consulting gig where I get to interact with interesting people, get smart questions and then research topics that they ask me for fun, that's just icing on the cake.

**CHUCK:&nbsp;** Awesome. I think generally I agree with you Reuven. The thing that I get out of the training more than anything else is interacting with people and feeling like I'm making a difference. And that's yeah, that's the thing. Answering those questions, feeling like it's contributing.

**REUVEN:&nbsp;** Someone once told me, I guess it was at this get-together for trainers about a year ago, and someone said this really smart sentence which is, “There are only two types of questions you'll get from students. Good questions and excellent questions. And a good question the student does not know the answer. And an excellent question, the teacher doesn't know the answer.” So, I always encourage them, ask me excellent questions. Challenge me. Make me do homework so that I'll have to come back the next day and report back to you.

**CHUCK:&nbsp;** Makes sense. Alright. I'm going to push us into picks mainly because I know that Reuven is about to be interrupted rather loudly. So, we'll let him go ahead and do picks first.

**REUVEN:&nbsp;** Fair enough. So, I've got I guess three picks that I think might be interesting for people. One of which is this really famous well-known computer scientist named Marvin Minsky died a few months ago. And I was fortunate enough to get a class with him when I was an undergrad. And he was just this wild, fascinating person with incredible ideas. So, I've been going back and reading some of his stuff. And his book called the 'Society of Mind' is an amazing way of describing how people's thought processes and minds work and how you can think in terms of education. And it gives a lot of hints as to how you can teach and how you can build up people's ideas in a different way than most people think about and talk about. So, Minsky's 'Society of Mind'. Definitely worth reading. It's a very, very easy read because every chapter is one page long.

The second book or set of books is I go to China a few times a year to teach. I've been taking Chinese. By the way, learning Chinese has affected my training and my teaching profoundly because it really gives me a sense of what is it to learn something that seems totally bizarre and different and yet has its own rules. So, I really empathize a lot more with my programming students as a result. And it's fun to surprise my students in China with my knowledge of some Chinese and my horrible accent. In any event, so there's this guy named Peter Hessler who used to write for the New Yorker. He still writes for The New Yorker and he was their China correspondent. And Peter Hessler's books are just beautifully written, amazing, insightful and great to read, before you go to China or otherwise.

And third thing that I'll do and somewhat self-serving is I am putting together a, I have my book as Chuck mentioned earlier about regular expressions, 'Practice Makes Regexp'. And I'm putting together an introduction email course to regex. So, I'm calling it the 'Regexp Crash Course'. So, RegexpCrashCourse.com and you get extra points if you can pronounce that better than I can. So, if you go there…

**CORALINE:&nbsp;** Reuven are you pronouncing the P in regexp?

**REUVEN:&nbsp;** I am. I am.

**CORALINE:&nbsp;** Wow.

**SAM:&nbsp;** Old school.

**REUVEN:&nbsp;** Because regexp… right, right, because real programming languages do that. [Laughs]

**CHUCK:&nbsp;** [Laughs]

**REUVEN:&nbsp;** Not to turn off [inaudible]. **SAM:&nbsp;** [Inaudible]

**REUVEN:&nbsp;** [Laughs] Anyway, so by the time this hits the airwaves, the podcast waves, that should be ready. And hopefully people can then learn or enhance their understanding of regular expressions through that.

Anyway, those are my picks.

**CHUCK:&nbsp;** Sam, what are your picks?

**SAM:&nbsp;** I've got two today. One of them is trying rspec-given. I recently started working on a small greenfield Rails app. And so, I gave myself permission as part of that project to try out a couple of new tools and techniques. And one of those tools that I chose was rspec-given which was written by the late Jim Weirich and is now maintained by I believe Justin Searls, at least based on the commit history. Anyway, rspec-given has a very opinionated perspective on testing. And I tried it out on this project for almost exactly three weeks. And I wound up tearing it out and going back to regular RSpec. But I learned a lot in the process. It was a really interesting and educational three weeks. And I recommend giving it a look. Even if you don't wind up using it, it will probably teach you something new about testing.

My other pick is a grab bag. It's the conference talks of Katrina Owen. I took a couple of hours out of my work day last week as we were recording this last week, to watch a couple of talks from RailsConf. And I was reminded again how incredibly worthwhile it is to listen to whatever Katrina has to say. Katrina is the queen of overthinking things. And we love her for it. Her talk, 'Therapeutic Refactoring' just totally blew my mind about three years ago. And her other talks just keep getting better and better. And I'll just put a link in the show notes to her Confreaks page.

And that's it for my picks.

**CORALINE:&nbsp;** I saw her speak at RailsConf last week Sam and she's got another amazing talk. So, look forward to that.

**SAM:&nbsp;** That's the one I saw.

**CHUCK:** Yeah, and she, for those that don't know, she used to be on Ruby Rogues on a regular basis. And the last time we did a Ruby Rogues retreat which was back when we had Avdi, Josh, and James, and David, and Katrina and I on the show, it was fun to just hang out with her for an extra couple of days along with the other Rogues. And she is just an amazing person. I think that comes through in the talks quite a bit. But I don't think you really get that until you actually get to spend some time with somebody in a little bit more casual and social setting like the one that we had when we all rented a place together and stayed for a couple of days.

**CORALINE:&nbsp;** I'm intrigued. We need to do that soon.

**CHUCK:&nbsp;** We totally need to do that soon.

**SAM:&nbsp;** I'm in.

**CHUCK:&nbsp;** Coraline, what are your picks?

**CORALINE:&nbsp;** I have a couple of picks today. I should warn you that next week when the videos start emerging hopefully next week I'll have a lot of picks from RailsConf. It was an excellent conference. But I was recently talking to the maintainer of hoodiehq, a rather large open source project. And he told me about a project developed by Finn Pauls in Berlin. It's a simple Node application you install via npm. It's called github-shoutouts. For now it only works for organizations.

But the way it works is you create a GitHub token and you export it. Then you run github-shoutouts with your organization name. And for every person who has contributed in some way to that organization's repositories it generates a shout-out. So for example, Charlotte worked on seven repositories. All time total 62 merged PRs. She landed this PR, merged three pull requests, reviewed three pull requests, and commented eleven times. So, I'm not a fan of the GitHub activity graph. It's something that I will be working on changing in my capacity at GitHub now. I'd like to see other kinds of non-[code] contributions to open source projects celebrated and lauded as much as code contributions. And I think github-shoutouts is a great step in that direction. So, there's that.

Also I am on the board of an organization called Ruby Together. And I'm amazed at how few people know about Ruby Together. Ruby Together is a non-profit that funds critical infrastructure work in Ruby, like RubyGems, like Bundler. They basically take sponsorships either from individuals or companies. And they use that to pay the salaries of part-time developers to work on critical Ruby infrastructure. There is an individual participator level that you can sign up for. And if your company is dependent on Ruby, please talk to them about supporting the things that keep the Ruby ecosystem alive and kicking. So, Ruby Together is my second pick.

**CHUCK:** Yeah, and just to put a shout-out in, Ruby Together we did an episode on. Looks like Sam found the link. So yeah, go check that out as well.

I've got a couple of picks. I'm really sorry for the smoke alarm tripping. I didn't realize that it was an issue until this morning. And then I replaced it with I think another dead battery. So, I'm probably going to run out before Freelancers' Show and get a new battery. Because I don't think we have any more here.

But anyway, real quick. I'm going to do a pick for Ruby Remote Conf which is going to be held June… oh, now I don't have the date in front of me. It's at the end of June. I think it's the 22<sup>nd</sup> through the 24<sup>th</sup>. And you can go find the details at RubyRemoteConf.com. But we have confirmed speakers, some of whom you've probably heard of. Sarah Mei, Phil Spitler, Justin Collins, Marcus Blankenship, all of whom have been on the show. Dan Schanler, I'm not sure if he's been or, or Ryan Francis. And we're working on getting a few more folks. We had some confirmations from folks. We had to postpone it a couple of months just because of some stuff that I had going on and I'm getting a little bit better at planning these. So, we're working on getting the other folks who said that they could speak to confirm. And I'm talking to a few other folks who I know you want to hear from. So, you can go sign up at RubyRemoteConf.com. Knowing that this comes out next week you can still get the early bird price which is a hundred dollars for a ticket. After next week, it will go up to $200 per ticket. So, I recommend you get it there. If you use the code RubyRogues, all one word, that will get you another 20% off. So anyway, I'm going to just put that out there.

One other pick that I have and I just got this for my wife. She doesn't know yet. She was complaining about the fitness tracker that she had. It's just not working for her. It's not tracking as well as she wants it to so I just got her a FitBit, the FitBit One which is super cool. I love FitBit stuff anyway. So, I'm going to go ahead and pick the FitBit One.

And I think that's it for picks. So, we'll go ahead and wrap this up. Reuven, if people want to find out what you're up to or buy your books or whatever, what's the best place to go do that?

**REUVEN:&nbsp;** So, if they go to my main website at lerner.co.il, that's L-E-R-N-E-R dot C-O dot I-L that has links to books, blog, webinars, all that other stuff. I announce my webinars on my blog and on my newsletter. I also do a site called DailyTechVideo.com which is strangely enough a new video about technology every day. Although it's a little bit on hiatus now because I'm finishing up the regular expression book. And I welcome suggestions for new videos. Anyway, I look forward to hearing from people from this podcast. I've been listening for a long time and it's super exciting for me to be on it.

**CHUCK:&nbsp;** Alright. Well, we'll go ahead and wrap this up. Thanks for coming, Reuven. And we'll catch you all next week.

**_[Bandwidth for this segment is provided by CacheFly, the world's fastest CDN. Deliver your content fast with CacheFly. Visit C-A-C-H-E-F-L-Y dot com to learn more.]_**

**_[Would you like to join a conversation with the Rogues and their guests? Want to support the show? We have a forum that allows you to join the conversation and support the show at the same time. You can sign up at RubyRogues.com/Parley.]_**


