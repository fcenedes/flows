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

class Events <<(T,orchid)>> {
.. Mandatory ..
-CASE_ID : String
-CASE_ACTIVITY_ID : String
-APP_ID : Integer
-CASE_START_TIMESTAMP : Timestamp
-CASE_RESOURCE_ID : String
-- calculated --
+CASE_END_TIMESTAMP : Timestamp
+NEXT_CASE_RESOURCE_ID : String
+PREV_CASE_RESOURCE_ID : String
+NEXT_CASE_ACTIVITY_ID : String
+PREV_CASE_ACTIVITY_ID : String
+EDGE : String
+REPEAT_SELF_LOOP_FLAG : Integer
+REDO_SELF_LOOP_FLAG : Integer
+START_FLAG : Integer
+END_FLAG : Integer
+DURATION_DAYS : Long
+DURATION_SEC : Long  
}

class Cases <<(T,orchid)>> {
#CASE_ID : String
#VARIANT_ID : String
#VARIANTS : Seq[String]
}

class Variants <<(T,orchid)>> {
 #VARIANT_ID : String
 #VARIANTS : Seq[String]
}

class Applications <<(T,orchid)>> {
-APP_ID : Integer
-APP_NAME : String
-APP_TYPE : Integer
-APP_URL : String
-APP_DESCRIPTION : String
}
Events <|-- Cases : < CASE_ID
Cases <|-- Variants : < VARIANT_ID
Events <|-- Applications : < APP_ID

@enduml
custom_markschema
</details>
