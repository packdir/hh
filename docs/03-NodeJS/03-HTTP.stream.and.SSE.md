
SSE is in fact a form of HTTP streaming. It is just an HTTP response with MIME type of "text/event-stream" and it sends plain text messages terminated with double newlines.

如果不是使用 HTTP/2，在一个浏览器上打开 SSE 的数量有限制，也就是说tab数量不能超过6个。

SSE API 看这个文档：[Using server-sent events](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events)




