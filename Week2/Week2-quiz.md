**1.** Fill in the blanks: __________ involves using many prompt-completion examples as the labeled training dataset to continue training the model by updating its weights.  This is different from _________ where you provide prompt-completion examples during inference.

- [ ] Pre-training, Instruction fine-tuning
- [ ] Prompt engineering, Pre-training
- [X] Instruction fine-tuning, In-context learning
- [ ] In-context learning, Instruction fine-tuning

Instruction fine-tuning utilizes labeled training data with prompt-completion examples to further train model weights. In-context learning incorporates prompt-completion examples during inference, employing zero or few-shot techniques. 


**2.** Fine-tuning a model on a single task can improve model performance specifically on that task; however, it can also degrade the performance of other tasks as a side effect.  This phenomenon is known as: 

- [ ] Instruction bias
- [ ] Model toxicity
- [ ] Catastrophic loss
- [X] Catastrophic forgetting


**3.** Which evaluation metric below focuses on precision in matching generated output to the reference text and is used for text translation?

- [ ] ROUGE-1
- [ ] ROUGE-2
- [X] BLEU
- [ ] HELM


**4.** Which of the following statements about multi-task finetuning is correct? Select all that apply:

- [ ] Multi-task finetuning can help prevent catastrophic forgetting.
- [ ] Multi-task finetuning requires separate models for each task being performed.
- [ ] FLAN-T5 was trained with multi-task finetuning.
- [ ] Performing multi-task finetuning may lead to slower inference.


However, remember that to prevent catastrophic forgetting it is important to fine-tune on multiple tasks with a lot of data.
The FLAN family of models have been trained with multi-task instruction finetuning.


**5.** "Smaller LLMs can struggle with one-shot and few-shot inference:"
Is this true or false?

- [X] True
- [ ] False

Even when you include a couple of examples, smaller models might still struggle to learn the new task through examples.


**6.** Which of the following are Parameter Efficient Fine-Tuning (PEFT) methods? Select all that apply.

- [X] Selective
- [X] Reparameterization
- [ ] Subtractive
- [X] Additive

Selective methods is a category of PEFT that fine-tunes a subset of the original LLM parameters. It uses different approaches to identify which parameters to update.

Reparameterization methods create a new low-rank transformation of the original network weights to train, decreasing the trainable parameter count while still working with high-dimensional matrices. LoRa is a common technique in this category.

Additive methods freeze all of the original LLM weights and introduce new model components to fine-tune to a specific task. 


**7.** Which of the following best describes how LoRA works?

- [X] LoRA decomposes weights into two smaller rank matrices and trains those instead of the full model weights.
- [ ] LoRA continues the original pre-training objective on new data to update the weights of the original model.
- [ ] LoRA freezes all weights in the original model layers and introduces new components which are trained on new data.
- [ ] LoRA trains  a smaller, distilled version of the pre-trained LLM to reduce model size

LoRA represents large weight matrices as two smaller, rank decomposition matrices, and trains those instead of the full weights. The product of these smaller matrices is then added to the original weights for inference.


**8.** What is a soft prompt in the context of LLMs (Large Language Models)?


- [X] A set of trainable tokens that are added to a prompt and whose values are updated during additional training to improve performance on specific tasks.
- [ ] A strict and explicit input text that serves as a starting point for the model's generation.
- [ ] A technique to limit the creativity of the model and enforce specific output patterns.
- [ ] A method to control the model's behavior by adjusting the learning rate during training.

A soft prompt refers to aa set of trainable tokens that are added to a prompt. Unlike the tokens that represent language, these tokens can take on any value within the embedding space. The token values may not be interpretable by humans, but are located in the embedding space close to words related to the language prompt or task to be completed.


**9.** "Prompt Tuning is a technique used to adjust all hyperparameters of a language model."
Is this true or false?

- [ ] True
- [X] False

Prompt Tuning focuses on optimizing the prompts given to the model using trainable tokens that don’t correspond directly to human language.  The number of tokens you choose to train, however, would be a hyperparameter of your training process.


**10.** "PEFT methods can reduce the memory needed for fine-tuning dramatically, sometimes to just 12-20% of the memory needed for full fine-tuning."

- [X] True
- [ ] False

By training a smaller number parameters, whether through selecting a subset of model layers to train, adding new, small components to the model architecture, or through the inclusion of soft prompts, the amount of memory needed for training is reduced compared to full fine-tuning.