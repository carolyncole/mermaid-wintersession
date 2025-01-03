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
              'actorBkg': 'lavender',
            }
        } }%%

sequenceDiagram
title Thingamajig System
accTitle: Thingamajig System Requirements Sequence Diagram
accDescr: A sequence diagram that shows what interactions we are expecting the Thingamagic system to have

actor user as User
participant sys as Our System
participant ext as External System
actor curator as Curator

rect lightcyan
  user -) sys: create thingamajig
  sys -->> ext: mint id
  sys --> sys: wait
  note over sys,ext: 5 seconds to mint id
  ext -->> sys: send id
  sys -) user: show id
end

note over curator: approve before publish
rect lightyellow
  loop until thingamajig is approved
    alt thingamajig needs work
      rect mistyrose
        curator -> sys: reject thingamajig
        sys ->> user: update your thingamajig
        rect papayawhip
          user -) sys: update thingamajig
          opt External system needs information
            sys -->> ext: send updated information
          end
        end
      end
    else thingamajig looks fantastic
      rect lightgreen
        curator ->> sys: approve thingamajig
        sys -->> sys: publish thingamajig
      end
    end
  end
end
```
