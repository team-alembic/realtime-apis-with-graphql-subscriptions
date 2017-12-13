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
#[fit] *REST*

---

![right filtered](roy.jpg)

#[fit] *Re*presentational
#[fit] *S*tate
#[fit] *T*ransfer

*Roy Fielding* invented it for his PhD thesis in 2000

^ not a fun guy

---

![left filtered](noel.jpg)

#[fit] Not to
#[fit] be confused
#[fit] with this guy

*Noel Fielding:* surreal comedian

^ a fun guy

---

![left zoom filtered](frozen-clock.jpg)

#[fit] REST has no story for
#[fit] *live data*

---

#[fit] *Content-Type*?

---

## Must step
#[fit] *outside*
## of REST

---

![filtered fit](cold.jpg)

---

![filtered fit](cold.jpg)

## *It's cold outside*

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

# Appendix

*Specification working draft*

https://github.com/facebook/graphql/blob/master/rfcs/Subscriptions.md

---

#[fit] Thanks!

- 🏂 James Sadler
- ✉️  james@alembic.com.au
- 🐦 @freshtonic

\* apologies to Roy Fielding

![right filtered](james-account-photo.jpeg)

