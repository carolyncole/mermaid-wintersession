The documentation for sequence diagrams is located at [mermaid-js](https://mermaid-js.github.io/mermaid/#/sequenceDiagram)

Who does things in our requirements?
1. add an actor for the User
1. add a participant for Our System
1. add a participant for the External System
1. add an actor for the curator

```mermaid
sequenceDiagram

actor user as User
participant sys as Our System
participant ext as External System
actor curator as Curator
```
