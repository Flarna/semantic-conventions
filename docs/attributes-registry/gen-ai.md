<!--- Hugo front matter used to generate the website version of this page:
--->

<!-- NOTE: THIS FILE IS AUTOGENERATED. DO NOT EDIT BY HAND. -->
<!-- see templates/registry/markdown/attribute_namespace.md.j2 -->

# Gen AI

## Gen Ai Attributes

This document defines the attributes used to describe telemetry in the context of LLM (Large Language Models) requests and responses.

| Attribute                        | Type     | Description                                                                                      | Examples                                                                | Stability                                                        |
| -------------------------------- | -------- | ------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------- | ---------------------------------------------------------------- |
| `gen_ai.completion`              | string   | The full response received from the LLM. [1]                                                     | `[{'role': 'assistant', 'content': 'The capital of France is Paris.'}]` | ![Experimental](https://img.shields.io/badge/-experimental-blue) |
| `gen_ai.prompt`                  | string   | The full prompt sent to an LLM. [2]                                                              | `[{'role': 'user', 'content': 'What is the capital of France?'}]`       | ![Experimental](https://img.shields.io/badge/-experimental-blue) |
| `gen_ai.request.max_tokens`      | int      | The maximum number of tokens the LLM generates for a request.                                    | `100`                                                                   | ![Experimental](https://img.shields.io/badge/-experimental-blue) |
| `gen_ai.request.model`           | string   | The name of the LLM a request is being made to.                                                  | `gpt-4`                                                                 | ![Experimental](https://img.shields.io/badge/-experimental-blue) |
| `gen_ai.request.temperature`     | double   | The temperature setting for the LLM request.                                                     | `0.0`                                                                   | ![Experimental](https://img.shields.io/badge/-experimental-blue) |
| `gen_ai.request.top_p`           | double   | The top_p sampling setting for the LLM request.                                                  | `1.0`                                                                   | ![Experimental](https://img.shields.io/badge/-experimental-blue) |
| `gen_ai.response.finish_reasons` | string[] | Array of reasons the model stopped generating tokens, corresponding to each generation received. | `stop`                                                                  | ![Experimental](https://img.shields.io/badge/-experimental-blue) |
| `gen_ai.response.id`             | string   | The unique identifier for the completion.                                                        | `chatcmpl-123`                                                          | ![Experimental](https://img.shields.io/badge/-experimental-blue) |
| `gen_ai.response.model`          | string   | The name of the LLM a response was generated from.                                               | `gpt-4-0613`                                                            | ![Experimental](https://img.shields.io/badge/-experimental-blue) |
| `gen_ai.system`                  | string   | The Generative AI product as identified by the client instrumentation. [3]                       | `openai`                                                                | ![Experimental](https://img.shields.io/badge/-experimental-blue) |
| `gen_ai.usage.completion_tokens` | int      | The number of tokens used in the LLM response (completion).                                      | `180`                                                                   | ![Experimental](https://img.shields.io/badge/-experimental-blue) |
| `gen_ai.usage.prompt_tokens`     | int      | The number of tokens used in the LLM prompt.                                                     | `100`                                                                   | ![Experimental](https://img.shields.io/badge/-experimental-blue) |

**[1]:** It's RECOMMENDED to format completions as JSON string matching [OpenAI messages format](https://platform.openai.com/docs/guides/text-generation)
**[2]:** It's RECOMMENDED to format prompts as JSON string matching [OpenAI messages format](https://platform.openai.com/docs/guides/text-generation)
**[3]:** The actual GenAI product may differ from the one identified by the client. For example, when using OpenAI client libraries to communicate with Mistral, the `gen_ai.system` is set to `openai` based on the instrumentation's best knowledge.

`gen_ai.system` has the following list of well-known values. If one of them applies, then the respective value MUST be used; otherwise, a custom value MAY be used.

| Value    | Description | Stability                                                        |
| -------- | ----------- | ---------------------------------------------------------------- |
| `openai` | OpenAI      | ![Experimental](https://img.shields.io/badge/-experimental-blue) |
