# Coderunner-C-Prototypes
Specialized prototypes, examples, and documentation for custom C programming tasks in the Moodle Coderunner plugin.

## Introduction

Programming exercises play a crucial role in computer science education, offering students practical opportunities
to apply theoretical concepts. While the Moodle Coderunner plugin supports a wide range of question types 
(including Parsons Problem and Fill-the-Gaps tasks for **Python**), it does
not natively accommodate Parsons Problems or Fill-the-Gaps tasks for the **C programming language**. 


However, by developing and implementing custom prototypes, it is possible to integrate these exercise
formats effectively. This repository provides two prototypes for Parsons Problems
and two prototypes for Fill-the-Gaps tasks, specifically tailored 
for use with Coderunner in C.

## Why two prototypes for each question type?

The structure and evaluation of C programming tasks vary significantly depending on the level of code students are expected to produce.  
As illustrated in the diagram above, different prototypes are necessary for handling:

- **Code snippets**, which focus on small isolated code fragments such as conditional statements or loops,
- **Standalone functions**, where a complete function with input parameters and return values must be implemented,
- **Complete programs**, including the `main()` function and full input/output management.

Ideally, each exercise format — Parsons Problems and Fill-the-Gaps — would require three distinct prototypes to fully cover these different structures.  
However, at present, this repository provides two prototypes for each type, covering code snippets and functions (Parsons Problem) and snippets and complete programs (Fill-the-Gaps).  

Each of these developed prototypes has its own template and grading logic adapted to the structure of the expected student submissions.  
For example, evaluating a snippet typically involves inserting the student's code into a controlled template and testing specific outputs.  
In contrast, testing a full program requires compiling and running an independently executable source file, while functions must be validated based on their defined interface and behaviour.

The solid lines in the diagram represent prototypes already developed and available in this repository.  
Dashed lines indicate intended future prototypes that have not yet been implemented.  
They highlight potential extensions, particularly for Parsons Problems involving complete programs and for Fill-the-Gaps tasks requiring standalone functions, where additional complexity in evaluation would need to be addressed.


```mermaid
flowchart TD
    %% Main Node
    Coderunner((Coderunner<br/>Custom Question Types in this Repo))

    %% Subcategories
    ParsonsProblem((Parsons Problem))
    Gapfiller((Gapfiller))

    %% Parsons Problem Nodes
    subgraph ParsonsProblemGroup [ ]
        Snippet1((Snippet))
        Function1((Function))
        Programm1((Program))
    end

    %% Gapfiller Nodes
    subgraph GapfillerGroup [ ]
        Snippet2((Snippet))
        Function2((Function))
        Programm2((Program))
    end

    %% Hierarchical structure
    Coderunner --> ParsonsProblem
    Coderunner --> Gapfiller

    ParsonsProblem --> Snippet1
    ParsonsProblem --> Function1
    ParsonsProblem -.-> Programm1

    Gapfiller --> Snippet2
    Gapfiller -.-> Function2
    Gapfiller --> Programm2

    %% Styles for Main Nodes
    style Coderunner stroke-width:5px,fill:#1e1e1e,stroke:#666,color:#ffffff
    style ParsonsProblem stroke-width:4px,fill:#1e1e1e,stroke:#666,color:#ffffff
    style Gapfiller stroke-width:4px,fill:#1e1e1e,stroke:#666,color:#ffffff

    %% Styles for Exercise Nodes
    style Snippet1 stroke-width:2px,fill:#2b2b2b,stroke:#555,color:#ffffff
    style Function1 stroke-width:2px,fill:#2b2b2b,stroke:#555,color:#ffffff
    style Programm1 stroke-width:2px,fill:#2b2b2b,stroke:#555,color:#ffffff

    style Snippet2 stroke-width:2px,fill:#2b2b2b,stroke:#555,color:#ffffff
    style Function2 stroke-width:2px,fill:#2b2b2b,stroke:#555,color:#ffffff
    style Programm2 stroke-width:2px,fill:#2b2b2b,stroke:#555,color:#ffffff

    %% Styles for faded/dashed nodes
    style Programm1 fill:#333,stroke:#666,color:#ffffff
    style Function2 fill:#333,stroke:#666,color:#ffffff

    %% Link Styles
    linkStyle 0 stroke-width:3px
    linkStyle 1 stroke-width:3px
    linkStyle 2 stroke-width:3px
    linkStyle 3 stroke-width:3px
    linkStyle 4 stroke-width:1px,stroke-dasharray: 3,3
    linkStyle 5 stroke-width:3px
    linkStyle 6 stroke-width:1px,stroke-dasharray: 3,3
    linkStyle 7 stroke-width:3px

    %% Subgraph styles (optional background for groups)
    classDef ParsonsProblemGroupStyle fill:#666,stroke:#444,stroke-width:2px;
    classDef GapfillerGroupStyle fill:#666,stroke:#444,stroke-width:2px;
    class ParsonsProblemGroup ParsonsProblemGroupStyle;
    class GapfillerGroup GapfillerGroupStyle;

```
