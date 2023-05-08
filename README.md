# ChatGPT Prompt Engineering for Developers

## DeepLearning.Ai
[Source](https://learn.deeplearning.ai/chatgpt-prompt-eng/lesson/1/introduction)

## Requirements
* OPENAI_API_KEY: str -> find your OpenAI API secret key [here](https://platform.openai.com/account/api-keys)

### How to use API key 
```
import openai
import os

# NOTE: find your account secret key here: https://platform.openai.com/account/api-keys
os.environ["OPENAI_API_KEY"] = "Your API key"
openai.api_key = os.environ["OPENAI_API_KEY"]
```

### Helper Function

Throughout this course, we will use OpenAI's gpt-3.5-turbo model and the [chat completions endpoint](https://platform.openai.com/docs/guides/chat).

This helper function will make it easier to use prompts and look at the generated outputs:


```
def get_completion(
    prompt:str,
    model:str="gpt-3.5-turbo",
    temperature:float=0
):
    messages = [{"role": "user", "content": prompt}]
    response = openai.ChatCompletion.create(
        model=model,
        messages=messages,
        temperature=temperature, # this is the degree of randomness of the model's output
    )
    return response.choices[0].message["content"]
```

# summary 
* Principles:
    * Write clear and specific instructions
    * Give the model time to think
* Iterative prompt development
* Capabilities: Summarizing, Inferring,
                Transforming, Expanding
* Building a chatbot
