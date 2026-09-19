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