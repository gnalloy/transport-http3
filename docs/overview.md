# Overview

[简体中文](overview.zh-CN.md) | [Docs Index](README.md)

## Purpose

HTTP/3 transport binding that maps QUIC request, control, QPACK, and push streams into Gnalloy channel pipelines.

This module owns an I/O boundary. It creates or adapts Gnalloy Channels for a concrete transport while protocol parsing, business handlers, TLS policy, and observability remain in other modules.

## Repository Identity

- Module path: `gnalloy.org/transport-http3`
- GitHub repository: `github.com/gnalloy/transport-http3`
- Default branch: `dev`
- License: Apache-2.0

## Package Map
- `gnalloy.org/transport-http3` (`http3`)

## Direct Gnalloy Dependencies

- `gnalloy.org/codec-http3`
- `gnalloy.org/gnalloy`
- `gnalloy.org/transport-quic`

## Direct Dependents in the Current Repository Set

- `gnalloy.org/benchmarks`
- `gnalloy.org/transport-webtransport`

## Architecture Position

Gnalloy keeps the core small and dependency-light. This repository is a replaceable module around one responsibility, connected through explicit Go packages instead of runtime discovery.

## Compatibility

The public import path is `gnalloy.org/transport-http3`. Until the first stable tag is published, use `@dev` or an explicit pseudo-version selected by your dependency policy.
