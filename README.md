gravizo
=======

How to include graphviz graphs in github README.md

Only need to include image markdown tag with the url [http://g.gravizo.com/g?](http://www.gravizo.com) followed by your description graph in [DOT syntax](http://en.wikipedia.org/wiki/DOT_(graph_description_language)) :

```html
![Alt text](http://g.gravizo.com/g?
  digraph G {
    aize ="4,4";
    main [shape=box];
    main -> parse [weight=8];
    parse -> execute;
    main -> init [style=dotted];
    main -> cleanup;
    execute -> { make_string; printf}
    init -> make_string;
    edge [color=red];
    main -> printf [style=bold,label="100 times"];
    make_string [label="make a string"];
    node [shape=box,style=filled,color=".7 .3 1.0"];
    execute -> compare;
  }
)
```
![Alt text](http://g.gravizo.com/g?
  digraph G {
    aize ="4,4";
    main [shape=box];
    main -> parse [weight=8];
    parse -> execute;
    main -> init [style=dotted];
    main -> cleanup;
    execute -> { make_string; printf}
    init -> make_string;
    edge [color=red];
    main -> printf [style=bold,label="100 times"];
    make_string [label="make a string"];
    node [shape=box,style=filled,color=".7 .3 1.0"];
    execute -> compare;
  }
)

This allow to include your graphs in the README, and still redeable in normal text editor.

Because limitations of the url you can use in markdown, you should use the <a target='_blank' href='http://www.gravizor.com/#converter'>Converter</a>  to see more complex graphs:

```
/**
*@hidden
*@opt nodefontcolor "blue"
*/
class UMLNoteOptions{}
/**
*Structural Things
*@opt commentname
*@note Notes can
*be extended to
*span multiple lines
*/
class Structural{}
/**
*spelling.java
*@opt shape component
*@opt commentname
*@note Component
*/
class Component extends Structural{}
/** @opt shape node */
class Node extends Structural{}
/**
*Chain of
*responsibility
*@opt shape collaboration
*@opt commentname
*@note Collaboration
*/
class Collaboration extends Structural{}
/**
*Place order
*@opt shape usecase
*@opt commentname
*@note Use Case
*/
class UseCase extends Structural{}
/**
*Business rules
*@opt shape package
*@opt commentname
*@note Package
*/
class Package{}
/**
*@opt all
*@note Class
*/
class Counter extends Structural {
static public int counter;
public int getCounter%28%29;
}
/**
*@opt shape activeclass
*@opt all
*@note Active Class
*/
class RunningCounter extends Counter{}
)
```

![Alt text](http://g.gravizo.com/g?
/**
*@hidden
*@opt nodefontcolor "blue"
*/
class UMLNoteOptions{}
/**
*Structural Things
*@opt commentname
*@note Notes can
*be extended to
*span multiple lines
*/
class Structural{}
/**
*spelling.java
*@opt shape component
*@opt commentname
*@note Component
*/
class Component extends Structural{}
/** @opt shape node */
class Node extends Structural{}
/**
*Chain of
*responsibility
*@opt shape collaboration
*@opt commentname
*@note Collaboration
*/
class Collaboration extends Structural{}
/**
*Place order
*@opt shape usecase
*@opt commentname
*@note Use Case
*/
class UseCase extends Structural{}
/**
*Business rules
*@opt shape package
*@opt commentname
*@note Package
*/
class Package{}
/**
*@opt all
*@note Class
*/
class Counter extends Structural {
static public int counter;
public int getCounter%28%29;
}
/**
*@opt shape activeclass
*@opt all
*@note Active Class
*/
class RunningCounter extends Counter{}
)


