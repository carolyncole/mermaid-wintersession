The documentation for sequence diagram notes is located at [mermaid-js/notes](https://mermaid.js.org/syntax/sequenceDiagram.html#notes)

A User updates the Thingamajig: Update the External System if the change is something they are interested

1. Add the User Updating the Metadata in Our System
1. Add a opt to show Our System Updating the External 


```mermaid

sequenceDiagram
title  System Requirements Diagram
accTitle: System Requirements Sequence Diagram

actor user as User
participant sys as Our System
participant ext as External System
actor curator as Curator
note over curator: Will be approving things later

user -) sys: create thingamajig
sys -->> ext: mint id
sys --> sys: wait
note over sys,ext: 5 seconds to mint id
ext -->> sys: send id
sys -) user: show id
user -) sys: update thingamajig
opt External system needs information
  sys -->> ext: send updated information
end
```
