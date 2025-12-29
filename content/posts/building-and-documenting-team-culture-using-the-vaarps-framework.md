+++
date = 2024-11-14T04:48:42Z
description = ""
draft = false
image = "__GHOST_URL__/content/images/2024/11/vaarps.png"
slug = "building-and-documenting-team-culture-using-the-vaarps-framework"
title = "Building and Documenting Team Culture using the VAARPS Framework"

+++


Culture makes or breaks engineering teams. Period. More than process, tools, or talent, culture determines whether a team will excel or implode. Yet most "culture initiatives" amount to meaningless platitudes that teams promptly ignore.

Here's the thing: culture will form whether you shape it or not. The choice is between deliberately crafting it or letting it grow like weeds. Most teams end up with something like this:

“At Synergistic Solutions International, we strive to leverage cutting-edge innovation to deliver best-in-class, customer-centric solutions while empowering stakeholder value through dynamic paradigm shifts in our quest for excellence.”

No matter how invested you are in Synergistic Solutions International's future, your reaction will likely be, “Hmm, okay.” This statement is meaningless because it doesn’t tell you how to behave to fulfill this mission statement other than that you should “leverage cutting-edge innovation.”, whatever that means.

For a long time, I have built “Values” documents with my team, and honestly, the reaction I often get is collective shrug.

Honestly, my main influence on wanting to put these together in the first place was The Zen of Python. If you are not familiar with it, you can go into a Python REPL and type “import this,” and you will get this series of zen-like statements like “Flat is Better than Nested” and “In the face of ambiguity, refuse the temptation to guess.” (my personal favorite)

I like that this is a set of values that every Python programmer should adhere to. It starts with things so obvious that it’s a little confusing and gradually moves towards things that might be controversial if such controversy hadn’t already been addressed here. If we have an argument about how some data should be laid out, I can point out that the Zen of Python says, “Flat is better than Nested,” and that’s sort of that.

This is exactly what I was trying to achieve with team values statements—principles that are clear enough to reference in day-to-day decisions ("flat is better than nested") but flexible enough to guide behavior without being overly prescriptive. Most importantly, they become part of the team's working vocabulary, something you can actually point to when making decisions. Unfortunately, most value statements I created were read once and never referenced again, unlike the Zen of Python, which developers actively use to guide their choices.

So how do we create values that actually matter? Values that people reference instead of ignore? Values that shape decisions instead of collecting dust?

Let's cut through the fluff and break down what culture actually is. It's not just values written on a wall - it's how those values translate into:

 * Behaviors (which I call Actions and Anti-Patterns for things you should and should not do)
 * Rituals
 * Power Dynamics
 * Symbols and Success Metrics

Sounds academic? It's not. These elements shape everything we do, usually without us even noticing. But in engineering teams, we can't afford to let culture develop by accident. When someone says, "We have a culture of collaboration," that should mean something specific. Are we talking about pair programming? Code reviews? Knowledge sharing? Let's make it concrete.

So, let’s walk through something using a couple of examples. Let’s start with this, which is something from the values statement from my last company:


Collaboration

Value Statement:

 * When you need help, you seek it
 * When you can help, you offer it
 * No one is ever in this alone
 * We succeed or fail as a team

Nice words. Completely useless. If I told you to "embody collaboration" today, would you have any idea what to actually do differently? So that takes us to the next steps of the VAARPS framework; we have our Values, and now let’s define the Behaviors. Let’s start with the Actions, things we should start DOING if we are not already. So for the collaboration values, we might put something like the following:

Actions:

 * Participating in code reviews within 24 hours
 * Joining pair programming sessions when asked
 * Blocking time for mentoring sessions
 * Sharing meeting notes in designated channels
 * Creating documentation when you discover something new (even just a quick Loom)
 * Asking for help when you get stuck

This isn't a complete list, but it makes things concrete.

Now we're getting somewhere. To align with these values, you need to do these things. (if you don’t agree with these particular things, that’s fine; you and your team should build them together)

Those are things you should do, now for some things you should not do:

Anti-patterns:

 * Working in isolation for extended periods
 * Hoarding knowledge that could benefit others
 * Declining reasonable requests for help without explanation

I like these because often, what we should not do is more important than what we should do, and the latter will often be obvious. For example, “Working in isolation for extended periods” seems to make more sense to junior developers than the affirmative “Asking for help when you get stuck,” which feels like a sign of weakness or ignorance.

So far, we have mostly focused on individual actions. Rituals are where we begin to embody this as a group. An example here for the collaboration values:

Rituals:

 * Weekly pair programming rotations
 * Regular knowledge-sharing sessions
 * "Open Office Hours" where seniors block time for questions
 * Cross-team code review days
 * Regular mob programming sessions for complex problems

So now we have established some more collective and concrete things so everyone can see and be aware of what is happening. A new employee coming in will see these as examples of our culture of collaboration without ever reading this document. Hopefully, this idea will begin to weave itself into the culture.

Culture dies when leadership says one thing but rewards another. Power Dynamics make or break your cultural aspirations:

