

- publicise Domain guest wifi details at start of talk

- transport agnostic, like all of GraphQL
- HTTP/2

- subscriptions will become the lingua franca for live data on the web
- 	- will work with server middleware for logging and monitoring
- 	- will come with bindings or your client side JS framework
- 	- no more ad hoc
- 	- are general enough to capture any event semantics

- Absinthe triggers are convenience shortcuts
- Will not work when multiple nodes behind a load balancer
- work around this with postgres notifications



---

# Polling with

# *`fetch()`*

^ This is RESTful

---

```javascript
function getLatestData() {
  fetch("https://my.api/data.json", {method: "get"}).then((response) => {
    updateUserInterface(response.json())
  });
}

setInterval(getLatestData, 5000)
```
---

# Websockets

---

```javascript
let connection = new WebSocket("ws://my.api/live")

function dispatch(data) {
  // figure out what to update based on the message payload
  // updateUserInterface(data)
}

connection.onmessage = function (e) {
  dispatch(e.data);
};
```
