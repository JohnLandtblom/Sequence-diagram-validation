
#Sequencediagram user access wiht JWT token

``` mermaid
sequenceDiagram
  participant Client
  participant Server
  participant Client
  participant Server
  participant Client
  participant Server
  participant Client
  participant Server
  Client->>Server: Send to Server
  Note over Client: Post req. login (email/Pw)
  Server-->>Client: Send to Client
  Note over Server: Credentials correct && user exist? 'unique JWT created' : 'error message'
  Client->>Server: Send to Server
  Note over Client: JWT sparas: cookies || local storage
  Server-->>Client: Send to Client
  Note over Server: Newly created JWT sent back to client
  Client->>Server: Send to Server
  Note over Client: User logged in. Next app visit, sends JWT t oaccess protected route
  Server-->>Client: Send to Client
  Note over Server: Verification
  Client->>Server: Send to Server
  Note over Client: Access :) || Denied :(
  Server-->>Client: Send to Client
  Note over Server: Valid JWT? 'grant access to protected route' : 'error message'

```

