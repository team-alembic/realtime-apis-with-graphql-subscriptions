theme: Poster, 1

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

---

#[fit] The *Anatomy*
## of a GraphQL Subscription

^ The concepts are general, examples are provided using Apollo Client, React, Elixir, Absinthe, Phoenix and Postgres

---

# *1.* The syntax

---

## *Specifies:*

### what to subscribe to
### what to return when triggered

---

# Syntax Example

```
subscription {
  personCreated {
    name
    bio
    avatarUrl
    githubUsername
    location
  }
}
```

---

# Syntax Example

``` [.highlight: 1]
subscription {
  personCreated {
    name
    bio
    avatarUrl
    githubUsername
    location
  }
}
```

^ Tells the server that you want a subscription
^ The remainder is looks like a regular GraphQL query

---

# Syntax Example

``` [.highlight: 2]
subscription {
  personCreated {
    name
    bio
    avatarUrl
    githubUsername
    location
  }
}
```

^ This is the field that you're interested in receiving updates for.
^ It doesn't have to be named like an event
^ It can also accept arguments like any GraphQL field, e.g. person(name: "@freshtonic")

---

# Syntax Example

``` [.highlight: 3-7]
subscription {
  personCreated {
    name
    bio
    avatarUrl
    githubUsername
    location
  }
}
```

^ These are the fields that will be returned when the subscription is triggered.

---

# *2.* The GraphQL schema

---

# *3.* Connecting it together


^ Better title here
^ This is about managing notifications. GraphQL is backend agnostic and does not provide the glue
^ e.g. Postgres notifications, multiple servers behind the load balancer
^ Maybe demo postgres notifications directly?

---

# *4.* Binding to the UI

^ This will be Apollo Client & React specific with Phoenix channels as the transport

---

# Demo time

![zoom filtered](fail-whale-1.png)

^ GraphiQL then FaceQL group sign up
^ Tell people to be nice ands refrain from obsceneties

---

# Demo time

![zoom filtered](fail-whale-2.jpg)

---

# Tour of the FaceQL code

^ Make FaceQL public on Github

---

## Massive 🎩 tip to *Luke Rollans* for building FaceQL

^ Thanks Luke. Put your hand up :)

---

#[fit] Thanks!

- 🏂 James Sadler
- ✉️  james@alembic.com.au
- 🐦 @freshtonic

![right filtered](james-account-photo.jpeg)

---

# Appendix

*Specification working draft*

https://github.com/facebook/graphql/blob/master/rfcs/Subscriptions.md
