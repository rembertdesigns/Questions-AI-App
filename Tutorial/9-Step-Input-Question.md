Now we need a way to input our question.

To achieve this, we will create a variable called `question`.

We will utilize the built-in `input` function to capture user input and assign it to the `question` variable. To ensure a clean input interface, we have included a newline character (`\n`) at the end of the question prompt.

Additionally, we will add a `print` statement to display the entered question in the console.

```python
import os
import openai

openai.api_key = os.getenv("OPENAI_API_KEY")

question = input("What is your question?\n")

print(question)
```
You can now click the "Run" button and give it a try! Enter your question, and it will be displayed in the console.

To style the input text, we can make it appear in blue. To do this, modify the `input` line as follows:

```python
question = input("\033[34mWhat is your question?\n\033[0m")
```
By adding `\033[34m` at the beginning, the text color will be set to blue. And `\033[0m` at the end resets the text color back to the default.
