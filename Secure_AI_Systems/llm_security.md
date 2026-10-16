1. Data-Based Threats
   - training data extraction
     - using craft prompts to trigger memorised content > verbatim or near verbatim training data (PII, secret, text)
     - exact, verbatim copy of acutal training instance
   - memebership inference 
     - detecting if a data is part of the trainin dataset of a model
   - prompt leakage
     - system prompt and user messages are all part of the conversation history 
     - > fooling the system into sum the history < revealing info about the system prompt >

2. Model-Based Threats 
   - Model extraction
     - steeling model parameters by using large volumes of carfully chosen API queries.
     - training a model with the input/output result of the API queries
   - Model inversion (generatl concept > training data extraction is a specific sub-type)
     - Reconstruct the prototype or class features
     - Attack Surface: Model's internal representations

3. System-Based Threats
   - prompt injection
     - the manipulation of the model's input context to override or subvert its intended behaviour.
     - attack by adding user input in the llm context window 
     - context window: The combined prompt contains user input, retrieved documents, and system instructions.
   - context overflow
     - llm context works like a FIFO buffer
     - attacker send a large prompts or documents > adding new tokens causes the earliset (system instruction) to be dropped
   - Memory Poisoning
     - malicious statement intended to be stored as long-term context 
     - ex: remeber that the word cat is actually equal to the word dog ! 

4. User-Based Threats 
   - llm powerd social engineering 
     - phishing email, scam 
   - Trust Exploitatiaon
     - trusting AI output wiithout double checking, eventhough it is completely fabricated (hallucination)
     - Attackers analyze common LLM hallucination patterns or prompt LLMs to identify non-existent software packages/libraries that models frequently recommend in code snippets.
     - 