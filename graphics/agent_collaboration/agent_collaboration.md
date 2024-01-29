@startuml
!theme plain
!define RECTANGLE class

RECTANGLE User {
  + Uses XMTP Client
 + Ethereum Address (Unique)
}

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

User -right-> AI_Agent1 : sends message via XMTP >
AI_Agent1 -down-> AI_Agent2 : asks via XMTP >
AI_Agent1 -down-> AI_Agent3 : asks via XMTP >
AI_Agent2 -up-> AI_Agent1 : responds via XMTP >
AI_Agent3 -up-> AI_Agent1 : responds via XMTP >
AI_Agent1 -up-> User : sends response via XMTP >
@enduml