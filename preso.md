# GraphQL Subscriptions

# For _**realtime**_ apps

![left filtered](graphql-logo.png)


---


## GraphQL
## Subscriptions Are
#[fit] _**Awesome**_

---

## But first some
#[fit] background

![filtered](rainbow.jpg)

---

## Before GraphQL was
#[fit] REST

---

### REST has no story for
#[fit] *live data*

---

![fit](not-moving.gif)

---

#[fit] *Content-Type*?

---

## Had to step
#[fit] outside
## REST

---

![filtered fit](cold.jpg)

---

![filtered fit](cold.jpg)

## *It's cold and miserable outside*

---

![filtered right](rube.jpg)

#[fit] _Ad hoc_
#[fit] _solutions_

---

#[fit] `fetch()`

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

#[fit] Websockets

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

---

#[fit] *Anatomy*
## of a GraphQL Subscription

---

#[fit] Thanks!

- 🏂 James Sadler
- ✉️  james@alembic.com.au
- 🐦 @freshtonic

![right filtered](james-account-photo.jpeg)

