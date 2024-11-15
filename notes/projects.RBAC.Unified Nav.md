---
id: t2hw6uxxi6g03f4n0hqbopo
title: Unified Nav
desc: ''
updated: 1729766334137
created: 1729687315749
---
### Panda calls the rules engine.

``` mermaid
sequenceDiagram
    Client->>+panda: 
    panda->>+PPAA/DCS: Request UI Capabilities
    par Get access data
        PPAA/DCS->>+RBAC: Get UAP
        PPAA/DCS->>+LES: Get License Info
        PPAA/DCS->>+Products: Get product user access controls
        RBAC-->>-PPAA/DCS: UAP
        LES-->>-PPAA/DCS: Subscriptions
        Products-->>-PPAA/DCS: Product user access controls
    end
    PPAA/DCS-->>-panda: UI Capabilities
    panda->>+Rules: Get allowed UI Elements 
    Rules-->>-panda: Allowed UI elements
    panda-->>-Client: Allowed UI elements 
```

#### Architecture

``` mermaid
architecture-beta
    group api(cloud)[iPIMS]

    
```

### PPAA/DCS/Data Collection service calls the rules engine as part of the request.

``` mermaid
sequenceDiagram
    Client->>+panda: 
    panda->>+PPAA/DCS: Request UI Capabilities
    par Get access data
        PPAA/DCS->>+RBAC: Get UAP
        PPAA/DCS->>+LES: Get License Info
        PPAA/DCS->>+Products: Get product user access controls
        RBAC-->>-PPAA/DCS: UAP
        LES-->>-PPAA/DCS: Subscriptions
        Products-->>-PPAA/DCS: Product user access controls
    end
    PPAA/DCS->>+Rules: Get allowed UI Elements 
    Rules-->>-PPAA/DCS: Allowed UI elements
    PPAA/DCS-->>-panda: UI Capabilities
    panda-->>-Client: Allowed UI elements 
```

#### Architecture
