---
layout: post
title:  "The ten project management commandments"
---

Over the course of
building <a href="http://www.rethinkdb.com">RethinkDB</a> we learned
many software engineering lessons. Most of these lessons feel like
rediscovered platitudes, but we still managed to mess them
up. Considering how many teams are struggling with shipping software,
I think these lessons are worth repeating.

# Instill shared culture

Sooner or later you&#8217;ll discover you&#8217;ve hired engineers
that have very different philosophies on how software should be
built. Say, a C programmer and a C++ programmer. The former will want
the codebase to look like the Linux kernel. The latter will want it to
look like the boost <span class="caps">MPL</span>
library. What&#8217;s a well-meaning engineering manager to do?

I&#8217;ve tried all possible ways of addressing the ensuing social
issues (including doing nothing), and found that there is only one
approach that works. Always, always, always fight to cultivate and
enforce shared culture. It can be unpleasant early on, but it&#8217;s
the only way I know of to build a team that&#8217;s both
happy <em>and</em> productive.

# Code review everything

The absolute best way to instill shared culture is to code review
every line of code before it ever goes into
mainline. (Why <em>every</em> line of code? Because code reviews
don&#8217;t stick if you do them selectively. Take my word for it
&#8212; some rules need to be absolute.)

Here&#8217;s how we do it. By default, the reviewer is always right,
and the author must fix every defect (we ask the reviewers to be
tough, but reasonable). If the author <em>really</em> disagrees with
the reviewer, they can appeal to a tech lead. The tech lead&#8217;s
decision is final, and cannot be appealed. In case of emergencies
(e.g. a broken build), the standard code review process can be too
slow, so we also allow quick reviews over the shoulder.

You can find a different way to do it, but we&#8217;ve found this to
be a pretty good system.

Code review is like exercise. Painful at the beginning, and any given
session might feel like a waste of time. But over the lifetime of a
project, it makes <em>all</em> the difference. Always code
review <em>every single commit</em>. No ifs, no buts, no exceptions.

# It&#8217;s the product, stupid

Ability to build great software and ability to build great products
are two completely orthogonal skills, and aptitude for the former does
not imply aptitude for the latter. It&#8217;s best to learn early that
software companies aren&#8217;t about building great
software. They&#8217;re about building great products. You have to
start with the product, and let great software be a means to an end.

Make sure every engineer on the team respects this principle. Whenever
possible, have people that understand <em>products</em> run the
show. Beware of people that care about a particular programming
language, technology, or an obscure technical sticking point more than
about making your users happy. They can derail your whole team and
firing them is often your best option.

# Fight complexity with all you&#8217;ve got

Linear increases in complexity cause superlinear increases in amount
of work to be done. Be careless about complexity, and before you know
it your development process will crawl to a halt.

Complexity increases the surface area of your project. In software
engineering, large surface area is death. Fight, fight, fight
complexity with everything you&#8217;ve got. If you can avoid adding
new functionality, fight like hell to keep it out. If you lose that
fight, see if you can get 80% of the functionality with 20% of the
work. Usually, you can. Fight like hell to do it that way. If you
lose <em>this</em> fight, either you&#8217;ve hit the one case in a
thousand where complexity is warranted, or, more likely, you should
have fought harder.

Less is more. Avoid grand designs. Keep the codebase as small as
possible.

# Pick abstractions carefully

Pick the simplest, most concrete possible implementation that solves
the customer&#8217;s problem. Avoid big abstractions &#8212; functions
are better
than <a href="http://hackage.haskell.org/package/lens">lenses</a> 99%
of the time. Use simpler language features whenever possible &#8212;
an if statement is better than a template specialization. Great
abstractions tend to feel very concrete because they make complex
tasks easy and simple to understand. That&#8217;s why functions and
pipes are better abstractions than monads
and <a href="http://www.haskell.org/arrows/">arrows</a>. Avoid grand
beautiful designs &#8212; they&#8217;re never as grand and as
beautiful as you&#8217;ve envisioned them.

Be careful about swinging too far to the other extreme. Once you
commit your project to an architecture, it can be extremely difficult
to change. If your abstractions aren&#8217;t flexible enough to solve
the customer&#8217;s problems, your competition will be right at your
heels.

Picking the right abstractions requires a great deal of care and
experience. Be thoughtful about this problem &#8212; if technology is
a differentiating factor in your product, this can mean the difference
between life and death.

# Sprints, deadlines, and estimates

I&#8217;ve observed the following two aspects of software development
so many times, I&#8217;ve learned to accept them as axioms:

1. Humans are terrible at time estimation for anything longer than 2-4
   days of work.
2. Lack of deadlines is a sure road to complex software with bad,
   overengineered abstractions.

Despite smelling like a fad, sprints are a surprisingly good solution
to the seemingly impossible scheduling problem. Break up all work into
no more than 2-4 day chunks (usually represented as issues in a
tracker). Assign these issues to people, and group them into sprints
of one to two weeks. Then work like hell together to get everything in
a sprint done on time.

It&#8217;s strange, but with the right people it works really, really
well. (Some people can&#8217;t work in this environment &#8212; in
that case your best option is to kindly ask them to switch employers).

# Treat big projects with care

Not all projects can be broken up in a way that allows fitting them
into a single sprint. Some projects are just too big. You have to
treat these projects differently.

Firstly, fight as hard as you can to <em>not</em> build big
projects. Break them up into smaller ones, find a different approach,
don&#8217;t build the feature in the first place, do everything you
have to do to keep them out.

If you&#8217;ve done all you can and still <em>must</em> build a big
project, build the absolute most minimal version that solves the
customer&#8217;s problem. Do all you can to decrease the scope. Make
sure there is a single engineer in charge of the project, and put
structure around it. Do a peer review of the initial design. Then set
up deliverable milestones, and do peer reviews for each
milestone. Once the project is feature complete in the shortest
possible amount of time, assign improvements as part of the standard
sprint schedule.

Keep the number of concurrent big projects to absolute minimum. One
big project per team of about eight to ten engineers is a good rule of
thumb.

# Never do large rewrites

Software rewrites and perpetual refactoring are a special case of big
projects, and are so prevalent that they deserve special
attention. Fight like hell <em>not</em> to allow big
refactors. Always, always, always keep refactoring within the confines
of a sprint.

If you absolutely must do a big rewrite, be triple-vigilant about
it. Peer review the initial idea, peer review milestones, be ruthless
about cutting complexity and scope. A big rewrite will take at least
three times what you&#8217;ve estimated (if you&#8217;re lucky).

Always keep a refactoring stack of at most depth one. If someone is
refactoring a part of the codebase (within the confines of a sprint,
or heavens forbid as a large project), make sure they don&#8217;t run
off refactoring other components. Always schedule refactoring as you
would any other change.

# Find a way to test religiously

There are hundreds of books written about different testing
methodologies (unit tests, integration tests, whitebox, blackbox,
etc.), but we&#8217;ve found that there is a much simpler way to
categorize tests: short ones and long ones.

Integrate any test that runs in less than a few seconds (including
unit and integration tests) into your <strong>development
process</strong>. Use a tool
like <a href="https://travis-ci.org/">Travis CI</a>, and run the short
test suite after every commit. Never merge code that breaks the short
test suite into mainline &#8212; be religious about it, and make it a
part of the code review process. Don&#8217;t write automated tests
that take more time to maintain than the code itself, but do write
automated tests.

Any test that takes longer than a minute to run is a long
test. Integrate long tests into your <strong>release
process</strong>. Since you can&#8217;t run long tests after every
commit, they lag behind development and tend to bitrot. Maintaining
long tests requires a lot of dedication and planning, and is often
impractical until you have full-time QA and release management teams.

Don&#8217;t abandon <em>all</em> automated testing because you
don&#8217;t yet have the organizational support structure to manage
long tests or because you wrote tests early on that required too much
maintenance overhead. Even a small test suite that integrates into the
development process makes an enormous difference in quality.

# Prepare to fight for your beliefs

As the Klingons say it, &#8220;the truth must be won on a
battlefield.&#8221; Sooner or later, some of your team members will
strongly disagree with some of these ideas.

Debate everything vigorously, but once the decision is made, make
sure <em>everyone</em> is on board, regardless of their personal
reservations. That means pestering people to follow the rules until
the process becomes self-perpetuating, confronting people that
undermine decisions they disagree with, and, in pathological cases,
firing talented engineers who can&#8217;t buy into the overall
engineering culture. (They may very well end up working in a very
different, but equally productive culture.)

It can be very unpleasant, but it must be done. Remember &#8212; your
first responsibility is to the team, not to any given individual
contributor.

