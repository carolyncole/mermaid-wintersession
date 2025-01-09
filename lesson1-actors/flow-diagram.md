The documentation for sequence diagrams is located at [mermaid-js](https://mermaid-js.github.io/mermaid/#/sequenceDiagram)

Who does things in our requirements?
  * The User - A human
  * Our System - A computer
  * The External System - A computer
  * The Curator A human

```mermaid
sequenceDiagram
title  System Requirements Diagram
accTitle: System Requirements Sequence Diagram
accDescr: A sequence diagram that shows what interactions we are expecting the system to have

actor user as User
participant system as Thingamajig Central
participant external as External System
actor curator as Curator

user->>system: Create a thingamajig
Note right of user: this user always makes really nice thingamajigs
system ->> external: Request a new ID
system ->> system: wait
Note over system: it takes 5 minutes
external ->> system: Provide the new ID
system ->> user: Display the ID
Note over curator: they will do something later
```
