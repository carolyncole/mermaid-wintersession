# Cheat Sheet

Here is a cheat sheet of useful items for a mermaid flow diagram.  Full documentation can be found at [Mermaid.js](https://mermaid-js.github.io/mermaid/#/sequenceDiagram)

## participants
  participant [name]: [display name] **OR** actor [name]: [display name] (an actor displays a stick figure and a participant displays a box

  
  ```mermaid
  sequenceDiagram
  %%{init: { 'sequence': {'mirrorActors':false} } }%%
    title Actor Diagram
    actor you as You
    participant store as Pet store
  ```

## Alternate
 alt [choice]
    ...
 else [another choice]
    ...
 else [yet another choice]
    ...
 end

  ```mermaid
  sequenceDiagram
    title Alternate Example Diagram
    actor you as You
    participant store as Pet store
    alt you love cats?
      you->>store: Buy a cat
    else you love fish
      you->>store: Buy a fish
    else you do not want a pet
      you->>you: stay home
    end  
  ```

## Loop
 loop [until when]
   ...
 end

  ```mermaid
  sequenceDiagram
      title Loop Example Diagram
      loop until you are full
        spoon->>mouth: Insert food on spoon
      end
  ```

## Theming
  Theming Mermaid can be done in a variety of ways.  See full documentation at [Mermaid.js](https://mermaid-js.github.io/mermaid/#/theming)

### Rectangles
   * rect rgb(255, 255, 240)
   * rect rgb(240, 255, 255)
   * rect rgb(255, 240, 255)
  ```mermaid
  sequenceDiagram
    title  Highlight Rectangles Example Diagram
    rect rgb(240, 255, 255) 
      A->>B: I like Green
    end
    rect rgb(255, 240, 255)
      B->>A: I like Pink
      rect rgb(255, 255, 240)
        C->>C: Yellow is best
      end
    end
  ```

### Notes
   * note [left|right|over] of [the particiapnt]: <note>
  ```mermaid
  sequenceDiagram
    title  Showing Notes Example Diagram
    participant spoon AS #129348;
    participant mouth as #128068;
    loop until you are full
     note over spoon,mouth: Open wide
      spoon->>mouth: Insert food on spoon
    end
  ```

### Overall Theming
  * Overall themes can be applied like a color theme: forest, dark, neutral
  ```mermaid
  %%{init: { 'theme': 'forest',
             'sequence': {'useMaxWidth':false, 
                          'mirrorActors':false,   
                          'diagramMarginX': 10
                          } 
            } 
  }%%
  sequenceDiagram
    title Forest Theme Example Diagram
    actor you as You
    participant store as Pet store
    alt you love cats?
      you->>store: Buy a cat
    else you love fish
      you->>store: Buy a fish
    else you do not want a pet
      you->>you: stay home
    end  
  ```

