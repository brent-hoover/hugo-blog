+++
date = 2024-10-31T11:34:46Z
description = ""
draft = false
image = "__GHOST_URL__/content/images/2024/10/debt.jpg"
slug = "handling-technical-debt-in-small-teams"
title = "Handling Technical Debt in Small Teams"

+++


What is Technical Debt

In the context of a startup, I would define technical debt as:

Technical Debt is some aspect of the system that prevents either the system or developers from delivering value to customers in a timely manner


Types of technical debt:

 1. Developer Experience: These are things that make developing the application more difficult or more time-consuming. Their effects on customers are once-removed: Customers are not directly affected but developers are slowed down and so features or fixes may take longer. An example of this may be that the build system is too slow and takes 15-30 seconds to recompile after every change
 2. Performance debt: These are items that make the system slow but otherwise don’t affect the features that a customer uses. This might be an inefficient query that can’t be fixed because of the way that the tables are structured or that the db is just too large and needs to be sharded or split in some way. Often it’s not a crisis state but as the db grows it could become one. Unless a customer complains there is often not a ticket open for it.
 3. Code debt: This is similar but not the same as DX debt. This is messy or poorly structured code that makes devs not want to touch it because it is brittle or because it’s poorly understood. This slows down any work that involves this code and developers will be reluctant to work on this code because they know that it will take them longer than normal and they know they are more likely to introduce bugs which they will be blamed for. Generally this is the most common and most difficult to fix type of debt.


Understanding the impact of technical debt on engineers

For developers, having a lot of technical debt is much like having a lot of financial debt. Not fixing it can be like just paying the minimum on a credit card with a large balance every month. You work hard only to just keep your head above water and never get ahead.

If you go too long without ever paying down technical debt, this can lead to developers feeling dissatisfied, that nobody cares about their concerns, and possibly leaving. This is why it’s important to have devs at least understand the decision-making process around what debt gets worked on and when, and get their buy in as much as possible.


The unique challenge of technical debt on startups

Handling Technical Debt in small teams at startups can be the most challenging because the demands being placed on the teams to deliver features now can be tremendous. If you are at the stage where you are still trying to find customers you are often told that the next feature is the feature that’s going to bring in all the customers finally, and that nobody is going to care about how messed up the schema is if we run out of money.

The good news is that this is almost never true.

However, the truth behind it is that not delivering features and bug fixes is going to have an impact in the 3-6 months to one year timeframe rather than 1-3 year timeframe as it might be at a more established company. You often don’t really have the bandwidth to work on debt if you have unfinished features or significant bugs.


So what to do?

Does this mean you just never tackle technical debt and just let it gather, hoping the systems don’t fall over in the meantime?

The answer isn't straightforward. For a small startup in its first year or two, you need to consider two things: first, examine why you've accumulated so much technical debt so early, and second, acknowledge that focusing on product-market fit may need to take precedence over debt reduction until you have traction.

Is the debt something that affects customers like performance debt, then it’s not really technical debt, it’s a bug that should be treated like a bug.


Catalog and Prioritize

What you can do in the meantime is catalog and prioritize. When a significant bit of technical debt surfaces, someone should be tasked with documenting it, then the team should be asked to give it a priority or urgency score. Developers will be tempted to make everything urgent but it should be emphasized that these are only for deciding which things will be worked on not whether they will be worked on. Making everything high priority just means the wrong decisions will be made about which things to work on.


Approach One: Tech Debt Sprint

I am using the term sprint here but it can be any defined timeframe. Two weeks is a good amount of time though to get some actual work done but not too significantly digress from making product progress. But it could be a month or whatever. The important thing is that the team knows that they have this specific amount of time to work on tech debt but that tasks that are partially finished will not be carried over, so they should try to pick things that they have a very high chance of being able to finish. This tends to make the team think long and hard about what is going to give them the most value since they are doing the work for themselves rather than sometimes mythical “customer”.


Rinse and Repeat

One of the jobs of an Engineering Leader is to understand this tech debt well and understand what tradeoffs are happening and make sure everyone (both Product teams and Dev teams) understands it as well. The best situation is where there is a mutual empathy between product and dev teams where everyone understands why everyone wants what they want so compromises can be made where everyone feels heard.

When is it a good time to have a tech-debt sprint? I think after there has been a major feature push this is a good time to give the team some “me” time.

How do you know it’s been a successful tech debt sprint? Much like a regular sprint in that all the work that has been committed to, got completed. Generally I would like to see 1 or 2 “high priority” items finished in a tech debt sprint plus a couple more lower priority ones. This isn’t always possible because high priority items can often be something that can’t be finished in a single sprint. What do you do with these? I will cover that in the next approach.


Approach Two: Debt Reduction as a Feature

