# Suhas Manjunath

Two small Python tools, each one file you can read through. No dependencies
beyond Python 3.9.

## [otl](https://github.com/gmsuhas/otl)

A plain-text event log turned into one OpenTelemetry trace.

A start and a stop become a span. A span opened inside another becomes its
child. A failure becomes an error status, and a start that never stops stays
in the trace as unclosed instead of being given a made-up duration. The same
tree is written as OTLP JSON: hex trace and span ids, integer span kind and
status, timestamps as decimal strings of nanoseconds.

That is the part that breaks in production before anyone picks a backend. An
unclosed span is held until the process notices. A trace reconstructed from
logs is what an incident becomes when the spans were never exported. A
collector rejects a trace id that was base64-encoded, or a span kind written
as a name. otl is those three failures, small enough to read.

It sits in front of projects that already do the rest.
[beam-telemetry/telemetry](https://github.com/beam-telemetry/telemetry)
dispatches events and is not OpenTelemetry.
[posit-dev/picotel](https://github.com/posit-dev/picotel) sends spans, and
[dimaqq/otlp-json](https://github.com/dimaqq/otlp-json) serialises spans the
official SDK already built. otl starts from the line of text.

## [playyard](https://github.com/gmsuhas/playyard)

Three text tools, same constraint:

- a small interpreter, cut down to print, assign, arithmetic, and one loop
- a day log that adds up where the time went, matching whole words
- one HTML file, styling included, with nothing to fetch

The other public repos on this account are forks, kept even with upstream.
