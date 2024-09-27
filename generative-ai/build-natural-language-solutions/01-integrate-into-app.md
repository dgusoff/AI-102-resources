# Integrate Azure OpenAI into your app

## create a reosurce

## deploy a model

3 types
* GPT
* code (built atop GPT, trained on code)
* embeddings

## authentication and specificaiton of deployed model
* endpoint
* key
* deployment name

## prompt engineering

more details => better response

look at prompt examples in playground

prompt engineering documentaiton https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/prompt-engineering


## endpoints

REST or SDKs for Python, C#, and Javascript

* ChatCompletion - only option for GPT-4 and is preffered for gpt-35-turbo
* Completion - available for all GPT3
* Embeddings

sample input, chat completion

```json
{"role": "system", "content": "You are a helpful assistant, teaching people about AI."},
{"role": "user", "content": "Does Azure OpenAI support multiple languages?"},
{"role": "assistant", "content": "Yes, Azure OpenAI supports several languages, and can translate between them."},
{"role": "user", "content": "Do other Azure AI Services support translation too?"}
```




