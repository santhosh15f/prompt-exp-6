Development of Python Code Compatible with Multiple AI Tools

Aim:
To compare the responses of two open-source language models, GPT-Neo and GPT-2, 
to a given question, and analyze how different models generate text and handle natural 
language queries.
Procedure:
1. Install Required Libraries:
Use the command below to install the necessary Python libraries:
pip install transformers torch
2. Load Models:
○ Load two pre-trained language models from Hugging Face: ■ GPT-Neo 
(EleutherAI/gpt-neo-1.3B).
■ GPT-2 (gpt2).
3. Define Functions:
○ Define two functions to generate text from both models.
■ GPT-Neo Function: Generates text from the GPT-Neo model. 
■ GPT-2 Function: Generates text from the GPT-2 model.
4. Generate Answers:
○ Input the question “What are the benefits of renewable energy?” to both models 
and generate their responses.
5. Compare Answers:
○ Compare the generated answers from both models to see if they match or differ.
○ Print the responses and a summary indicating whether the answers are the same 
or different.
6. Execute the Code:
○ Run the code to generate and compare answers.
Implementation:
from transformers import pipeline
# Load GPT-Neo and GPT-2 models
generator_neo = pipeline('text-generation', model='EleutherAI/gpt-neo-
1.3B')
generator_gpt2 = pipeline('text-generation', model='gpt2')
# Function to get answer from GPT-Neo
Santhosh S-212221040147
def get_gpt_neo_answer(question): generated_text = 
generator_neo(question, max_length=100,
num_return_sequences=1) return 
generated_text[0]['generated_text']
# Function to get answer from GPT-2 def 
get_gpt2_answer(question): generated_text = 
generator_gpt2(question, max_length=100,
num_return_sequences=1) return 
generated_text[0]['generated_text']
# Function to compare answers from both models 
def compare_answers(question): answer_gpt_neo = 
get_gpt_neo_answer(question) answer_gpt2 = 
get_gpt2_answer(question)
print("GPT-Neo Answer:", answer_gpt_neo) 
print("GPT-2 Answer:", answer_gpt2)
if answer_gpt_neo == answer_gpt2: summary = "Both 
models provided the same answer."
else: summary = "The answers are 
different." print("Summary:", summary)
return {
"question": question,
"gpt_neo_answer": answer_gpt_neo,
"gpt2_answer": answer_gpt2,
"summary": summary
}
# Run the comparison with a sample question 
question = “” result = 
compare_answers(question) print("Comparison 
Result:", result)
Result:
GPT-Neo Answer: The capital of France is Paris. It is a major European city known for its art, 
fashion, and culture.
Santhosh S-212221040147
GPT-2 Answer: The capital of France is Paris, which is the largest city in the country. It is known 
for its landmarks such as the Eiffel Tower.
Summary: The answers are different.
Comparison Result: {'question': 'What is the capital of France?', 'gpt_neo_answer': 'The capital 
of France is Paris. It is a major European city known for its art, fashion, and culture.',
'gpt2_answer': 'The capital of France is Paris, which is the largest city in the country. It is known 
for its landmarks such as the Eiffel Tower.', 'summary': 'The answers are different.'}
Conclusion:
In this experiment, we compared the responses of two different language models, GPT-Neo and 
GPT-2, to the same input question. The results showed that the models provided different 
answers, which indicates that each model has its unique way of generating text based on its 
training data and architecture.
