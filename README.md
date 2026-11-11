# Suhas Manjunath

Senior manager of software development at Amazon, in Seattle. I lead teams
that build AI, data, and observability platforms.

**TLDR.** Four small Python tools, nothing to install. Each one is a
decision that used to live in someone's head, written down so a second
person gets the same answer. The table below is the whole catalog. Open a
repo only if its row is your problem.

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

## The four

| | Read it if | What you get |
|---|---|---|
| [otl](https://github.com/gmsuhas/otl) | a trace stops short of the thing that broke | one trace from a text log, and a span left open stays open |
| [ramp](https://github.com/gmsuhas/ramp) | you cannot tell whether the new version is the one failing | the version written on the request, and a count the same day |
| [veto](https://github.com/gmsuhas/veto) | a review gives a different answer the second time | `pass`, `fail`, or `watchlist`, and a missing number fails |
| [playyard](https://github.com/gmsuhas/playyard) | you want the small version of an idea you never finished | a few lines of a language, a day added up, one HTML file |

## Everything else

The other public repositories are forks. Each description says so, and
names the upstream it tracks. They are not my work. `spawnpackage` is an
empty repository from 2015.
