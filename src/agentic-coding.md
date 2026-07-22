<image alt="Docker Logo" height="100px" src="../images/agentic-coding.png" width="100px" />

# Agentic Coding 

## General
* LLMs don’t have memory. They “remember” things through their context window which is the maximum amount of tokens you can send to the model. You send your entire input and output of your chat to the LLM.
* The system message is the "personality" behind every AI interaction. This is set by the provider and takes up part of your context window.
* Allow LLMs to summarize your chats to bring context over to a brand new chat if your current chat is not producing the desired outcome.
* Delimiters allow us to break prompts up so the LLM can understand our ask much easier which will give us better results. (EX: tripple quotes, dashes, XML tags, markdown)

## Prompt Types
* Standard Prompt - Direct question or instruction to AI. The simplest form of prompting.
* Zero Shot Prompt - Direct task request without any examples. Model relies entirely on pre-training knowledge.
* One Shot Prompt - Providing exactly one example with your request. Model learns the pattern, format, and style.
* Few Shot Prompt - Provideing 2+ examples to establish patterns and edge cases. Model learns nuances and variatoins from diverse examples. Include variety.
* Structured Output - Tell the model exactly how you want your response structured to get consistent formats every time.
* Chain Of Thought - Ask the model to show its reasoning step-by-step. Breaks complex problems into intermediate steps.

## Cursor
* Inline Edit (CMD + K) - Surgical, in-place code modifications directly in your code editor.
* AI Chat (CMD + L or CMD + I) - Opens up a chat window along the side. Enables agentic coding for complex , multi-file tasks. You describe a goal and then the agent comes up with a plan and carries it out.