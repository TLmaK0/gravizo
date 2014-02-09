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
![Alt text](http://g.gravizo.com/g?
digraph Vehicles {
  node [
    shape = "record"
  ]
  edge [
    arrowtail = "empty"
  ]
  Vehicle [
    label = "{Vehicle|+ model : string%5Cl+ capacity : int%5Cl|+ drive%28%29 : void%5Cl+ canFly%28%29: boolean%5Cl}"
  ]
  Motorcycle[
    label = "{Motorcycle|%5Cl|+ canFly%28%29: boolean%5Cl}"
  ]
  Car [
    label = "{Car|%5Cl|+ canFly%28%29: boolean%5Cl}"
  ]
  Vehicle -> Car [dir=back]
  Vehicle -> Motorcycle [dir=back]
}
)
```

![Alt text](http://g.gravizo.com/g?
digraph Vehicles {
  node [
    shape = "record"
  ]
  edge [
    arrowtail = "empty"
  ]
  Vehicle [
    label = "{Vehicle|+ model : string%5Cl+ capacity : int%5Cl|+ drive%28%29 : void%5Cl+ canFly%28%29: boolean%5Cl}"
  ]
  Motorcycle[
    label = "{Motorcycle|%5Cl|+ canFly%28%29: boolean%5Cl}"
  ]
  Car [
    label = "{Car|%5Cl|+ canFly%28%29: boolean%5Cl}"
  ]
  Vehicle -> Car [dir=back]
  Vehicle -> Motorcycle [dir=back]
}
)


