+++
date = 2024-06-21T12:42:08Z
description = ""
draft = false
slug = "doing-developer-hiring-right-part-1"
title = "Doing Developer Hiring Right - Part 1"

+++


Hiring the right people is one of the most important decisions you make at an early stage startup. Here is how we did it at Merchstack

When I started at Merchstack one of the first documents I wrote was “How We Hire”. At a small company each hire is a critical decision, and one bad decision can knock you off course. How we hire would also set the tone for how we treat employees, and also how we see our relationship with employees. Were we actually working together in the best interests of everyone, or just extracting the most value possible for the least amount of money?

 * We have a 6 week SLA for each candidate. They are either hired or moved out of the process within those 6 weeks and notified immediately via email. No candidate should go more than 2 weeks without hearing from us, and everybody hears from us if they submitted a resume. If we can’t meet this SLA than we need to halt the process and review
 * We minimize the number of steps in the process so that the time commitment we ask each candidate to make is reasonable
 * Our interview process should be a reasonable discussion between peers, not a hazing process where the interviewer shows how smart they are
 * If we can’t find the right person, we don’t hire. We step back and reevaluate our approach and the position
 * We proactively hire for diversity. Diversity of thought comes from diversity of team


Our Hiring Pipeline

Building this pipeline is a compromise between getting the most information about a candidate and being reasonable about your time constraints for both the candidate and the hiring team, who often have a full set of other duties. This pipeline worked pretty well for us as a pretty small company building their initial dev team. If we were larger and had an established team we might add another stage for a team interview or a leadership team interview for more senior positions.

Step 1: Job Posting Because our job was remote on a distributed team we focused on boards for remote workers. I feel like this helped minimize the resume spam we got and found people who were looking specifically for remote positions. Our link from these sites went to a form built in Airtable that had a few qualifying questions including uploading their resume, years of experience with NodeJS, etc and built out an Airtable with each candidate and their current status set to “submitted”.

Step 2: Resume screening: Both our CEO and I would go through each resume and give a thumbs up or down without seeing the other persons vote. Resume screening is by far the most difficult task because honestly, so many resumes are awful and the way people write on resume is sometimes intentionally opaque. It is often difficult to really ascertain what they did at any particular job.

Candidates who got two thumbs up moved to the next stage. We also had a field here called “key candidate” who would get top priority for scheduling and an “express lane” route through the process because they seemed exceptionally well qualified. This paid off well a couple of times.

Step 3: Initial Screen This would be a short, 15–20 minute casual chat where I would explain the role, describe the company and what it was about etc, and try to get a feel for the candidates approach and experience. The things I was looking for were:

 * Did they show up?
 * Did they show up on time and prepared?
 * English proficiency (as we hire mostly from SouthEast Asia this was important)
 * Their general demeanor Honestly the number of candidates I rejected during this phase was pretty small. I think my 3 or 4 people I reject because they were either completely uninterested or openly hostile during this initial call. It did help me identify some “key candidates” at this stage as well. (hint: good developers often have terrible resumes)

Step 4: Code Screen

We need some way of screening people out who were just completely unqualified because, honestly a lot of people either overestimate their own abilities, or they are outright lying. We chose a coding assessment platform and built custom assessments for each role.

We tried to make sure that the assessment was able to be completed by someone who knew what they were doing in 1 hour. The tough part about these is that people who completely failed, it was easy to just reject. And there was a lot, probably only about a third of candidates completed what I thought was a pretty easy assessment. Or they just never tried.

People who had sort of middling or good scores, you really needed to dig into their code and look at their answers. Some people wrote solutions that technically “worked” but the code was tangled and impossible to read. You could not just assume that because they got really high scores that they were more technically talented. But generally I think this stage did it’s job pretty well, and did not take hours of my time wasted on people who were clearly not qualified.

Step 5: Pair Programming Exercise/Story Time Interview

This was the real crucial part and the next to last stage. I created an exercise based on a problem I had worked on in the past for Reaction Commerce where the developer who worked on it had some up with a pretty elegant solution. It was a real world problem but it had a pretty narrow focus so it was something I thought we could work through in an hour.

The key parts here are twofold:

 1. Understand the persons thinking process and ability to both understand the problem and communicate their solution to it.
 2. Their ability to turn that solution into working code.

This was the most illuminating stage in terms of technical skill and communication skill. Some people struggled to understand the problem, some people struggled to articulate their answer. Rarely people struggled people to turn their answer into code. But was the code any good? Again some people produced messy, repetitive, difficult-to-read code that might have worked but would have been a horror to maintain.

People who shined in this pair programming interview always turned out to be great coders.

The other part of this same interview was the “Story Time” questions. Some examples of these are:

 * There is a bug in production. What are your steps to try and ascertain the cause?
 * Customers are reporting that a particular endpoint is slow. What steps do you take to figure out why?
 * Another developer made comments on your PR calling your solution “stupid”. How do you deal with that?

These were more about trying to understand how they would be at the non-coding parts of the job. What sort of person were they? Arrogant and confrontational? Timid?

One of my favorites that I tended to save for last was: “There is a bug in production that is causing the entire site to crash. You understand the problem and think you have a fix. However you boss is out of town and you can’t reach him and he has left explicit instructions to not push anything to production while he is gone. What do you?”

Of course the only wrong answers to this are immediately say “push a fix” or “don’t do anything” without giving it any thought. There are so many courses of action here: Try and seek out your bosses boss. Get advice or consensus from more senior developers. Does your fix have an easy rollback plan, etc etc.

Step 5: The CEO interview

This was obviously the only part of the interview process that I was not involved in. This was the final “vibe check”, and was more used to choose between two equally qualified candidates.

Step 6: Make an Offer

In the next part, I will talk a bit more about the tools we used to try and keep costs low while also excelling at managing the process.