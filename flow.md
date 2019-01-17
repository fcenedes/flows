<details> 
<summary></summary>
custom_markflo
  digraph G {
    size ="4,4";
    "Ingest Data" [shape=box];
    "Ingest Data" -> parse [weight=8];
    parse -> execute;
    "Ingest Data" -> init [style=dotted];
    "Ingest Data" -> cleanup;
    execute -> { make_string; printf};
    init -> make_string;
    edge [color=red];
    "Ingest Data" -> printf [style=bold,label="100 times"];
    make_string [label="make a string"];
    node [shape=box,style=filled,color=".7 .3 1.0"];
    execute -> compare;
  }
custom_markflo
</details>
