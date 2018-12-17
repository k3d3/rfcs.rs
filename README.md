# RFCs.rs

(Currently in an experimentation phase - please make suggestions, big or small, as to how to improve this page or project!)

RFCs.rs is (currently) an experimental platform/idea that attempts to improve the current Rust RFC process.

There's lots of documentation showing both problems and proposals of solutions:
- https://boats.gitlab.io/blog/post/rust-2019/
- http://smallcultfollowing.com/babysteps/blog/2018/06/20/proposal-for-a-staged-rfc-process/

And of course, we want to learn from people who are doing similar things:
- https://www.chromestatus.com/features

It's useful to gather a list of concrete complains people have about the current system:
- RFC threads get too long and it becomes impossible to quickly understand concerns.
  - It also becomes very tough to contribute to a specific concern or thread of thought.
- The current RFC system is too informal and implicit for Rust Team members
  - (from what I can tell, at least - I can only speak for others so well, and I'm likely wrong or missing important details)
  
## Goals

I'm hoping that, through this website, we can achieve the following goals:
- Make it easier for the community (and newcomers to the community) to spectate or take part in the RFC process.
  - It should be easy to grasp a general understanding of an RFC's state in the Design or "Spitball" stages very rapidly.
  - It should be easy to dig deeper into a specific thread or concern of an RFC, without sifting through unrelated
  reading.
  - It should be easy to contribute to a particular RFC's concern, without repeating others or causing disorganization.
- Make it simpler for the Rust core team, working teams, and community to maintain RFCs through the entire process.
  - This system should lift a chunk of the burden from the core team members in keeping up with RFCs.
  - In order to fulfill the first point, this point should (hopefully) not require extra work.
  
## Website Proposal

I hope, through this repo, that we can work our way towards a website that can fully support a working RFC system for Rust.
I have some rough ideas to start with, however there is certainly a lot of ground to cover for revamping the RFC system.

The proposal that has been laid out by Niko is very clear, and I believe we should use a website to fulfill it. While the
idea of using an organization of repos to organize RFCs is interesting, I believe it still requires too much boilerplate
and still takes away from achieving the simultaneous goals of 1) making it easier to see everything at a glance, and 2)
doing so without burdening maintainers.

There have been proposals, and they're good to work from, but I'd like to implement a strawman just so we can test how it
works in practice. Baseball bats not included.

## Open Questions

There are many unanswered questions in this proposal:
- How much of the RFC process should this take over, and how much should stay on Github?
- Who should moderate RFCs? Should concerns be "resolvable" in a design phase, and by whom?
- Should the "Evaulating" stage be represented at all on the website?

## Front Page

*(TODO: screenshot example here)*

As this will be the first page anyone sees when following or contributing to the RFC process, it's very important to
determine exactly how to lay this page out. As a first step, visuals aren't important.

I believe the front page's contents should include:
- List of RFCs in the Final Comment Period
  - There shouldn't be too many of these at any given time, so hopefully all FCPs can be displayed.
  - This is the set of RFCs that we want the most visibility on, so it should be front-and-centre.
  - Depending on how much space is taken up, FCP RFCs should show some information at a glance, likely a subset of:
    - RFC title
    - Category (libs, lang, core, docs, etc.)
    - Disposition (merge, postpone, close)
    - FCP end date
    - Number of likes, concerns, comments, etc. (or some subset)
- List of RFCs that have been recently created or updated
- List of RFCs that currently have lots of activity
  - Should these have half the space of the FCPs, so they can be placed beside each other?

Those are probably the more important things to have at a glance, and further down (for people who want to dig further):
- List of RFC categories
- Anything else?

Additionally, the top of the page should probably contain the usual things, like a search box and somewhere to log in.

There's also, of course, much more to the RFC process than just the design stage, so there will need to be some way to
access lists of Pre-RFCs (spitballs?), tracking RFCs (the "Implementing" stage), and RFCs in the Team stages.
Perhaps tabs, or simply a few links at the top of the page? Should RFCs in other stages be more prominent?

## RFC Page (Design Phase)

*(TODO: screenshot example here)*

The RFC page should contain two sections: The RFC itself, and the community input on said RFC. I'm unsure about whether
these two pieces should be stacked on top of each other, or reside in separate tabs on the page (or some other option).

The RFC section should contain:
- The RFC itself (of course)
- A slider or some mechanism to see previous iterations of the RFC
- The ability to vote for an RFC (similar to the github thumbs-up emoji on an Github issue's first comment)

The Community section should contain:
- A list of concerns
  - The ability to vote up a concern
  - A comments section for each concern
  - Perhaps a section for improvements, and a comment section for each of those
- A list of praises
  - Similar to above, minus the "improvements"
- A list of questions or clarifications?
  - Alternatively, maybe there should be a "general" comments section where people can ask questions, or give suggestions
  on small improvements of the text (e.g. fixing typos, or rewording for clarification)
  
The flow of RFCs in the design phase should be controlled by the core team, as they'd ultimately be the ones to reject
the proposal based on major concerns, set the Final Comment Period, and end the Design stage.

## Pre-RFC Page ("Spitballing" Phase)

*(TODO: screenshot example here)*

The Pre-RFC page should contain the same two sections as the RFC page, however with some differences:
- The Pre-RFC author has full control over the page. They can reject/resolve concerns, push the Pre-RFC to the RFC stage,
or kill the Pre-RFC entirely.

As the author has full control of this stage, they are the ones who can push this to the RFC stage (similar to how anyone
can create a new PR on rust-lang/rfcs).

## Tracking RFC Page ("Implementing" Phase)

*(TODO: screenshot example here)*

TODO: What should go on the tracking RFC page? How should Tracking RFCs even be listed?

## Other Pages

TODO: ???

## Other details

### Authentication

Authentication is a hard thing to get right, and network effect is always a burden on new systems. For these reasons,
and because it's already prominent in the Rust community, I propose that Github be used for authentication.

### RFC Format

To keep things similar to the existing system, RFCs should still be written in Markdown format. This will also allow for
RFCs to more seamlessly transition to Github issues.