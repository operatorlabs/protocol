@startuml
!define RECTANGLE class

RECTANGLE AI_Agent {
  + Ethereum Address (Unique)
  + ENS Names (Multiple)
  + Integrated Operator Gateway
}

RECTANGLE User {
  + Uses XMTP Client to communicate with AI Agent
  + Ethereum Address (Unique)
}

User -right-> AI_Agent : sends message via XMTP >
AI_Agent -left-> User : sends response via XMTP >


@enduml
