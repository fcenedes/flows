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

<details> 
<summary></summary>
custom_markschema        
@startuml


class Events {
   {field} CASE_ID : String
   ACTIVITY_ID : String
   APP_ID : Integer
}

class Cases {
  {field} CASE_ID : String
   VARIANT_ID : String
}

class Variants {
   {field} VARIANT_ID : String
   Graph : Seq[String]
}

class Sources {
   {field} APP_ID : Integer
   APP_NAME : String
   APP_TYPE : Integer
}


Events <|-- Cases
Cases *-- Variants
Events o-- "4" Sources

@enduml
custom_markschema
</details>
