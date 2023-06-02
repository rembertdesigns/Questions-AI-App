Now, we need to make a request to the OpenAI API.

To accomplish this, we will use a code snippet provided in the [OpenAI documentation](https://platform.openai.com/docs/api-reference/chat/create?lang=python).

We'll be making a Chat Completion request, which is the type of completion commonly used in ChatGPT. This is a standard request to interact with OpenAI.

In the right section of the OpenAI docs, you'll find a code example. Make sure to select "Python" from the dropdown menu.

We will add similar code to our program, placing it between the question variable and the print statement:

```python
import os
import openai

openai.api_key = os.getenv("OPENAI_API_KEY")

question = input("\033[34mWhat is your question?\n\033[0m")

completion = openai.ChatCompletion.create(
    model="gpt-3.5-turbo",
    messages=[
      {"role": "system", "content": "You are a helpful assistant. Answer the given question."},
      {"role": "user", "content": question}
    ]
)

print("\033[32m" + completion.choices[0].message.content + "\n")
```
Let's go through what this code does:

First, we create a `completion` variable.

Second, we make a request to OpenAI's "chat completion" endpoint using the `openai` library we imported.

This request takes two parameters:

- The model to use, in this case, "gpt-3.5-turbo" (the default ChatGPT model).
- The messages to provide as input. The first message is a system message with a prompt that instructs the AI how to behave. The second message is a user message that contains our question stored in the question variable.

Instead of printing our question, we now want to print the response from OpenAI.

```python
print("\033[32m" + completion.choices[0].message.content + "\n")
```
Here's what we did:

- Styled the print statement as green text.
- Accessed the response using `completion.choices[0].message.content`.
- Added a new line character to add spacing in our CLI.

Run the program again to ask your AI bot a question and receive a response!
