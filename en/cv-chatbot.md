# CV Chatbot  

Hi! This README contains an overview of the tools and ideas I used to develop **CV Chatbot**. Feel free to check it out [here](https://yabra-cv-chatbot-5d4c332eae4a.herokuapp.com/) and reach out if you want to discuss anything!  

## Overview  

CV Chatbot is an interactive application that helps users explore my CV in a conversational way. It integrates **LLMs** with a simple yet effective user interface, allowing for intuitive and responsive interactions.  

## Guts  

The chatbot's core functionality is powered by **Python**, using **LangChain** and **LangGraph** to structure interactions with **GPT-4o-mini** while efficiently managing chat history. These libraries simplify working with large language models and allow for flexible prompt engineering.  

A helpful tutorial that guided me through the process:  
🔗 [LangChain Chatbot Tutorial](https://python.langchain.com/docs/tutorials/chatbot/)  

## Model Considerations  

### RAG vs. Long Context within Prompt  

I debated between **Retrieval-Augmented Generation (RAG)** and simply including my CV within the prompt. Since my detailed CV does not exceed **four pages**, and modern LLMs handle longer contexts effectively, I decided to embed my CV information **directly in the system prompt**. This ensures that the chatbot always has access to my full background without requiring a retrieval system.  

### Security  

I wanted to ensure that my chatbot remains **professional and relevant**. To prevent it from responding to **off-topic** or **inappropriate** queries, I extensively tested different **prompting strategies** to steer the model towards a **focused and professional tone**. The final system prompt ensures that the chatbot strictly speaks about my CV and related topics.  

## Frontend  

Since I am not a front-end engineer, I opted for **Dash (by Plotly)** to build a simple yet functional UI entirely in **Python**. Dash makes it easy to create interactive web applications with minimal effort.  

I found this example particularly useful:  
🔗 [Dash Chatbot Example](https://github.com/plotly/dash-sample-apps/tree/main/apps/dash-chatbot)  

## Deployment  

The chatbot is deployed on **Heroku** using a **basic Dyno**. Heroku provides a straightforward deployment process and handles scalability for small applications.  

## Database  

To log user interactions, I set up a **PostgreSQL database** on **Heroku**. This allows me to analyze how users engage with the chatbot. I use the **psycopg2** library in Python to insert data into the relevant tables.  
