# Tracing & Correlation

Distributed tracing connects events across services.

## Goals
- Visualize end-to-end latency.
- Identify critical path and bottlenecks.
- Correlate logs, metrics, traces.

## Key Concepts
- Trace, Span, Span Context, Baggage.
- Propagation (W3C Trace Context): `traceparent`, `tracestate`.

## Instrumentation Approaches
- Auto instrumentation (agents)
- Manual instrumentation (OpenTelemetry SDK)

## Sampling Strategies
- Head vs Tail sampling.
- Dynamic sampling (error / latency biased).

## Correlation Patterns
- Inject trace/span IDs into structured logs.
- Include high-cardinality attributes carefully.

## Tooling
- OpenTelemetry Collector pipelines (receivers -> processors -> exporters).

> TODO: Add example collector config.
