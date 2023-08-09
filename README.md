# Finetuning-with-LoRA
n this notebook, we will fine-tune Flan-T5 LLM model from Hugging Face for dialogue summarization. To improve the inferences, we perform a Parameter Efficient Fine-Tuning (PEFT) method called LoRA and evaluate the results using ROUGE score.

PEFT is a form of instruction fine-tuning that is much more efficient than full fine-tuning - with comparable evaluation result. 

**Low-Rank Adaptation (LoRA)** allows the user to fine-tune their model using fewer compute resources. Using PEFT/LoRA, you are freezing the underlying LLM and only training the adapter. After fine-tuning for a specific task with LoRA, the result is that the original LLM remains unchanged and a newly-trained “LoRA adapter” emerges. This LoRA adapter is much, much smaller than the original LLM.

LoRA reduces the number of trainable parameters by learning pairs of rank-decompostion matrices while freezing the original weights. This vastly reduces the storage requirement for large language models adapted to specific tasks and enables efficient task-switching during deployment all without introducing inference latency. LoRA also outperforms several other adaptation methods including adapter, prefix-tuning, and fine-tuning.

At inference time, the LoRA adapter needs to be reunited and combined with its original LLM to serve the inference request.#

Edward J. Hu*, Yelong Shen*, Phillip Wallis, Zeyuan Allen-Zhu, Yuanzhi Li, Shean Wang, Lu Wang, Weizhu Chen
Paper: https://arxiv.org/abs/2106.09685
