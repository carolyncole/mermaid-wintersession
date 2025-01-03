The documentation for sequence diagrams is located at [mermaid-js](https://mermaid-js.github.io/mermaid/#/sequenceDiagram)

Who does things in our requirements?
  * The User - A human
  * Our System - A computer
  * The External System - A computer
  * The Curator A human

```mermaid
sequenceDiagram
actor user as User
participant sys as Our System

sys -->> user: Advertise thingamajig
alt User wants <br> a thingamajig
  user ->> sys: Click Link
else
  sys -->> user: Advertise whatsits   
end
```
