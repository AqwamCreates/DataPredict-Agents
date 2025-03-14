# API Reference

## Constructors

### new()

Creates a new DataPredict instance

```lua

DataPredictAgent.new(id: number): DataPredictAgentInstance

```

#### Parameters:

* id: The id of the instance. If the instance of the id already exists, it will return that instance (Default: 1)

### Returns

* DataPredictAgentInstance: The created DataPredict Agent instance.

## Functions (Dictionary-Related)

### addServerDictionary()

```lua

DataPredictAgent:addServerDictionary(serverName: string, serverDictionary: dictionary)

```

#### Parameters:

* serverName: The name of the server to be added to the DataPredict Agent instance.

* serverDictionary: The dictionary containing all the server's information. It contains:

  * address: The IP address or the website address of the server that is hosting the large language model.

  * inputKey: The name of the input key that is responsible of inputting the message to the server during JSON encoding. (Default: "message")

  * outputKey: The name of the output key that is responsible of outputting the message from the server during JSON decoding. (Default: "answer")

### removeServerDictionary()

```lua

DataPredictAgent:removeServerDictionary(serverName: string)

```

#### Parameters:

* serverName: The name of the server to be removed from the DataPredict Agent instance.

### getServerDictionary()

```lua

DataPredictAgent:getServerDictionary(serverName: string): dictionary

```

#### Parameters:

* serverName: The name of the server to get the server dictionary from the DataPredict Agent instance.

#### Returns:

* serverDictionary: The dictionary containing all the server's information. It contains:

  * address: The IP address or the website address of the server that is hosting the large language model.

  * inputKey: The name of the input key that is responsible of inputting the message to the server during JSON encoding.

  * outputKey: The name of the output key that is responsible of outputting the message from the server during JSON decoding.

### addAgentActionArray()

```lua

DataPredictAgent:addAgentActionArray(agentActionName: string, agentActionArray: array)

```

#### Parameters:

* agentActionName: The name of the agent's action to be added to the DataPredict Agent instance.

* agentActionArray: The array containing all of the synonyms related to the given agent's action name.

### removeAgentActionArray()

```lua

DataPredictAgent:removeAgentActionArray(agentActionName: string)

```

#### Parameters:

* agentActionName: The name of the agent's action to be removed from the DataPredict Agent instance.

### getAgentActionArray()

```lua

DataPredictAgent:getAgentActionArray(agentActionName: string): array

```

#### Parameters:

* agentActionName: The name of the agent's action to get the agent action array from the DataPredict Agent instance.

#### Returns:

* agentActionArray: The array containing all of the synonyms related to the given agent's action name.

### addAgentDictionary()

```lua

DataPredictAgent:addAgentDictionary(agentName: string, agentDictionary: dictionary)

```

#### Parameters:

* agentName: The name of the agent to be added to the DataPredict Agent instance.

* agentDictionary: The dictionary containing all the agents's information. It contains:

  * serverName: The name of the server that will handle the agent's interactions.

  * agentActionArray: The array containing the names of top-level actions that can be performed by the agent. (Default: {})

  * hasGlobalMemory: Sets whether or not the agent remembers all the interactions, including the surroundings. (Default: true)

  * hasLocalMemory: Sets whether or not the agent remembers all the interactions with individual interactors. (Default: true)

  * globalMemoryCapacity: The amount of global memory that the agent can store at a given time. (Default: 100)

  * localMemoryCapacity: The amount of local memory that the agent can store at a given time. (Default: 25)

  * initialHiddenChatPrompt: The initial hidden chat prompt to be added to all messages. (Default: nil)

  * addOnHiddenPrompt: The initial hidden prompt to be added to all messages. (Default: nil)

  * hiddenPrompt: The hidden prompt to be added to all messages. (Default: nil)

  * model: The deep reinforcement learning model from DataPredict library to improve the agent's free will capabilities. (Default: nil)

### removeAgentDictionary()

```lua

DataPredictAgent:removeServerDictionary(agentName: string)

```

#### Parameters:

* agentName: The name of the agent to be removed from the DataPredict Agent instance.

### getAgentDictionary()

```lua

DataPredictAgent:getAgentDictionary(agentName: string): dictionary

```

#### Parameters:

* agentName: The name of the agent to get the agent dictionary from the DataPredict Agent instance.

#### Returns:

* agentDictionary: The dictionary containing all the agents's information. It contains:

  * serverName: The name of the server that will handle the agent's interactions.

  * agentActionArray: The array containing the names of top-level actions that can be performed by the agent.

  * hasGlobalMemory: Sets whether or not the agent remembers all the interactions, including the surroundings.

  * hasLocalMemory: Sets whether or not the agent remembers all the interactions with individual interactors.

  * globalMemoryCapacity: The amount of global memory that the agent can store at a given time.

  * localMemoryCapacity: The amount of local memory that the agent can store at a given time.

  * initialHiddenChatPrompt: The initial hidden chat prompt to be added to all messages.

  * addOnHiddenPrompt: The add on hidden prompt to be added to all messages.

  * hiddenPrompt: The hidden prompt to be added to all messages.

  * model: The deep reinforcement learning model from DataPredict library to improve the agent's free will capabilities.

