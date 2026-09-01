# API 参考

[English](api.md) | [文档索引](README.zh-CN.md)

本清单由本仓库 package 的 `go doc -short` 生成，用于快速查看公共面。精确语义以源码和测试为准。

## 包

### `gnalloy.org/transport-http3`

包名：`http3`

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
