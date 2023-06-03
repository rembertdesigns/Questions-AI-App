We can enhance our program by adding an if statement to check `if` we type 'exit' as our question, which will allow us to stop the program.

```python
import os
import openai

openai.api_key = os.getenv("OPENAI_API_KEY")

while True:
    question = input("\033[34mWhat is your question?\n\033[0m")

    if question.lower() == "exit":
        print("\033[31mGoodbye!\033[0m")
        break

    completion = openai.ChatCompletion.create(
        model="gpt-3.5-turbo",
        messages=[
            {"role": "system", "content": "You are a helpful assistant. Answer the given question."},
            {"role": "user", "content": question}
        ]
    )

print("\033[32m" + completion.choices[0].message.content + "\n")
```
Here, we added an `if` statement to check a specific condition. We use the `lower()` method to convert the question variable to lowercase and then compare it with the string 'exit'. If the condition is true, we print "Goodbye!" in red text and break out of the` while` loop, thereby ending the program.

This allows us to gracefully exit the Q&A session whenever we type 'exit' as our question.
