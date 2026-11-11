# Suhas Manjunath

Senior manager of software development at Amazon, in Seattle. I lead teams
that build AI, data, and observability platforms.

**TLDR.** Four small Python tools, nothing to install. Each one is a
decision that used to live in someone's head, written down so a second
person gets the same answer. Read the line under a name. Open the repo
only if that line is your problem.

## The story

I kept meeting the same failure in different clothes.

A checkout breaks and the trace stops short of the operation that broke, so
the team argues about vendors instead of about the request. A change rolls
out to some customers and not others, and when errors rise nobody can say
whether the new version caused them, so the whole launch gets undone. A
review I ran twice in one week gave two different answers, because a number
that was "near" the line counted as a pass the second time. A day disappears
because it was never written down in a form anyone could add up.

In every case the information was already there. What was missing was one
agreed way to read it. I write that way down, small, before I ask anyone to
staff the real version. A thing you can re-run beats a thing you have to
trust.

The four tools are those readings. They share a constraint and nothing else:
Python, no dependencies, and an explicit list of what they will not do.

Longer writing is on [LinkedIn](https://www.linkedin.com/in/gmsuhas).

## [otl](https://github.com/gmsuhas/otl)

**TLDR.** A text log becomes one trace, so you can see the request that
broke instead of buying a tracing backend to find out.

A start and a stop become a span. A span opened inside another becomes its
child. A start that never stops stays open, because a made-up end time is
how the failure disappears.

## [ramp](https://github.com/gmsuhas/ramp)

**TLDR.** The version a customer got is written on the request, so when
something fails you know the same day whether the new version is the one
failing.

Each customer keeps a number from 0 to 99. A rollout of 10% sends the
numbers under 10 to the new version. A failure counts against the version
they actually got. It does not choose the percentage, and it does not
declare a winner.

## [veto](https://github.com/gmsuhas/veto)

**TLDR.** A review answers `pass`, `fail`, or `watchlist` from the figures
you give it, so Thursday's answer matches Monday's.

A missing number fails the rule that needs it. "Near enough" is not a pass.
It does not fetch a price and it does not recommend a trade. The same check
is a command and a one-tool MCP server.

## [playyard](https://github.com/gmsuhas/playyard)

**TLDR.** Three things I kept meaning to have, each small enough to finish:
a few lines of a toy language, a day added up by where the time went, and
one HTML page with nothing to fetch.

## Everything else

The other public repositories are forks, kept even with upstream and not
presented as my work. `spawnpackage` is an empty repository from 2015.
