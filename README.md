
# Proxygpt

ProxyGPT is an innovative application designed to simplify and enhance access to OpenAI's ChatGPT by eliminating the need for an API key. Utilizing reverse proxy technology through Axios, ProxyGPT allows users to seamlessly interact with OpenAI's API, providing both real-time streaming and one-time message functionalities.

## Quick Start
Run the container by command:

```bash 
docker run -dp 3040:3040 nmnarora/proxygpt:latest
```


## Access by cloning
Clone the repo by,
```bash
git clone https://github.com/nmnarora600/proxygpt.git
```

## Sample use case:

* ### NodeJS
```bash
import OpenAI from 'openai';

const openai = new OpenAI({
	apiKey: "something",
	baseURL: "http://localhost:3040/v1",
});

const chatCompletion = await openai.chat.completions.create({
  messages: [{ role: 'user', content: 'Hello OpenAi this is a test message.' }],
  model: 'gpt-3.5-turbo',
});

console.log(chatCompletion.choices[0].message.content);
```

* ### Python
```bash
import openai

openai.api_key = 'something'
openai.base_url = "http://localhost:3040/v1/"

completion = openai.chat.completions.create(
    model="gpt-3.5-turbo",
    messages=[
        {"role": "user", "content": "Hello OpenAi this is a test message but for python."},
    ],
)

print(completion.choices[0].message.content)
```
