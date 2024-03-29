# window.postMessage()
[`window.postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage)

> The window.postMessage() method safely enables cross-origin communication between Window objects; e.g., between a page and a pop-up that it spawned, or between a page and an iframe embedded within it.

> Normally, scripts on different pages are allowed to access each other if and only if the pages they originate from share the same protocol, port number, and host (also known as the "same-origin policy"). window.postMessage() provides a controlled mechanism to securely circumvent this restriction (if used properly).

> Broadly, one window may obtain a reference to another (e.g., via targetWindow = window.opener), and then dispatch a MessageEvent on it with targetWindow.postMessage(). The receiving window is then free to handle this event as needed. The arguments passed to window.postMessage() (i.e., the “message”) are exposed to the receiving window through the event object.
