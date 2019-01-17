<details> 
<summary></summary>
custom_markflo
  digraph G {
    size ="4,4";
    "Ingest Data" [shape=box];
    "Ingest Data" -> parse [weight=8];
    parse -> Cleanup;
    Cleanup -> Normalise;
    Normalise -> { process_miner; store};
    process_miner [label="Process Mining"];
    store [shape=box,style=filled,color=".7 .3 1.0", label="temp storage"];
  }
custom_markflo
</details>
