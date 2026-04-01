**Chatbot using Transformers**

**1. Project Objective**

The objective of this assignment was to design and implement a functional, interactive chatbot using the Hugging Face Transformers library. The system is designed to process natural language input and generate contextually relevant responses using a pre-trained Large Language Model (LLM).

**2. Technical Architecture**

The chatbot follows a Hybrid Intelligence Model to ensure both accuracy for factual queries and flexibility for general conversation.

**2.1 Model Selection**

Core Model: google/flan-t5-large.

Architecture Type: Encoder-Decoder (Sequence-to-Sequence).

Reasoning: FLAN-T5 was selected over standard GPT-2 because it is instruction-fine-tuned. This allows the model to better understand specific commands like "Answer clearly," making it highly effective for academic and technical assistants.

**2.2 The Pipeline Flow**

The system processes data through the following stages:

User Input: Captures raw text from the console.

Verified Layer: Checks a dictionary of "Verified Answers" for 100% accuracy on core technical terms (AI, Python, ML).

Preprocessing: Tokenizes the input text into numerical tensors.

Model Inference: The Transformer generates the most probable following tokens.

Decoding: Converts tensors back into human-readable strings while skipping special tokens.

****3. Implementation Details
**
3.1 Key Functions**

get_verified_answer(user_input): Acts as a deterministic filter to ensure the chatbot provides standard definitions for foundational IT concepts.

generate_response(user_input): Handles the generative aspect of the bot, utilizing the model.generate() method with specific parameters.

**3.2 Hyperparameter Tuning**

To optimize performance on a local Jupyter Notebook environment, the following parameters were used:

max_length=80: Restricts the output length to reduce latency and prevent rambling.

do_sample=False: Implements Greedy Search, which prioritizes the single most likely token to maintain factual consistency.

**4. Code Structure**

The implementation is divided into four modular sections:

Environment Setup: Installation of transformers, torch, and sentencepiece.

Model Initialization: Downloading and loading the FLAN-T5 weights and tokenizer.

Logic Layer: Defining the verification and generation functions.

Interaction Layer: A while loop that manages the user interface and the exit condition.

**5. Learning Outcomes**
Library Proficiency: Gained hands-on experience with the Hugging Face Hub and the AutoModel API.

Latency Optimization: Learned how to manage inference speed in a CPU-bound Jupyter environment by adjusting token limits.

Prompt Engineering: Understood how adding context to a prompt can significantly change the quality of a model's output.

**6. How to Run**
Open the provided .ipynb file in Jupyter Notebook.

Execute the cells in sequence.

Type your queries in the input box.

Type 'exit' to terminate the program.

Type 'exit' to terminate the program.