This approach is a lot more challenging. Trying to get the business to sign off on doing a significant chunk of work that won’t have immediate direct consequences is going to be a challenge and rightly so.

However, if the debt meets our definition of debt in that it affects delivering value, you will need to make a case to the business that you will deliver more work faster if you can remove this impediment.

To illustrate how to make a compelling business case for technical debt reduction, let's examine a common scenario involving build system performance. This example demonstrates how to quantify the impact of technical debt and present a clear path to resolution.


Example: Build System Performance Impact

Our build system currently takes 30 seconds to compile and reload after each code change. Developers make an average of 50 changes per day while developing features.


Impact Analysis

 * 30 seconds waiting time per code change
 * 50 changes per day
 * Total daily wait time: 25 minutes per developer
 * For a team of 5 developers: 125 minutes (2.08 hours) of total team wait time per day
 * Monthly impact: ~42 hours of developer wait time
 * At an average fully-loaded developer cost of $100/hour: $4,200 in lost productivity per month


Proposed Solution

Invest 3 weeks of one developer's time to:

 1. Implement incremental compilation
 2. Optimize build caching
 3. Update build configuration for parallel processing
 4. Implement distributed build system
 5. Create comprehensive test suite for build system

Expected Results:

 * Reduce build time from 30 seconds to 5 seconds
 * New monthly wait time: 7 hours (vs current 42 hours)
 * Monthly savings: 35 hours of developer time
 * Financial impact: $3,500 saved per month


Return on Investment

 * Investment: 3 weeks of developer time = $12,000 (120 hours × $100/hr)
 * Monthly savings: $3,500
 * Break-even point: ~3.4 months
 * Annual savings after break-even: $42,000


Additional Benefits

 1. Improved Developer Experience
    * Reduced context switching
    * Higher job satisfaction
    * Better retention
 2. Faster Feature Delivery
    * More time spent on actual development
    * Quicker iterations on bug fixes
    * Faster customer feedback cycles
 3. Better Quality
    * Developers more likely to make small, incremental changes
    * More willing to refactor when needed
    * Increased test coverage due to faster test runs


Implementation Plan

 1. Week 1:
    * Profile current build system
    * Implement incremental compilation
    * Initial build caching setup
 2. Week 2:
    * Complete build caching optimization
    * Implement parallel processing
    * Begin distributed build system setup
 3. Week 3:
    * Complete distributed build system
    * Create comprehensive test suite
    * Team training on new system
    * Performance validation and tuning


Sprint Considerations

Given that this work exceeds our standard two-week tech debt sprint window, we have several options:

 1. Split the work:
    * Sprint 1 (2 weeks): Implement core improvements (incremental compilation and caching)
    * Future Sprint: Complete distributed build system and testing
 2. Treat as a feature:
    * Track this as a performance improvement feature rather than tech debt
    * Include in regular sprint planning
    * Break into smaller, deliverable chunks
 3. Extended tech debt period:
    * Request a one-time extended tech debt period
    * Justify based on ROI and team impact


Success Metrics

We will track:

 1. Average build times
 2. Developer productivity (stories completed per sprint)
 3. Team satisfaction scores
 4. Time to market for new features


Risk Mitigation

 * Phased rollout to catch issues early
 * Keep old build system as fallback
 * Daily progress updates to stakeholders
 * Clear rollback plan if issues arise

This approach takes a lot more work but you need to make the case that this is going to either make or save us real money or there is no reason the business should sign off on it.


Final Thoughts

Managing tech debt involves weaving together both a strong technical understanding of the underpinnings of the system and also an understanding of what motivates both the business and developers. Success comes from finding the right balance between three key factors:

 1. Timing and Prioritization
    * Not all tech debt needs to be addressed immediately
    * Focus on debt that actively impedes value delivery
    * Use the cataloging system to make informed decisions
    * Choose the right approach (sprint vs. feature) based on scope and impact
 2. Communication and Transparency
    * Keep both technical and business stakeholders informed about the state of tech debt
    * Use data and metrics to illustrate impact
    * Build mutual empathy between product and engineering teams
    * Make the cost of delay visible without creating unnecessary alarm
 3. Sustainable Progress
    * Regular small improvements through tech debt sprints
    * Strategic larger investments when ROI justifies it
    * Monitor the effectiveness of debt reduction efforts
    * Adjust approaches based on results and team feedback

Remember that technical debt isn't inherently bad—it's often a byproduct of moving quickly and making pragmatic choices. The goal isn't to eliminate all debt but to manage it effectively. By maintaining this balanced approach, you can move both the product and the system forward together, keeping your team productive and your business competitive.

The most successful tech debt management strategies are those that become part of your engineering culture rather than one-off initiatives. When developers feel heard, the business sees value, and customers benefit from improved delivery speed, you've found the sweet spot in technical debt management.