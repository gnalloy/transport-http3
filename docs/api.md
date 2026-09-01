# API Reference

[简体中文](api.zh-CN.md) | [Docs Index](README.md)

This inventory is generated from `go doc -short` for the packages in this repository. It is a quick public-surface map; source files and tests remain the authority for exact semantics.

## Packages

### `gnalloy.org/transport-http3`

Package name: `http3`

```text
var ErrInvalidConnection = errors.New("gnalloy/transport/http3: invalid connection") ...
type Config struct{ ... }
type Session struct{ ... }
    func NewSession(conn quic.Connection, cfg Config) (*Session, error)
type SessionStats struct{ ... }
type StreamChannel struct{ ... }
type StreamKind uint8
    const StreamKindRequest StreamKind = iota + 1 ...
```
