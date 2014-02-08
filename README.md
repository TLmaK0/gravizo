gravizo
=======

How to include graphviz graphs in github README

Only need to include image markdown tag with the url http://g.gravizo.com/ followed by your description graph in [DOT syntax](http://en.wikipedia.org/wiki/DOT_(graph_description_language)) :

```html
![Alt text](http://g.gravizo.com/
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
![Alt text](http://g.gravizo.com/
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

You can also use normal image HTML tag like this:

```html
<img width='300px' src='http://g.gravizo.com/
digraph G {
  main -> parse -> execute;
  main -> init;
  main -> cleanup;
  execute -> make_string;
  execute -> printf
  init -> make_string;
  main -> printf;
  execute -> compare;
}
'/>
```

<img width='300px' src='http://g.gravizo.com/
digraph G {
  main -> parse -> execute;
  main -> init;
  main -> cleanup;
  execute -> make_string;
  execute -> printf
  init -> make_string;
  main -> printf;
  execute -> compare;
}
'/>

Note: use ' instead of " for the src attribute to avoid other problems.

