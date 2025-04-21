# Chainlit OpenAI Project Setup with UV

## Step 1: Initialize the Project

```bash
# First of all we initialize the chainlit_op_ag (OpenAI project) using the UV package manager
uv init --package chainlit_op_ag
cd chainlit_op_ag
```

## Step 2: Add Chainlit

```bash
# Then we have to add Chainlit using the command below
uv add chainlit
```

## Step 3: Dry Run to Test Chainlit

```bash
# After adding Chainlit, we should dry run it once to check if it's working or not
uv run chainlit hello
```

## Step 4: Create chatbot.py

```bash
# After this, we have to make a file named chatbot.py
# Place it in: src/chainlit_op_ag/

# Paste a prebuilt function that repeats our input in chat message format
# Example content for chatbot.py:

import chainlit as cl

@cl.on_message
async def main(message: cl.Message):
    await cl.Message(content=f"You said: {message.content}").send()
```

## Step 5: Run the Chatbot

```bash
# Then run it using the command below
uv run chainlit run "src/chainlit_op_ag/chatbot.py" -w
```
