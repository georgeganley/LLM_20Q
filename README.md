# 20 Questions with LLM's
The code in this repository addresses the 'LLM 20 Questions' Kaggle competition for which two LLMs are designed to play a game of 20 Questions, one as the question asker and the other as the answerer. They interact with each other according to the rules of 20 questions; as such, the efficacy of a successful submission is determined by the quality of the behavior of each LLM in its role within the game.

The current version of this code uses the GPT2 model, loaded from Hugging Face's transformer library. Subsequent versions will use more recent, advanced LLMs.


## Goals

The primary goals of this exercise are to:

1. Demonstrate the ability of language models to generate coherent and contextually appropriate responses.
2. Evaluate the model's capacity for logical deduction through strategic questioning.
3. Showcase the collaborative interaction between paired agents (questioner and answerer) using large language models.

## Methods

### Model and Framework

- **Model**: The project uses the `GPT-2` model, a widely adopted language model known for its ability to generate text that is coherent and contextually relevant.
- **Library**: The implementation relies on the `transformers` library provided by Hugging Face, which facilitates easy access to a variety of pre-trained language models.
- **Environment**: The code is designed to run in a local environment with either a CPU or GPU.

### Implementation Details

1. **Prompt Formatting**: Custom formatting is used to define turns in the conversation between the questioner and answerer, using `<start_of_turn>` and `<end_of_turn>` tokens.
2. **Agent Design**: Two classes are defined:
   - `GemmaQuestionerAgent`: Responsible for asking questions based on the conversation context.
   - `GemmaAnswererAgent`: Provides yes-or-no responses based on the secret keyword and category.
3. **Response Generation**: The agents use the GPT-2 model to generate responses by encoding prompts and decoding outputs using the model's tokenizer.
4. **Session Handling**: Each session of the game is initialized and reset as needed, maintaining a history of questions and answers to guide the agents' decision-making process.

### Testing

The model is tested by simulating a conversation where a keyword is guessed by the questioner. A predefined prompt is used to initiate the conversation, and the model generates responses based on this prompt.

### Installation and Execution

To run the project locally, ensure you have Python installed along with the required dependencies. You can install them using:

```bash
pip install transformers torch

