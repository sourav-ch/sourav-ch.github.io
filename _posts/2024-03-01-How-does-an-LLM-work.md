---
title: How does an LLM work?
tags: [LLM, Components]
style: fill
color: info
description: Learn about the internal working of an LLM 
---
A few weeks back, I attended a workshop on AI/ML concepts and the foundational knowledge required to use them. We were given a brief explanation on how data is pre-processed, and models are trained and tested. What excited me the most was Generative AI and how it processes a prompt to give us very accurate responses, regardless of the topic. Here is a step by step process of the workings of a chatbot.

### Step-by-Step Flow of Processing a User Prompt

#### 1. **User Input**
The process begins when the user inputs a prompt into the chatbot interface. This could be a simple question or a more complex request, such as "What's the weather like today?" or "Can you help me book a flight to New York next Friday?"

#### 2. **Preprocessing the Input (Optional)**
Before diving into the processing itself, the chatbot may perform some basic preprocessing, such as:
   - **Tokenization:** Breaking down the input into smaller components (tokens) like words or subwords.
   - **Normalization:** Converting the input to a consistent format (e.g., lowercasing, removing punctuation).
   - **Named Entity Recognition (NER):** Identifying specific entities (like dates, locations, or names) within the input.

This preprocessing helps in understanding the structure and key elements of the prompt.

#### 3. **Text Processing with Large Language Model (LLM)**
The next step is where the **Large Language Model (LLM)** comes into play:
   - **Context Understanding:** The LLM first processes the user’s prompt to understand the query’s intent. It evaluates the input context, including any ambiguities or specific phrasing.
   - **Initial Response Generation:** If the prompt is straightforward and doesn't require additional information or real-time data, the LLM may generate a direct response. For example, "The weather today in your city is sunny."

However, if the query is more complex or asks for real-time information, the chatbot might need to retrieve additional data. This is where the next steps come in.

#### 4. **Retrieval with Retrieval-Augmented Generation (RAG)**
Now, if the LLM determines that the information required for the prompt isn’t contained within its pre-trained model, it uses **Retrieval-Augmented Generation (RAG)** to fetch relevant external data:
   - **Querying the Vector Database:** The LLM queries a **Vector Database (Vector DB)**. This vector database is preloaded with indexed documents, articles, and other data sources in the form of vectors (numerical representations of data). These vectors capture the semantic meaning of the content, making it easier for the system to find relevant information.
   
#### 5. **Vector Database Search**
Here’s where the **Vector Database (Vector DB)** plays a crucial role:
   - **Embeddings of the Input:** The chatbot takes the user’s prompt and converts it into a vector (embedding) using a pre-trained embedding model. This embedding captures the semantic meaning of the input, ensuring that the chatbot doesn’t just search for keywords but also understands the context and nuances of the request.
   - **Similarity Search:** The vector database searches for documents or data that are semantically similar to the user’s input by comparing the vector of the prompt against stored vectors in the database.
   - **Retrieving Relevant Data:** The database returns the top results—documents, passages, or other pieces of information—that are most relevant to the user’s query.

#### 6. **Data Retrieval and Decision-Making by Agents**
At this point, **Agents** within the chatbot system take over:
   - **Evaluating Results:** The agent assesses the retrieved data and decides how to integrate it into the final response. If the retrieved data is sufficient to answer the question, the agent might use it directly. If the data is insufficient or requires further clarification, the agent might trigger additional queries or steps.
   - **Performing Actions (if needed):** If the prompt requires an action (e.g., booking a flight, updating a calendar), the agent might interact with external APIs or systems to complete that task. For example, if the user asks for a flight booking, the agent might contact an external travel service API to retrieve available flights.
   - **Context Management:** Agents also manage the ongoing conversation, keeping track of prior interactions to ensure the chatbot responds in a manner that makes sense over the course of the dialogue.

#### 7. **Response Generation with LLM and Final Refinement**
Once the agent has assessed the retrieved data and context, it goes back to the **Large Language Model (LLM)** for generating the final response:
   - **Incorporating Retrieved Data:** The LLM takes the retrieved information and combines it with its existing knowledge to craft a response. The information from the vector database, combined with the chatbot's context management, ensures that the response is both accurate and relevant.
   - **Response Refinement:** The LLM might adjust the tone, phrasing, or structure of the response based on the conversational context. For example, if the user has asked a casual question, the LLM might adjust the response to sound more conversational or informal.

#### 8. **Response Delivery**
Finally, the chatbot delivers the refined response to the user. The response might be a direct answer ("The weather is sunny in your city today"), a recommendation ("I found flights to New York next Friday, here they are"), or an action completion ("Your flight has been booked for next Friday").

#### Example Flow of a User Prompt:

**User Prompt:** *"Can you book me a flight to New York for next Friday?"*

1. **User Input:** "Can you book me a flight to New York for next Friday?"
2. **Text Processing (LLM):** The LLM understands that the user is asking for a flight booking and identifies "New York" and "next Friday" as key details.
3. **Retrieval with RAG:** The LLM might query external resources, like flight databases, to retrieve available options.
4. **Vector Database Search:** The prompt is converted into a vector, and the vector database finds relevant data on available flights to New York next Friday.
5. **Agent Decision:** The agent evaluates the available flights and decides which to present. It might also check external APIs for flight booking information.
6. **Response Generation:** The LLM, incorporating the retrieved flight data, generates a response: "I found flights to New York for next Friday. Here are your options."
7. **Response Delivery:** The chatbot presents the flight options to the user.

### Conclusion: How These Components Work Together

To summarize, the flow of a prompt through these components looks like this:
1. **User Input** → 2. **Text Processing with LLM** → 3. **Retrieval with RAG** → 4. **Vector DB Search** → 5. **Agent Decision** → 6. **Response Generation (LLM)** → 7. **Response Delivery**.

Each component—LLMs, RAG, Vector DBs, and Agents—plays a crucial role in ensuring that the chatbot provides accurate, contextually relevant, and dynamic responses. By combining these advanced technologies, chatbots can handle more complex interactions, retrieve up-to-date information, and even take action on behalf of the user. This makes for a far more intelligent and engaging user experience.