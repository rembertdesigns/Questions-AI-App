Next, you will need to set your API key.

To do this, add the following line of code:

```python
openai.api_key = os.getenv("OPENAI_API_KEY")
```
This code utilizes the os module to fetch the value of the environment variable named "OPENAI_API_KEY" and assigns it to the api_key property within the openai library.

With this step complete, you are now ready to make requests to the OpenAI platform!



