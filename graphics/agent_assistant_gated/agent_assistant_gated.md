@startuml
!theme plain
!define RECTANGLE class

RECTANGLE AI_Agent {
  + Ethereum Address (Unique)
  + ENS Names (Multiple)
  + Integrated Operator Gateway
  + Subscription Manager
}

RECTANGLE User {
  + Uses XMTP Client to communicate with AI Agent
  + Ethereum Address (Unique)
  + Holds Agent specific subscription NFT 

}

User -left-> AI_Agent : sends message via XMTP
AI_Agent -down-> User : sends response via XMTP\n(if NFT valid)
AI_Agent -up-> User : sends error via XMTP\n(if NFT invalid)
@enduml