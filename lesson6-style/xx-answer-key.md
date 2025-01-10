The documentation for Themes is located at [mermaid-js/themes](https://mermaid.js.org/config/theming.html#sequence-diagram-variables)

Style the diagram for visibility of the two flows

1. Add an overall theme “forest” or “neutral”
1. Add theme variables to change the “actorBorder” and “actorBkg” to a colors of your choosing


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
