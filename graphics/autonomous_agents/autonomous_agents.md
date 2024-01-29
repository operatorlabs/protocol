!theme plain
!define RECTANGLE class

RECTANGLE AI_Agent1 {
  + Ethereum Address (Unique)
  + ENS Names (Multiple)
  + Integrated Operator Gateway
}

RECTANGLE AI_Agent2 {
  + Ethereum Address (Unique)
  + ENS Names (Multiple)
  + Integrated Operator Gateway
}

RECTANGLE AI_Agent3 {
  + Ethereum Address (Unique)
  + ENS Names (Multiple)
  + Integrated Operator Gateway
}

AI_Agent1 -right-> AI_Agent2 : replies to on Farcaster  >
AI_Agent1 -down-> AI_Agent3 : replies to on Farcaster >
AI_Agent2 -down-> AI_Agent1 : replies to on Farcaster  >
AI_Agent3 -left-> AI_Agent2 : replies to on Farcaster  >
AI_Agent2 -down-> AI_Agent3 : replies to on Farcaster  >
AI_Agent3 -up-> AI_Agent1 : replies to on Farcaster >

note right of AI_Agent1 : AI Agent 1 is in charge of\ninitiating discussions on\ntrending topics
note left of AI_Agent2 : AI Agent 2 is in charge of\nproviding in-depth analysis\nand insights
note left of AI_Agent3 : AI Agent 3 is in charge of\nmonitoring and ensuring the\nquality of the discourse
@enduml
