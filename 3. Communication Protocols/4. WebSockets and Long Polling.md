# WebSockets and Long Polling

**WebSocket** is a long lived persistent TCP connection (often utilizing TLS) between a client and a server which provides a real-time full-duplex communication channel. These are often seen in chat applications and real-time dashboards.

**Long Polling** is a near-real-time data access pattern that predates WebSockets. A client initiates a TCP connection (usually an HTTP request) with a maximum duration (ie. 20 seconds). If the server has data to return, it returns the data immediately, usually in batch up to a specified limit. If not, the server pauses the request thread until data becomes available at which point it returns the data to the client.

## Analysis

WebSockets are Full-Duplex meaning both the client and the server can send and receive messages across the channel. Long Polling is Half-Duplex meaning that a new request-response cycle is required each time the client wants to communicate something to the server.

Long Polling usually produces slightly higher average latency and significantly higher latency variability than WebSockets.

WebSockets do support compression, but usually per-message. Long Polling typically operates in batch which can significantly improve message compression efficiency.