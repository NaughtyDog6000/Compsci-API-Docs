# Overview

=======

## API Response Guide

The response from the API should always come in the forms below[^note], with the apropriate status code to if the request was successful or a failure.

**Success:**

status code: 200

```json
{
  "response": "message",
  "data": {
    "...": "...."
  }
}
```

**Fail:**

status code: 400, 401, 4XX

```json
{
  "response": "something went wrong!",
  "data": {
    "...": "...."
  }
}
```

## http request prerequisites

### making a request

To get a response from the api in Javascript you make a fetch request.

```javascript
const response = await fetch("https://api.robbiecornock.com/ping");
```

```javascript
// get the json object from the response
const json = await response.json();

// and then print the json as a string
console.log(JSON.stringify(json));
```

### request methods

Depending on how you are interacting with the api, different request methods are used,
the ones that the API currently makes use of are:

| method |                                                                   description                                                                   |
| :----: | :---------------------------------------------------------------------------------------------------------------------------------------------: |
|  GET   |          for getting resources from the server, you cannot send a body on a get request, only auth headers and query string parameters          |
|  POST  | for sending data to the api and expecting a response, e.g. sending the username and password and getting back an auth token from a signin route |

Example of a GET request:

```javascript
fetch("https://api.robbiecornock.com/", {
  method: "GET",
});
```

OR (as the default method is GET)

```javascript
fetch("https://api.robbiecornock.com/");
```

Response from API:

```json
{
  "Time": 1707224771,
  "method_sent": "GET",
  "response": "HELLO"
}
```

Example of a POST request:

```javascript
fetch("https://api.robbiecornock.com/", {
  method: "POST",
});
```

Response from API:

```json
{
  "Time": 1707224976,
  "method_sent": "POST",
  "response": "HELLO"
}
```

### cors

if you ran the previous examples in a web browser, it wouldnt run and with some weird error.

This is because when sending requests to the api in a browser from another website,
the browser will only allow the request to be used if both the server and the client have the correct cors policy,
the api has the most permissive cors policy and (_shouldn't be_) isnt an issue.
to tell the browser that making a request to the api is allowed, you pass the cors mode into the configuration of the fetch request.

```javascript
// wont work in a website's JS
fetch("https://api.robbiecornock.com", {
  method: "POST",
});
```

```javascript
// will work in a website's JS
fetch("https://api.robbiecornock.com", {
  method: "POST",
  mode: "cors",
});
```

### sending data

To send json data to the API you run `JSON.stringify()`, on the object and then put it in the `body` parameter of the fetch request.

```javascript
fetch("https://api.robbiecornock.com/check_user", {
  method: "POST",
  mode: "cors",
  body: JSON.stringify({ username: "nd6k" }),
});
```

## Auth

[^note]: the example routes ("/" and "/ping") dont follow the format for simplicity.
