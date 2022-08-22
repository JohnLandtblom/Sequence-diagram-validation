
#Sequencediagram user access wiht JWT token
##Mermaid
```
mermaid
sequenceDiagram
  participant Client
  participant Server
  Client->>Server: Send to Server
  Note under Client: Post req. login (email/Pw)
  Server-->>Client: Send to Client
  Note under Server: Credentials correct && user exist? 'unique JWT created' : 'error message'
  Client->>Server: Send to Server
  Note under Client: JWT sparas: cookies || local storage
  Server-->>Client: Send to Client
  Note under Server: Newly created JWT sent back to client
  Client->>Server: Send to Server
  Note under Client: User logged in. Next app visit, sends JWT t oaccess protected route
  Server-->>Client: Send to Client
  Note under Server: Verification
  Client->>Server: Send to Server
  Note under Client: Access :) || Denied :(
  Server-->>Client: Send to Client
  Note under Server: Valid JWT? 'grant access to protected route' : 'error message'

```

