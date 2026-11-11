# Suhas Manjunath

Senior manager of software development at Amazon, in Seattle. I lead teams
that build AI, data, and observability platforms, and I still write the
small version of a problem myself before I ask anyone to staff it.

The tools below are that version. Each one is Python, dependency-free, and
explicit about what it will not do. The interesting part is the behavior,
not the setup: a decision you can re-run, a trace you can read, a count
that names the variant which failed.

Longer writing is on [LinkedIn](https://www.linkedin.com/in/gmsuhas).

## [otl](https://github.com/gmsuhas/otl)

A plain-text event log turned into one OpenTelemetry trace.

A start and a stop become a span, and a span opened inside another becomes
its child. A failure is an error status. A start that never stops stays
unclosed, rather than being given a made-up duration. `otl otlp` writes the
trace as OTLP JSON, and a date turns the time of day into unix time so a
collector can place it.

## [ramp](https://github.com/gmsuhas/ramp)

Decides which variant a request gets, and writes that decision as one
`feature_flag` event on the span that was open around it.

The bucket is a number from 0 to 99, stable for a flag and an identity. A
ramp of 10 sends the numbers under 10 to the treatment. The event uses the
names the OpenTelemetry feature-flag registry already records, so the same
line can be read back as a trace and counted: how many of each variant
failed. It does not serve the flag, and it does not say the treatment won.

## [veto](https://github.com/gmsuhas/veto)

A checklist for a long call. Given the figures, it returns `pass`, `fail`, or
`watchlist`. Both entry modes failing is a watchlist, not a smaller trade,
and a missing number fails the rule that needs it.

The same decision is a command, `veto check`, and a one-tool MCP server,
`veto serve`, so a host that already runs other servers can call it. It does
not fetch prices and it does not recommend a trade.

## [playyard](https://github.com/gmsuhas/playyard)

Three text tools, under the same constraint:

- a small interpreter: print, assign, arithmetic, and one loop
- a day log that adds up where the time went, matching whole words
- one HTML file, styling included, with nothing to fetch

## Everything else

The other public repositories are forks, kept even with upstream and not
presented as my work. `spawnpackage` is an empty repository from 2015.
