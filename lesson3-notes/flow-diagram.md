The documentation for sequence diagram notes is located at [mermaid-js/notes](https://mermaid.js.org/syntax/sequenceDiagram.html#notes)

Noting our wait time is typically 5 seconds
Noting our curator will be doing things later


```mermaid

sequenceDiagram
title  System Requirements Diagram
accTitle: System Requirements Sequence Diagram

actor user as User
participant sys as Our System
participant ext as External System
actor curator as Curator

note over user: ...

user -) sys: create thingamajig
sys -->> ext: mint id
sys --> sys: wait
ext -->> sys: send id
sys -) user: show id

```