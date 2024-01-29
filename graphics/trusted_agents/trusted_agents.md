@startuml  
!theme plain    
!define RECTANGLE class    
  
RECTANGLE SmartContract {  
  + Ethereum Address (Unique)  
  + Holds some balance of tokens  
  + Requests Output from a Specific Agent Type  
}  
  
RECTANGLE AgentCoordinator {  
  + Coordinates Task Distribution  
  + Collects & Validates Responses  
  + Handles Errors and Retries  
}  
  
RECTANGLE AgentTypeRegistry {  
  + IPFS Address (Unique)  
  + Contains Agent Markup Language (AML) Files  
  + Provides Agent Type Definitions  
}  
  
RECTANGLE AI_Agent1 {  
  + Ethereum Address (Unique)  
  + Stakes Tokens  
  + Matches Requested Agent Type  
}  
  
RECTANGLE AI_Agent2 {  
  + Ethereum Address (Unique)  
  + Stakes Tokens  
  + Matches Requested Agent Type  
}  
  
RECTANGLE AI_Agent3 {  
  + Ethereum Address (Unique)  
  + Stakes Tokens  
  + Matches Requested Agent Type  
}  
  
RECTANGLE ConsensusMechanism {  
  + Validates Agent Responses  
  + Manages Stakes and Slashes  
}  
  
RECTANGLE LLMEvaluator {  
  + i.e. GPT-4 on Ritual Infernet
  + Provides Trustless Access to LLMs  
}  
  
SmartContract -down-> AgentCoordinator : Requests Output from a Specific Agent Type  
AgentCoordinator -left-> AgentTypeRegistry : Retrieves Agent Type Definition  
AgentTypeRegistry -down-> AgentCoordinator : Returns Agent Type Definition  
AgentCoordinator -right-> AI_Agent1 : Delegates Task  
AgentCoordinator -down-> AI_Agent2 : Delegates Task  
AgentCoordinator -left-> AI_Agent3 : Delegates Task  
AI_Agent1 -right-> ConsensusMechanism : Submits Response  
AI_Agent2 -down-> ConsensusMechanism : Submits Response  
AI_Agent3 -left-> ConsensusMechanism : Submits Response  
ConsensusMechanism -right-> LLMEvaluator : Verifies Responses using LLMs  
LLMEvaluator -up-> ConsensusMechanism : Returns Verification Results  
ConsensusMechanism -up-> AgentCoordinator : Confirms Valid Response  
AgentCoordinator -up-> SmartContract : Returns Trusted Response  
@enduml  
