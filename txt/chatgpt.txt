import openai


def response(texts):## Call the API key under your account (in a secure way)
    openai.api_key = ""
    # response = openai.completions.create(engine="text-davinci-002",
    # prompt =  texts,
    # temperature = 0.6,
    # top_p = 1,
    # max_tokens = 64,
    # frequency_penalty = 0,
    # presence_penalty = 0)

    response = openai.chat.completions.create(
        model="gpt-4o",  # You can also use "text-davinci-003" for the Davinci model
        messages=[{"role": "system", "content": "You are a helpful assistant."},{"role": "user", "content": texts}],
        # prompt=texts,
        max_tokens=100  # You can adjust the maximum number of tokens based on your requirements)
    )

    return response.choices[0].message.content