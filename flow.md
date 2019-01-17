<details> 
<summary></summary>
custom_markflo
  digraph G {
    size ="4,4";
    "Ingest Data" [shape=box];
    "Ingest Data" -> parse [weight=8];
    parse -> Cleanup ;
    Cleanup -> Normalise;
    Normalise -> { process_miner; printf};
    process_miner [label="make a string"];
    node [shape=box,style=filled,color=".7 .3 1.0"];
  }
custom_markflo
</details>
