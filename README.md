# Building RAG-Enabled Apps and AI Agents with Semantic Kernel and Azure AI

Welcome to our first Azure AI Foundry workshop (signups are closed, but [this is the description on sign-up page](https://www.meetup.com/north-boston-azure-cloud-user-group/events/304611894/)).

![Prompt Being](assets/prompt-being.jpg)
_Visualize the AI prompt as a powerful being, a conductor orchestrating the symphony of LLMs.  Create an image where this figure exudes authority and control, while other elements like safety, RAG, SDKs, and programming languages are mere instruments in its grand orchestra. This image should convey the message that the prompt reigns supreme in the realm of LLMs, especially from a developer's standpoint._

These instructions will walk you through the workshop labs.

## Workshop Goals

In this workshop, we provide hands-on experience to help you understand how to AI-enable your applications or create new AI-powered services. The toolbox will be Semantic Kernel (examples and labs in C#) and AI Large Language Models (LLMs) running as services in the Azure AI Foundry. We'll start with the basics of Semantic Kernel, move on to implementing RAG patterns using Azure SQL DB's vector search capabilities, and then have a look at building AI Agents. 

The workshop day is a mix of explanatory lectures intermingled with hands-on labs.

## Learning Objectives

After this workshop, you will be able to:

1. Create a working AI application using Semantic Kernel and backed by Azure AI Foundry services
2. Access 🔍 telemetry data (e.g., token usage stats) available through Semantic Kernel's OpenTelemetry support
3. Make tools available to your Semantic Kernel application by creating function prompts and native functions
4. Apply semantic searching and other modern AI techniques to integrate custom or proprietary data sources backed by Azure SQL DB vector search (🚀 now in public preview)
5. Put AI to work for your organization in a more sophisticated model as an 🤖 AI Agent 

## Assumptions

Attendees are assumed to have explored using or creating chatbots with LLMs and have a sense of what is a prompt, what is prompt engineering, and what are some of the possibilities for using LLMs in applications.

## What is in this repo?

We of course hope that you attend one of our in person workshops and are using this repo to work through the labs with the other attendees. However, we also want you to be able to do the labs at your own pace and revisit when you are building your own projects in the future. We also recognize you may not be able to attend an in person event - so we've included everything you need from the workshop in this repo.

### Presentations

* [Session 1 title here](link to pdf file of presentation)
* [Retrieval Augmented Generation (RAG)](assets/Workshop-RAGIntro.pdf)
* [Agentic AI Unlocking the Power of Multi-Agent Systems](./labs/lab6/assets/Multi-Agent-Systems_SK.pdf)

### Labs

* Lab 1: [Getting Started with Semantic Kernel](./labs/lab1/readme.md) ([Visual Studio version](./labs/lab1/readme-vs.md))
* Lab 2: [Creating Semantic Kernel Plugins](./labs/lab2/readme.md) ([Visual Studio version](./labs/lab2/readme-vs.md))
* Lab 3: [Using WebRetrieverPlugin to create a RAG application](./labs/lab3/readme.md) ([Visual Studio version](./labs/lab3/readme-vs.md))
* Lab 4: [Creating a RAG application to Search a PDF](./labs/lab4/readme.md) ([Visual Studio version](./labs/lab4/readme-vs.md))
* Lab 5: [Putting it all together](./labs/lab5/readme.md) ([Visual Studio version](./labs/lab5/readme-vs.md))
* Lab 6: [Semantic Kernel Agent Lab](./labs/lab6/README.md)

## High-Level Summary of Labs

### Lab 0: Can we just access the dang API?
- Focus: Accessing APIs and running a simple SK console app.
- Objectives: Get local copies of API keys, run a simple SK console app.
- Additional Exercises: Experiment with different API endpoints.
- Further Ideas: Explore different API authentication methods.

### Lab 1: Getting Started with Semantic Kernel
- Focus: Adding Semantic Kernel to an application, using Azure OpenAI, and creating prompt functions.
- Objectives: Demonstrate how to add Semantic Kernel to an existing application, use Semantic Kernel to chat with the Azure OpenAI LLM, define a prompt function and use it in an application, recognize the need for chat history and how to add it.
- Additional Exercises: Experiment with different Temperature values to see their influence.
- Further Ideas: Explore different prompt engineering techniques.

### Lab 2: Creating Semantic Kernel Plugins
- Focus: Creating native plugins and using web search plugins.
- Objectives: Implement a plugin with native C# code, use a plugin to give an LLM additional information, create a plugin that uses an LLM to rewrite a user query, utilize a Semantic Kernel plugin to perform a web search.
- Additional Exercises: Experiment with different plugin functions.
- Further Ideas: Explore different ways to integrate plugins with Semantic Kernel.

### Lab 3: Using WebRetrieverPlugin to create a RAG application
- Focus: Creating a RAG application using web search results.
- Objectives: Build a plugin to combine the rewriting of a user's query and a web search, write a prompt to perform a basic RAG pattern call to an LLM, implement a simple chatbot loop, demonstrate the usefulness of a RAG implementation.
- Additional Exercises: Experiment with different web search engines.
- Further Ideas: Explore different ways to integrate web search results with Semantic Kernel.

### Lab 4: Creating a RAG application to Search a PDF
- Focus: Creating a RAG application to search a PDF using a vector store.
- Objectives: Configure a vector store to use with the application, read, chunk and ingest a pdf file, implement logic to perform a similarity search on the vector store, create a plugin to perform RAG using the memory store.
- Additional Exercises: Experiment with different PDF files.
- Further Ideas: Explore different ways to integrate PDF search results with Semantic Kernel.

### Lab 5: Putting it all together
- Focus: Integrating all previous labs and adding logging and user intent determination.
- Objectives: Use filters to add logging and understand the call flows, have the LLM determine which plugin functions to call, create a plugin to determine the user's intent, dynamically control the functions available to the LLM depending on the user's intent.
- Additional Exercises: Experiment with different logging techniques.
- Further Ideas: Explore different ways to integrate logging and user intent determination with Semantic Kernel.

### Lab 6: Semantic Kernel Agent Lab
- Focus: Building agents with Semantic Kernel.
- Objectives: Create an agent with reasoning capabilities to solve domain-specific requests, build an agent with skills to get the current weather of a city by calling a public API, create a team of agents to collaboratively solve more complex problems.
- Additional Exercises: Experiment with different agent skills.
- Further Ideas: Explore different ways to integrate agents with Semantic Kernel.

## Prerequisites

### C#/.NET

Please install this software ahead of the workshop:

1. [VS Code](https://code.visualstudio.com/download) (Windows, Mac, Linux) or [Visual Studio](https://visualstudio.microsoft.com/) (Windows). See [More information on VS Code and VS setup](setup.md)

2. [.NET 8](https://dotnet.microsoft.com/en-us/download) (.NET 9 should work but we have not verified as of 12/1/2024)

3. [SQL Server Management Studio](https://learn.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver16) or [Azure Data Studio](https://learn.microsoft.com/en-us/azure-data-studio/download-azure-data-studio)

4. LLM API credentials from Azure AI Foundry (formerly known as Azure AI or Azure OpenAI). The labs use both GPT-4o and text-embedding-ada-002 models. 

> NOTE: For simplicity, we plan to provide credentials for Azure OpenAI services to use during the workshop, after which they will stop working.

5. Database Connection string to a vector search-enabled Azure SQL DB

> NOTE: For simplicity, we plan to provide credentials for an Azure SQL database to use during workshop, after which they will stop working.

📣 You are also welcome to create your own resources and use them in the workshop. Since you are paying for them, you can decide when to decommission associated resources. See [Instructions for creating LLM Connection String](configure-llm.md)

6. You can expect we will recommend you install additional tools and VS Code or Visual Studio extensions, NuGet packages, or code samples as part of the workshop experience.

## Additional Resources

* [Semantic Kernel](https://github.com/microsoft/semantic-kernel)

## Contributors

### Bill Wilder
Add bio and any social contact info

### Jason Haley
I’m an independent Full Stack Solution Architect with a deep focus on Azure and .NET technologies.  I’m currently focused on helping customers integrate Gen AI functionality into their .NET applications.

[LinkedIn](https://www.linkedin.com/in/jason-a-haley/)
[My Blog](https://jasonhaley.com/)
[Email](mailto://info@jasonhaley.com)

### Juan Pablo Garcia Gonzalez
I am an AI Partner Solution Architect working with Microsoft, focusing on AI solutions with our Global Software Company partners group. I have more than 24 years of experience in the tech industry.

[LinkedIn](https://www.linkedin.com/in/jpgarciagonzalez/)

[Twitter](https://twitter.com/liarjo)