### addInteractorDictionary()

```lua

DataPredictAgent:addInteractorDictionary(interactorName: string, interactorDictionary: dictionary)

```

#### Parameters:

* interactorName: The name of the interactor to be added to the DataPredict Agent instance.

* interactorDictionary: The dictionary containing all the information related to individual agents that has been interacted by the interactor.

### removeInteractorDictionary()

```lua

DataPredictAgent:removeInteractorDictionary(interactorName: string)

```

#### Parameters:

* interactorName: The name of the interactor to be removed from the DataPredict Agent instance.

### getInteractorDictionary()

```lua

DataPredictAgent:getInteractorDictionary(interactorName: string): dictionary

```

#### Parameters:

* interactorName: The name of the interactor to get the interactor dictionary from the DataPredict Agent instance.

#### Returns:

* interactorDictionary: The dictionary containing all the information related to individual agents that has been interacted by the interactor.

## Functions (Agent-Related)

### chat()

```lua

DataPredictAgent:chat(agentName: string, interactorName: string, interactorMessage: string, isAddOnHiddenPromptAdded: boolean)

```

#### Parameters:

* agentName: The name of the agent that will receive the interactor's message.

* interactorName: The name of the interactor that will send the interactor's message.

* interactorMessage: The message content inside of the interactor's message.

* isAddOnHiddenPromptAdded: Set whether or not the add-on hidden prompt is added.

### chat()

```lua

DataPredictAgent:chat(agentName: string, isAddOnHiddenPromptAdded: boolean)

```

#### Parameters:

* agentName: The name of the agent that will perform self chat.

* isAddOnHiddenPromptAdded: Set whether or not the add-on hidden prompt is added.

### act()

```lua

DataPredictAgent:act(agentName: string, agentActionName: string, agentActionTarget: string)

```

### Parameters:

* agentName: The name of the agent that will perform the action.

* agentActionName: The name of the agent's action to be performed.

* agentActionTarget: The target of the selected agent's action.

### queueAgentChat()

```lua

DataPredictAgent:queueAgentChat(agentName: string, agentMessage: string)

```

#### Parameters:

* agentName: The name of the agent that will queue the message.

* agentMessage: The message content inside of the agent's message.

### updateAgentSenseMemory()

```lua

DataPredictAgent:updateAgentSenseMemory(agentName: string, memoryToAdd: string)

```

#### Parameters:

* agentName: The name of the agent that will store the sense memory.

* memoryToAdd: The memory to add to the agent's sense memory.

### updateAgentGlobalMemory()

```lua

DataPredictAgent:updateAgentGlobalMemory(agentName: string, memoryToAdd: string)

```

#### Parameters:

* agentName: The name of the agent that will store the global memory.

* memoryToAdd: The memory to add to the agent's global memory.

### updateAgentLocalMemory()

```lua

DataPredictAgent:updateAgentLocalMemory(agentName: string, interactorName: string, memoryToAdd: string)

```

#### Parameters:

* agentName: The name of the agent that will store the local memory.

* interactorName: The name of the interactor that the agent interacted with inside the memory that will be added.

* memoryToAdd: The memory to add to the agent's local memory.

## Events

### bindChatToAgent()

```lua

DataPredictAgent:bindChatToAgent(agentName: string, functionToRun: function): thread

```

#### Parameters:

* agentName: The name of the agent to give the chatting ability to.

* functionToRun: The function to be called when the agent chats.

#### Returns:

* chatThread: The thread that controls the agent's chatting ability.

### bindSenseToAgent()

```lua

DataPredictAgent:bindSenseToAgent(agentName: string, functionToRun: function): thread

```

#### Parameters:

* agentName: The name of the agent to give the sensing ability to.

* functionToRun: The function to be called when the agent senses.

#### Returns:

* senseThread: The thread that controls the agent's sensing ability.

### bindFreeWillToAgent()

```lua

DataPredictAgent:bindFreeWillToAgent(agentName: string, functionToRun: function): thread

```

#### Parameters:

* agentName: The name of the agent to give the free will to.

* functionToRun: The function to be called when agent's free will is activated.

#### Returns:

* freeWillThread: The thread that controls the agent's free will.

### bindAgentActionToAgentSequential()

```lua

DataPredictAgent:bindAgentActionToAgentSequential(agentName: string, functionToRun: function): thread

```

#### Parameters:

* agentName: The name of the agent to bind the agent's action to.

* functionToRun: The function to be called when the agent's action is called by the agent.

#### Returns:

* actionThread: The thread that controls the agent's action.

### bindAgentActionToAgentParallel()

```lua

DataPredictAgent:bindAgentActionToAgentParallel(agentName: string, agentActionName: string, functionToRun: function): thread

```

#### Parameters:

* agentName: The name of the agent to bind the agent's action to.

* agentActionName: The name of the agent action so only that particular action a particular function.

* functionToRun: The function to be called when the agent's action is called by the agent.

#### Returns:

* actionThread: The thread that controls the agent's action.
