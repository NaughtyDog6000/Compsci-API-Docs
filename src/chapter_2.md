# Chapter 2: Basic Routes & Setup

## Javascipt Exapmle for fetching from the API

```javascript,editable
    fetch("https://api.robbiecornock.com");
    # console.log({
    #    "response": "HELLO",
    #    "method_sent": "GET",
    #    "Time": Date.now()
    # })
```

## HTTP Methods

**GET** requests are used to fetch some info where no parameters / data is needed to be sent
(in Javascript the method is optional for get requests)

```javascript,editable
    fetch("https://api.robbiecornock.com/ping", {
        method: "GET",
    });
    # console.log({
        "response": "pong GET"
    # })
```

**POST** requests are commonly used for requests which have a body and need to upload some data, this is an example for how you would create a post request

```javascript,editable
    fetch("https://api.robbiecornock.com/ping", {
        method: "POST",
    });
    # console.log({
        "response": "pong GET"
    # })
```
