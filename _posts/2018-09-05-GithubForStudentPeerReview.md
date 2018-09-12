---
title: "Using Github for Student Peer Reviews"
excerpt: "Teaching development students to work together using github pull-requests as a peer-review tool"
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

# Using github to teach github and best practices
During last year's review of the development courses I teach at Games and Interaction, we felt students hadn't been pushed to work together enough (they formed small cliques, and certain students would be left behind), and some of them hadn't taken github to heart (even though they had handed in all their assignments through it), or had trouble understanding what they were doing and why they were using it at all.

Luckily, we'd recently formalized how we work together using github at ECT, and as such I thought I might be able to use github as a tool to teach students how to work together, push them to interact with a higher variety of peers, and at the same time learn how to use github. The basic github flow ECT (ideally) employs is roughly as follows:

 * Fork a repository from github.com/hku-ect
 * Do work on a feature on your own fork
 * Submit a Pull-Request to the repository at github.com/hku-ect

![Teaching Git (source: https://xkcd.com/1597/)](https://imgs.xkcd.com/comics/git.png){: .image-left } This forces the work you do to be viewed by at least one other developer, preventing a flow of work that is just "thrown over the fence" without anybody knowing about it or having seen it. It promotes an attitude towards review on both sides, the person doing the work as well as the person receiving it. Github further allows you to add settings for how many times work must be approved, which is especially useful for the setup I had in mind for students.

# Translating to student environment
This brings me to the specifics of how I wanted to employ this as a peer review tool for students. First off, I made sure the master branch on the repository was blocked from directly being "pushed" to, which meant the only way to submit work was through pull-requests. Then I set it so that each pull-request needed two reviews, and added all the students as collaborators. We decided to work with branches, and not forks, because of the need to pull-request towards the master branch, and this way we could easily preview what students were working on without having to browse to their version of the repository.

Finally, there's a didactical approach to the whole thing. The only thing students are graded for, is "having done two reviews per week". There is no other requirement, not even uploading work (although it's hard to review anything without there being work to review). The entire system relies on peer-pressure to get people to submit code for review.

{% include figure image_path="/assets/images/pull-requests.png" alt="Pull request overview" caption="Pull request overview" %}

# Automated statistics for gamified didactics
This on its own works well enough, but it's a huge hassle to manually check if students have done the two reviews per week, or to keep tabs on how well they're doing and perhaps even nudge them towards positive behaviours. Luckily, github contains a REST API, that allows you to request information through HTTP GET requests. These return JSON, simple structured data in a standardized text-format, which you can then parse. There are a few key things we measure and signal back to students:

 * We count the amount of reviews done, and indicate the "target" for the current week. These are posted as a group, so all students see each other's data.
 * We count the amount of pull-requests students have done, and indicate that if there is no work to review, students should first ask those with the least PR's to submit work.
 * We calculate a score for each student. The calculation is: ( amount-of-reviews + "likes"-received-for-comments ) * number-of-unique-students-reviewed
 
{% include figure image_path="/assets/images/student_statistics.png" alt="student stats for week 1 (including their often hilariously inappropriate names)" caption="student stats for week 1 (including their often hilariously inappropriate names)" %}
 
Especially the last part, how we calculate the score, (hopefully) pushes students to try to give constructive and useful feedback, and review as many different people as possible (avoiding the development of fixed feedback cliques that tend to leave out struggling students). At the end of a certain period, we'll give the top-3 students a prize. What exactly is still being discussed, but the idea is that it is only valuable when shared (just to drive the point home).

Reading these stats from github is done through Python, again a nice link to subject matter students received previously, providing an real-world example of what you can use that knowledge for. [Here's the script we use](https://gitlab.com/snippets/1753337).

Once this program has run at least once, I'll update with lessons learned, so stay tuned!
