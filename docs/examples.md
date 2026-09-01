# Examples

[简体中文](examples.zh-CN.md) | [Docs Index](README.md)

## Example 1: Add the Module to an Application

```bash
mkdir gnalloy-app && cd gnalloy-app
go mod init example.com/gnalloy-app
go get gnalloy.org/transport-http3@dev
go doc gnalloy.org/transport-http3
```

## Example 2: Inspect Current Packages

The current source tree exposes these package import paths:
- `gnalloy.org/transport-http3`

Use `go doc` against the package that matches the behavior you need:

```bash
go doc gnalloy.org/transport-http3
```

Selected current exported entry points:
- `var ErrInvalidConnection = errors.New("gnalloy/transport/http3: invalid connection") ...`
- `type Config struct{ ... }`
- `type Session struct{ ... }`
- `type SessionStats struct{ ... }`
- `type StreamChannel struct{ ... }`
- `type StreamKind uint8`

## Example 3: Use Executable Tests as Behavioral Examples

Repository tests are executable examples of supported behavior. Start with the selected names below, then read the matching `_test.go` files for complete setup and assertions. See [Testing and Performance](testing.md) for the complete discovered list.

```bash
GOWORK=off GOTOOLCHAIN=local go test ./... -run Test -count=1
```

Selected current test, benchmark, fuzz, and example entry points:
- `TestSessionAcceptPushStreamReadsPushID`
- `TestSessionAcceptRemoteControlStreamReadsSettings`
- `TestSessionAcceptsConfiguredALPN`
- `TestSessionOpenPushStreamWritesTypeAndPushID`
- `TestSessionOpenRequestStreamInstallsPipelineAndWritesFrames`
- `TestSessionOpensLocalControlStreamAndWritesSettings`
- `TestSessionRejectsNilConnection`
- `TestSessionRejectsNonHTTP3ALPN`
- `TestSessionRejectsNonTLS13`
- `TestSessionRoundTripOverRFC9000QUIC`
- `TestSessionStatsTrackAcceptedStreams`
- `TestSessionStatsTrackStreamsAndBytes`
- `TestStreamChannelCloseCancelsReadAndClosesWriter`
- `TestStreamChannelEOFDoesNotCancelRead`

## Example 4: Cross-Module Assembly

Direct Gnalloy dependencies for this module:
- `gnalloy.org/codec-http3`
- `gnalloy.org/gnalloy`
- `gnalloy.org/transport-quic`

Assembly guidance:
- Use this transport to own the concrete I/O endpoint and connect it to Gnalloy Channel and EventLoop contracts.
- Protocol parsing stays in codec modules and policy stays in handler modules.
- Platform-specific capability checks should happen during application startup and integration tests.

## Example 5: Pressure-Test Harness

For sustained load, wire this module into a scenario under `gnalloy.org/benchmarks` or a runnable client under `gnalloy.org/examples` when the module participates in network traffic. Record host, OS, CPU, Go version, protocol, payload, concurrency, warmup, repetitions, throughput, and p99 latency in the report.
