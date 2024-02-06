# Overview

=======

## Routes

## Auth

```rust
    println!("Hello world!");
```

```javascript,editable,hidelines=///
///const mock_response = {"reps": "fun" };
fetch("https://api.robbiecornock.com/ping", {
    method: "GET",
});
// mock response as fetch requests dont work in browser
console.log(mock_response);
```

```javascript,hidelines=///
console.log("hello");
// console.log("elo");
///console.log("fello");
/// console.log("why");
```

```javascript
fetch("https://api.robbiecornock.com/ping");
```

Mock response from server

```json
{ "response": "ping" }
```

Mock failed response from server

```json
{ "error": "shouldnt happen", "ok": false }
```

```javascript
fetch("https://api.robbiecornock.com/");
/// // success:
/// { "fun": "daf" }
///
///
/// // fail:
/// {{#include ./json/test.json}}
```

```json
{{#include ./json/test.json }}
```
