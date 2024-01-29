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
  + Integrated Operator Gateway
  + Stakes Tokens  
  + Matches Requested Agent Type  
}  
  
RECTANGLE AI_Agent2 {  
  + Ethereum Address (Unique)  
  + Integrated Operator Gateway
  + Stakes Tokens  
  + Matches Requested Agent Type  
}  
  
RECTANGLE AI_Agent3 {  
  + Ethereum Address (Unique)  
  + Integrated Operator Gateway
  + Stakes Tokens  
  + Matches Requested Agent Type  
}  
  
RECTANGLE ConsensusManager {  
  + Validates Agent Responses  
  + Manages Stakes and Slashes  
}  
  
RECTANGLE AgentEvaluator {  
  + i.e. GPT-4 on Ritual Infernet
  + Provides Trustless Access to LLMs  
}  
  
SmartContract -down-> AgentCoordinator : Requests Output from a Specific Agent Type  
AgentCoordinator -left-> AgentTypeRegistry : Retrieves Agent Type Definition  
AgentTypeRegistry -down-> AgentCoordinator : Returns Agent Type Definition  
AgentCoordinator -right-> AI_Agent1 : Delegates Task  
AgentCoordinator -down-> AI_Agent2 : Delegates Task  
AgentCoordinator -left-> AI_Agent3 : Delegates Task  
AI_Agent1 -right-> ConsensusManager : Submits Response  
AI_Agent2 -down-> ConsensusManager : Submits Response  
AI_Agent3 -left-> ConsensusManager : Submits Response  
ConsensusManager -right-> AgentEvaluator : Verifies Responses using LLMs  
AgentEvaluator -up-> ConsensusManager : Returns Verification Results  
ConsensusManager -up-> AgentCoordinator : Confirms Valid Response  
AgentCoordinator -up-> SmartContract : Returns Trusted Response
@enduml