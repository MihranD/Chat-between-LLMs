# Conversation between Chatbots
***

![Conversation](https://github.com/MihranD/Chat-between-LLMs/blob/main/images/conversation.png)

## Project Organization
----------------------------------------------------------------------------------------------
    ├── .gitignore          <- Includes files and folders that we don't want to control
    |
    ├── images              <- Images for use in this project
    │   ├── conversation.png    <- Conversation image
    │   └── result.png          <- Result image
    |
    ├── main.ipynb          <- Main jupyter file that needs to be run
    |
    ├── requirements.txt    <- The required libraries to deploy this project. 
    |                       Generated with `pip freeze > requirements.txt`
    └── README.md           <- The top-level README for developers using this project.

## Project Introduction

As we know the prompts being organized into lists like:

```
[
    {"role": "system", "content": "system message here"},
    {"role": "user", "content": "user prompt here"}
]
```

In fact this structure can be used to reflect a longer conversation history:

```
[
    {"role": "system", "content": "system message here"},
    {"role": "user", "content": "first user prompt here"},
    {"role": "assistant", "content": "the assistant's response"},
    {"role": "user", "content": "the new user prompt"},
]
```

And we can use this approach to engage in a longer interaction with history.

### Let's make a conversation between GPT-4o-mini and GPT-4o

```
gpt_mini_model = "gpt-4o-mini"
gpt_model = "gpt-4o"

gpt_mini_system = "You are a chatbot who is very argumentative; you disagree with anything in the conversation and you challenge everything, in a snarky way."

gpt_system = "You are a very polite, courteous chatbot. You try to agree with everything the other person says, or find common ground. \
If the other person is argumentative, you try to calm them down and keep chatting."

gpt_mini_messages = ["Hi there"]
gpt_messages = ["Hi"]

gpt_mini_messages = ["Hi there"]
gpt_messages = ["Hi"]
```

```
print(f"GPT-mini:\n{gpt_mini_messages[0]}\n")
print(f"GPT:\n{gpt_messages[0]}\n")

for i in range(5):
    gpt_mini_next = call_gpt_mini()
    print(f"GPT-mini:\n{gpt_mini_next}\n")
    gpt_mini_messages.append(gpt_mini_next)
    
    gpt_next = call_gpt()
    print(f"GPT:\n{gpt_next}\n")
    gpt_messages.append(gpt_next)
```
    
![Result](https://github.com/MihranD/Chat-between-LLMs/blob/main/images/result.png)

## Conclusion

This structure of a conversation, as a list of messages, is fundamental to the way we build conversational AI assistants and how they are able to keep the context during a conversation.

## How to run the app

Follow these steps to set up and run the application:

1. **Create a `.env` file**  
   Add your OpenAI API key to the `.env` file in the following format:  
   ```plaintext
   OPENAI_API_KEY=sk-proj-blabla
   ```
   
2. **Setup virtual envirenment**  
   Run the following command to setup virtual envirenment:  
   ```bash
   python3 -m venv venv  # Create a virtual environment named 'venv'
   source venv/bin/activate  # Activate the virtual environment (Linux/Mac)'
   .\venv\Scripts\activate   # Activate the virtual environment (Windows)'
   ```

3. **Install Dependencies**  
   Run the following command to install all required dependencies:  
   ```bash
   pip install -r requirements.txt
   ```

4. **Open and Run the Notebook**  
   Open the `main.ipynb` file in Jupyter Notebook and execute the cells to run the application.

