# Overview

=======

## Routes

## Auth

```rust
# fn main(){
    println!("Hello world!");
# }
```

```rust
#use std::error::Error;
#use std::collections::HashMap;
#fn main() -> Result<(), Box<dyn Error>> {
    let resp = reqwest::get("https://httpbin.org/ip")
        .await?
        .json::<HashMap<String, String>>()
        .await?;
    println!("{:#?}", resp);
    return ()
#}
```

```javascript,editable
const response = await fetch("api.robbiecornock.com");
console.log(response.body);
```
