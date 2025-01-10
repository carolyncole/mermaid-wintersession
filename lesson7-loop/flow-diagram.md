The documentation for looping is located at [mermaid-js/loop](https://mermaid.js.org/syntax/sequenceDiagram.html#loops)

add requirement 3 to our diagram “A Curator needs to approve the thingamajig for it to show up publicly in the system”

1. Add an alt for the Curator approving or rejecting a thingamajig
   ```
   alt ...
     curator -> sys: ...
   else ...
     curator -> sys: ...
   end
   ```
1. Add loop to show the above process happening multiple times
   ```
   loop ...
     ...
   end
   ```
1. Bonus: Style the new workflow



```mermaid
%%{init: { 'theme': 'forest',
            'themeVariables': {
              'actorBorder': 'blue',
              'actorBkg': 'pink'
            }
        } }%%

sequenceDiagram
title  System Requirements Diagram
accTitle: System Requirements Sequence Diagram

actor user as User
participant sys as Our System
participant ext as External System
actor curator as Curator
note over curator: Will be approving things later

rect lightblue
  user -) sys: create thingamajig
  sys -->> ext: mint id
  sys --> sys: wait
  note over sys,ext: 5 seconds to mint id
  ext -->> sys: send id
  sys -) user: show id
end

rect lightgreen
  user -) sys: update thingamajig
  opt External system needs information
    sys -->> ext: send updated information
  end
end
```
