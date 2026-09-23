* Common Crawl is a non-profit that creates a free, open-access archive of the public internet by scraping billions of web pages every month.
* It provides the primary open text dataset used to train major AI models, including foundational datasets for OpenAI (GPT), Google, and Meta (LLaMA).
* SBOM → "What software components are inside?"
* ML-BOM → "What data and processes went into this AI model?"
* Data provenance refers to the ability to answer three critical questions about training data:
  1. Where did it come from?
  2. When was it collected?
  3. Has it been modified since?

--> We use pruning and quantisation to make AI models smaller, faster, and cheaper to run, while in IT security we must ensure these modifications don’t unintentionally weaken the model’s security or safety mechanisms.
* Quantisation = reducing the numerical precision of the model's weights (e.g. 32-bit → 8-bit) so the model requires
   less memory and computation > Can degrade safety-aligned behaviour; backdoor defences tested on full-precision models may fail to detect threats in quantised versions
* Pruning: Removes less important parameters from a trained model to make it smaller and faster without significantly
   affecting its performance > Changes model behaviour post-training; rarely documented in detail

* Traditional AI:
1,000 phones → send their typing data → central server → train model
* Federated Learning: genuinely does reduce privacy risk at the data level.
1,000 phones → train locally on each phone → send only model updates → central server combines them


fine-tuning Security Problem:
1. Safety alignment erodes, not breaks
   - the defence mechanisms of aligned LLMs can be compromised by fine-tuning
   - Fine-tuning can weaken existing safety safeguards by adding new trainable parameters (LoRA weights) that change the model’s behaviour, even though the BASE MODEL weights remain frozen.
2. Specialisation increases attack surface
   - Fine-tuning can change the model's behavior in ways that make certain prompt-injection attacks more effective than they were against the original model
3. Version matters, and it's rarely tracked 
   - A fine-tuned model inherits potential security risks from the specific base-model version it was created from, so without tracking that exact version, its security exposure cannot be reliably assessed.


* A model card might contain:
    1. Model: What model/version is this?
    2. Purpose: What is it designed to do?
    3. Training data: What type of data was used?
    4. Training method: How was it trained/fine-tuned?
    5. Performance: How well does it perform?
    6. Limitations: Where can it make mistakes?
    7. Bias/safety: What known risks exist?
    8. Intended use: What should/shouldn't it be used for?

