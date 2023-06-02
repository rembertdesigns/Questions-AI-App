You may have noticed that the program currently ends after asking a single question. Let's fix that.

To achieve this, we'll place our Q&A code inside a `while` loop. This will allow us to repeat the process and continue asking questions until we decide to stop running the program.

```python
import os
import openai

openai.api_key = os.getenv("OPENAI_API_KEY")

while True:
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
By setting the condition of the `while` loop to `True`, which is a boolean value, the loop will continue running the code inside it indefinitely until we manually stop the program.

Now you can keep asking questions and receiving responses from your AI assistant as long as you wish.
