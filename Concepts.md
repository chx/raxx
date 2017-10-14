```
| Client |                  | Server |
|        | --- request  --> |        |
|        | <-- response --- |        |
|        |                  |        |

| Client |                                                        | Server |
|        | --> < tail / body / body / body / head(request) >  --> |        |
|        | <-- < head(response) / body / body / body / tail > <-- |        |
|        |                                                        |        |

```

```
--------------------------------------------------------------------    
POST / HTTP/1.1         %Raxx.Request{body: true, method: :POST ...}
host: example.com

--------------------------------------------------------------------    
{                       %Raxx.Body{data: "{\r\n  \"name\": ..."}
  "name": "betty",
--------------------------------------------------------------------    
  "age": 8              %Raxx.Body{data: "  \"age\": 8\r\n ..."}
}
--------------------------------------------------------------------    
--------------------------------------------------------------------    
                        ^^ %Raxx.Tail{trailers: []} ^^
```


```
--> < tail / body / body / body / head(request) > -->
<-- < head(response) / body / body / body / tail > <--
```

```
simple

           request   >
Client ============================================ Server
                                   <   response
```

```
streamed

           tail | body(1+) | head(request)   >
Client ============================================ Server
           <   head(response) | body(1+) | tail
```
## Why use Raxx

Raxx provides an extremely simple interface.
 on the battle tested Rack project from Ruby

Raxx provides a pure functional interface for all HTTP usecases

- Unary request/response exchanges.
- Long poll responses.
- Client streamed requests.
- Server streamed responses.
- Bidirectional streaming.

Raxx provides solid building blocks, such as Raxx.Router