Power Dynamics:

 * Technical decisions are made through consensus rather than authority
 * Recognition and influence earned through helping others
 * Senior engineers are measured partly by team enablement and success
 * Leadership is shown through mentorship rather than direction

There is an element of putting our money where our mouth is here. Something like “Senior engineers are measured partly by team enablement” means that we need to build that into our performance evaluations and ensure that we actually reward individuals for contributing to the collective rather than just for what we personally produce.

So that brings us to the last letter in our acronyms, S for Symbols and Success Metrics. Symbols are the outward, non-behavior representations of these values, while Success Metrics are the way that we will measure if we are actually living our values. While measurement is important, we have to be careful not to reduce culture to just numbers. Some aspects can be measured directly; others might just be trends we observe. The goal is to have enough measurement to know we're on track, without turning values into mere metrics to be gamed.

Symbols:

 * Shared team calendar showing availability for pairing
 * Public kudos channel for helping others
 * Collaboration metrics in team dashboards
 * Shared documentation spaces
 * Team chat channels organized around knowledge-sharing

Success Metrics:

 * Direct measures:
   * PR review response times (target: 80% within 24 hours)
   * Number of pairing sessions per sprint
 * Behavioral indicators:
   * % of complex problems solved collaboratively
   * Knowledge-sharing session participation
 * Feedback measures:
   * Team survey results about collaboration support
   * New team member time to full participation

Some metrics give you hard numbers. Others reveal patterns. Both matter, but don't fall into the trap of only valuing what you can count. Some might be a little more vague, like “% of complex problems solved collaboratively,” which might just be an observed trend toward collaboratively solving problems. The trick here is not to get too bogged down in trying to put a ton of numbers around it because culture should generally be something you do without thinking. Otherwise, they are just rules.

So there is one other element of culture that I have intentionally left out of the Framework acronym because you will not have it to start, and that is:

Collective Stories & Language. These things evolve over time and emerge from the experiences of the people who build/create the culture every day with their behavior. Some examples are:

 * "War stories" of significant incidents and how they were handled
 * Case studies of major successes/failures
 * Common terminology glossary
 * Team inside jokes or references
 * Origin stories of why certain decisions were made

This is something that you can document later on and add to the document, but you are just not going to have them on day one, so you can’t “Build” the document with it.

So to hopefully make this easier to understand, here is another fully built-out example:


Quality

Value Statement:

 * We value simplicity over trying to solve every problem preemptively
 * Nothing is complete until it has tests and documentation
 * We favor readability over terseness/cleverness

Actions:

 * Including test coverage with all pull requests
 * Documenting architecture decisions in ADRs
 * Reviewing code for performance implications
 * Tracking and regularly addressing technical debt
 * Updating documentation alongside code changes

Anti-patterns:

 * Merging code without tests
 * Adding features without documentation
 * Implementing overly complex solutions without clear benefits

Rituals:

 * Regular code quality reviews
 * Technical debt review sessions
 * Architecture Working Group
 * Performance testing ceremonies
 * Documentation sprints
 * Architecture review meetings

Power Dynamics:

 * Authority to block merges over quality concerns
 * Empowerment to spend time on refactoring
 * Quality metrics influence technical leadership
 * Shared ownership of quality standards

Symbols:

 * Quality dashboards
 * Test coverage reports
 * Performance monitoring tools
 * Architecture decision record templates
 * Code quality badges in repositories

Success Metrics:

 * Direct measures:
   * Test coverage for new code (target: agreed team threshold)
   * Architecture Decision Records completed for major changes
   * Time from feature completion to documentation update
 * Process indicators:
   * Ratio of planned refactoring work to feature work
   * % of PRs requiring multiple revision rounds (lower is better)
   * Technical debt items addressed vs. new ones identified
 * Outcome measures:
   * Production incidents due to missing tests or docs
   * Customer-reported bugs in new features
   * Team satisfaction with codebase maintainability (surveys)


How to keep this a living document

Let's be honest - even the best culture document can become shelfware. Here's how to keep it alive and breathing:


Revisit the Document Regularly

I think it’s good to revisit the document fairly regularly, especially after you first create it, to determine whether it fits well with your goals. At first, maybe once a quarter, and once you feel that it’s fairly well solidified, maybe just once or twice a year.


Update the document with your learnings

It’s pretty unlikely that you created the perfect culture document the first time. So as you learn, make sure that what you learn is part of the document. If a necessary change comes out of a retrospective, see where that change aligns with values and document that Action or Anti-pattern. This keeps your document aligned and the team accountable for putting the findings into practice.


Tie values alignment into your performance reviews and 1-on-1s

If your values document is good, keeping aligned with these values should ultimately lead to team and individual success. So perhaps, as part of quarterly reviews on the Developer Roadmap process, you can revisit the values and evaluate how each developer is keeping with these values and possibly identify areas to improve. The success metrics for each value are a good starting point, but we shouldn’t overly weight them here to avoid this becoming a numbers game.


Conclusion

As engineers, we like to have things that are concrete and actionable. I feel like the VAARPS framework allows people to work through “creating the culture” with their team in a methodical way where, hopefully, something meaningful and useful comes out of it. If you use this framework, please drop me a line and let me know how it works for you.