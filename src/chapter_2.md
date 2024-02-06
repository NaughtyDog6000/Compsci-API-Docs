# Chapter 2: Signin and Signup

## Signin

```javascript
const myHeaders = new Headers();
myHeaders.append("Content-Type", "application/json; charset=UTF-8");
fetch("https://api.robbiecornock.com/signin", {
  method: "POST",
  mode: "cors",
  headers: myHeaders,
  body: JSON.stringify({ username: "nd6k", password: "letmein!" }),
});
```

Success:

```json
{
  "username": "nd6k",
  "password": "password"
}
```

Fail:

(response code: 400)

```json
{
  "response": "PASSWORD OR USERNAME INCORRECT"
}
```

## Signup
