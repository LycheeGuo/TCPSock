# GrainAI

GrainTCP-style VLESS/WebSocket TCP relay with SOCKS5, HTTP CONNECT, and HTTPS CONNECT upstream support.

Set `UPSTREAMS` as a Worker secret. It accepts standard proxy URIs or raw lines from the supplied proxy result files.

Examples:

socks5://user:pass@1.2.3.4:1080
http://5.6.7.8:8080
https://user:pass@9.10.11.12:443

For checker lines such as `IP:PORT:https | : | ...`, GrainAI interprets the `https` tag as an HTTP CONNECT-capable proxy over a plain TCP connection. Use an explicit `https://` URI only when the connection to the proxy itself is TLS.

Deploy:

npm install -g wrangler
wrangler secret put UPSTREAMS
wrangler deploy
