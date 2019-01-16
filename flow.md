<details> 
<summary></summary>
custom_markflo
  digraph G {
    size ="4,4";
    Start [shape=box];
    Start -> parse [weight=8];
    parse -> execute;
    Start -> init [style=dotted];
    Start -> cleanup;
    execute -> { make_string; printf};
    init -> make_string;
    edge [color=red];
    Start -> printf [style=bold,label="100 times"];
    make_string [label="make a string"];
    node [shape=box,style=filled,color=".7 .3 1.0"];
    execute -> compare;
  }
custom_markflo
</details>
