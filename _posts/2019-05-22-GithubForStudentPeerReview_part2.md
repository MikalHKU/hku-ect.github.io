---
title: "Using Github for Student Peer Reviews Part 2"
excerpt: "Teaching development students to work together using github pull-requests as a peer-review tool (2/...)"
author: Aaron Oostdijk
header:
  overlay_image: /assets/images/pull-requests.png
  image_description: "Github pull-request overview"
  teaser: /assets/images/pull-requests.png
tags: 
  - github
  - development
  - didactics
---

<style type="text/css">
.image-left {
  display: block;
  margin-left: auto;
  margin-right: auto;
  float: right;
}
</style>

# Lessons learned
This past year we started an experiment with github as a peer review tool. [I detailed this in an earlier blog-post](https://pong.hku.nl/blog/GithubForStudentPeerReview/). Now that year is almost completed, and we've largely left the students to their own devices since the start of the second semester.

A few things that we've taken away from the experiment:
 * Students are more proficient with git than last year  (Good!)
 * Forcing peer-review only seemed to work well with homework assignments (So-so)
 * Pull-requests are too "one off" to induce in-depth dialogue (Bad)

# What worked, what didn't
The first iteration included a score calculation based on what students had done in the previouw week. I've been trying to find a research paper that shows that testing for something causes people to optimize for the way your testing (which I know exists, but is impossible to find because of the words employed), instead of focussing on what you're asking them to do, because this is exactly what we observed. Because of this, we quickly moved to a second iteration of the score-system, redesigned by a student (!). This second system produced less incentive to "game the system", but also reduced engagement. The type of engagement did appear to be more authentic (less formulaic, more content-focussed).

Overall the second iteration focussed on two things: 
 * Measuring activity in a fair way. It was made harder to do all the work at the end or up front, instead it rewarded consistency by awarding more points for doing smaller amounts of work over time, 
 * Reducing "false positives" for bad interactions (badly reviewing lots of work was no longer a rewarding activity).

The goal of getting students more proficient with git has already been successful, but I'm still not happy with how well they're picking up on the importance of peer-reviewing.

# What's next
For the next iteration we're going to try and use different parts of git for different purposes.

## Git flow
First off, the pull-request & review setup remains the same (implementation of this often call themselves git flow). Our implementation of this process is:
 * You create a branch of the current repository (could also be on your own git)
 * You do some work, that you commit to this branch
 * You create a Pull-Request from your working branch to the current master
 * At least 2 students need to OK this Pull-Request, and can provide feedback

As you can see, students will still need to review each other's work, but this "reviewing" will be very minor compared to the previous iteration (where they would really look at the contentual quality). It's really just a "this passes the standard for a commit".

## No more scoring
Secondly, the automated scoring will probably be removed entirely, replaced with a weekly check-in by staff members (or perhaps TAs!). The problem with the current system is that all the pull-requests are so spread out, that doing a weekly check-in becomes very difficult! Luckily there's a simpler approach, which is the next point...

## Issues
Thirdly, we're introducing the use of "issues" to track a students progress on a larger project or feature.

The idea of an issue in git is that you can create one to work on something over a longer period of time. It's also possible to reference issues when doing commits, which then get added to the overall discussion of an issue. Other members of the project can then look at what you've been doing, and comment on it there (and you comment yourself on what you want people to look at, for instance).

This is the structure we want to try: students work on something over time, and discuss their work with each other on a non-arbitrary basis. The pull-request / review simply becomes a part of the workflow, and doesn't require much "discussion" (or grading). Crucially, this also remains part of the responsibility of students (otherwise they don't need each other for anything, and it just becomes private homework).

Staff is then assigned students (potentially rotating over time) and asked to check on the issue these students are working on. Students are asked to always have a "running issue", but it's up to them how large this task is, what the task is about, and if they want to close the current one and start a new one.

# Coming Soon 
Check back next year for an update on how this new setup panned out!