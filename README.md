# Suhas Manjunath

I write small Python tools and keep them dependency-free, so the interesting
part is the behavior rather than the setup. Each one is explicit about what
it will not do.

## [veto](https://github.com/gmsuhas/veto)

A checklist for a long call. Given the figures, it returns `pass`, `fail`, or
`watchlist`. Both entry modes failing is a watchlist, not a smaller trade,
and a missing number fails the rule that needs it.

The same decision is a command, `veto check`, and a one-tool MCP server,
`veto serve`, so a host that already runs other servers can call it. It does
not fetch prices and it does not recommend a trade. A pull request to add it
to the public list of MCP servers is open.

## [otl](https://github.com/gmsuhas/otl)

A plain-text event log turned into one OpenTelemetry trace.

A start and a stop become a span, and a span opened inside another becomes
its child. A failure is an error status. A start that never stops stays
unclosed, rather than being given a made-up duration. `otl otlp` writes the
trace as OTLP JSON, and a date turns the time of day into unix time so a
collector can place it.

## [playyard](https://github.com/gmsuhas/playyard)

Three text tools, under the same constraint:

- a small interpreter: print, assign, arithmetic, and one loop
- a day log that adds up where the time went, matching whole words
- one HTML file, styling included, with nothing to fetch

## Everything else

Eleven of the other public repositories are forks, kept even with upstream
and not presented as my work. `spawnpackage` is an empty repository from
2015.
