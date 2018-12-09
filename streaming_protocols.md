
Name | Info
-- | --
Adobe HDS (HTTP Dynamic Streaming) | for Adobe Air
[Apple HLS](https://developer.apple.com/documentation/http_live_streaming) (HTTP Live Streaming) | for streaming to iOS-based devices—including iPhone, iPad, iPod touch, and Apple TV—and on desktop computers (macOS) and Android...
[Microsoft Smooth Streaming](https://www.microsoft.com/silverlight/smoothstreaming/) | HTTP-based media delivery via the Silverlight browser plug-in 
[MPEG DASH](https://en.wikipedia.org/wiki/Dynamic_Adaptive_Streaming_over_HTTP) | Support via the HTML5 [Media Source Extensions](https://en.wikipedia.org/wiki/HTML5_video#MPEG-DASH_Support_via_the_HTML5_Media_Source_Extensions_(MSE)) (MSE)

* RTSP/RTP
* RTSP/RTP (MPEG-2 Transport Stream)
* RTSP/RTP over HTTP.

* RTMP (MPEG-TS)

Name | Info
-- | --
**RTP** (Real-time Transport Protocol) | is a network protocol for delivering audio and video over IP networks.
**RTSP** (Real Time Streaming Protocol) | [RTSP 1.0](https://tools.ietf.org/html/rfc2326) and [RTSP 2.0](https://tools.ietf.org/html/rfc7826) in 2016.
**[RTMP](https://www.adobe.com/devnet/rtmp.html)** (Real-Time Messaging Protocol), **RTMPS** (secure over TLS/SSL), **RTMPT** (tunneled over HTTP) | streaming protocol designed by Adobe for high-performance transmission of audio, video, and data.
**[WebRTC](https://webrtc.org)** (Web Real-Time Communication) | Real-Time Communications (RTC) capabilities via simple APIs for the web browsers, that can be used by video-chat, voice-calling, and P2P-file-sharing Web apps.
**[WebSocket](https://tools.ietf.org/html/rfc6455)** | is a protocol that providing (full-duplex?) communication channels over a single (persistent?) TCP connection between server (web servers) and client (web browsers) so they can exchange data at any time. Through WebSocket, servers can pass data to a client without prior client request, allowing for dynamic content updates. Combined with The WebSocket API ([WSAPI](https://html.spec.whatwg.org/multipage/web-sockets.html)), it provides an alternative to **[HTTP polling](https://tools.ietf.org/html/rfc6202)** (HTTP was not initially meant to be used for bidirectional communication) for two-way communication from a web page to a remote server. [Why use WebSockets?](https://www.fullstackpython.com/websockets.html)
**[HTTP/2](https://http2.github.io/faq/)** | [Evolution of HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Evolution_of_HTTP), [Does HTTP/2 make websockets obsolete?](https://stackoverflow.com/questions/28582935/does-http-2-make-websockets-obsolete), [No WebSocket over HTTP/2](https://daniel.haxx.se/blog/2016/06/15/no-websockets-over-http2/), [Web Push](https://en.wikipedia.org/wiki/Push_technology#Webpush), [Journey from WebSockets to HTTP/2](https://building.lang.ai/our-journey-from-websockets-to-http-2-4d069c54effd)
**HTTP/3** | In developement. HTTP/3 is the coming new HTTP version that uses *QUIC* (Quick UDP Internet Connections) for transport!. HTTP over IETF-QUIC [[HTTP/QUIC]](https://daniel.haxx.se/blog/2018/11/11/http-3/) [[The Road to QUIC]](https://blog.cloudflare.com/the-road-to-quic/)

**Synchronous**
1. At the same time, at the same frequency.
2. (computing, of communication) Single-threaded; blocking; occurring in the same thread as other computations, thereby preventing those computations from resuming until the communication is complete.
3. (at the same time or frequency): simultaneous, in phase, in synch, in step
4. (single-threaded): blocking, modal, single-threaded

> Synchronous requests block the execution of code which creates "freezing" on the screen and an unresponsive user experience.

**Asynchronous**

1. Not synchronous; occurring at different times. 
2. (computing, of a request or a message) Allowing the client to continue during processing.
3. (computing, communication) Having many actions occurring at a time, in any order, without waiting for each other.
4. (computing) allowing the client to continue during processing of a request or a message.

> Ajax is an asynchronous mechanism for requesting small bits of data over HTTP; the result is sent back when the response is complete, not immediately.

> [Difference Between Synchronous and Asynchronous Messaging](https://peoplesofttutorial.com/difference-between-synchronous-and-asynchronous-messaging/)
