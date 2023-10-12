# Software Requirements Specification for New Software Developer Employee Training in a Fintech Company

## 1. Introduction

This document outlines the software requirements for a training program designed for new software developer employees in a fintech company. The training program includes the use of autonomous AI agents and conversational chatbots to facilitate learning and information retrieval. The following sections provide an overview of the system's components and functionalities.

## 2. System Description

### 2.1. Autonomous AI Agent Functionality

The training program employs autonomous AI agents to guide new software developer employees through complex tasks by breaking them down into a multi-step action plan. These agents operate by:

- Decomposing complex tasks into a series of intermediate steps.
- Executing actions individually, leading to a final solution.

The operation of these agents follows a cognitive loop, characterized by a Thought/Action/Action Input/Observation sequence, similar to the chain-of-thought process described in research papers by OpenAI and Google. This loop adheres to the ReAct format, which combines chain-of-thought reasoning with action execution.

### 2.2. LangChain Module - Tools

Another integral component of the training program is the LangChain module, specifically the "Tools" module. This module is based on the MRKL paper, which highlights the limitations of large language models (LLMs) due to their reliance on training data and the absence of access to real-time or proprietary data. 

To address these limitations, the system incorporates a concept known as the MRKL system, comprising an expandable set of modules (referred to as "experts") and a routing mechanism (usually the LLM itself). This routing system directs natural language queries to the module best suited to respond to the query. The Tools module serves as the LangChain's abstraction of these experts.

## 3. Example Use Case (Mock Examples)

Please note that the following examples are for illustrative purposes only and do not represent the full capabilities of our AI agent. In practice, the AI agent will provide even more accurate and sophisticated responses to user queries. The examples below serve to demonstrate the basic functionalities of the system.

### 3.1. HR Training Chatbot

To illustrate the system's functionality, consider an HR Training Chatbot designed for employee interaction. The following is an example conversation flow:

- **User:** "Who am I and what's my employee id?"
- **Chatbot:** "Your name is Aditya, and your employee id is 1005676."
- **User:** "How many vacation leaves do I have left, and what is the policy on unused VLs?"
- **Chatbot:** "You have 45 vacation leaves left. Unused VLs can be carried over to the next year, but should not exceed 30 days. Any excess leave will be forfeited. Unused VLs can also be encashed at the end of the year at the basic salary rate. Encashment rate is basic salary divided by 30 days multiplied by unused leaves to be encashed."
- **User:** "How much will I be paid if I encash my vacation leaves?"
- **Chatbot:** "22500.0."
- **User:** "Are employees on probation allowed to have vacation leaves?"
- **Chatbot:** "No, employees on probation are not allowed to have vacation leaves."
- **User:** "Thanks for the information."
- **Chatbot:** "You're welcome. Is there anything else I can help you with today?"

### 3.2. Project Assignment

In another scenario, the autonomous AI agent plays a pivotal role in project assignment for new software developer employees. This use case showcases how the AI agent can streamline the project allocation process and ensure a fair distribution of tasks based on employee skills and preferences.

- **User:** "I'm ready to take on my first project assignment. What options are available?"
- **Chatbot:** "Great! We have three projects available for your consideration: Project A, Project B, and Project C. Here's a brief overview of each project:
  - Project A: A mobile app development project with a tight deadline.
  - Project B: A web application project focused on e-commerce, expected to take several months.
  - Project C: A machine learning research project that involves natural language processing and is anticipated to be a long-term commitment.
  
  Which project are you interested in, or do you need more information about any of them?"
- **User:** "Tell me more about Project C."
- **Chatbot:** "Project C is an exciting research project in the field of machine learning and natural language processing. It involves developing cutting-edge language models and applications for text analysis. This project is expected to last for at least a year, and it offers opportunities for innovation and research publication. Do you want to join Project C, or do you have any other questions?"
- **User:** "What are the prerequisites for Project C?"
- **Chatbot:** "Project C requires a strong background in machine learning, natural language processing, and a good understanding of deep learning frameworks like TensorFlow and PyTorch. Additionally, strong programming skills in Python are essential. It's also preferable if you have experience with research publication in this field. Do you meet these prerequisites?"
- **User:** "Yes, I meet the prerequisites. I'd like to join Project C."
- **Chatbot:** "Excellent choice! I've added you to Project C. You'll receive detailed project information and resources shortly. Is there anything else I can assist you with regarding this project or any other matter?"
- **User:** "No, that's it for now. Thanks for your help."
- **Chatbot:** "You're welcome. If you have any more questions in the future, feel free to ask. Best of luck with Project C!"

This example demonstrates how the AI agent can effectively present project options to employees, provide detailed information about each project, and help employees make informed decisions regarding their assignments. It ensures that employees are assigned to projects that align with their skills and interests, ultimately contributing to higher job satisfaction and productivity.

### 3.3. Financial Compliance Guidance

In a third scenario, the AI agent is utilized to provide financial compliance guidance to employees. This use case showcases the AI agent's ability to offer accurate and up-to-date information on complex financial regulations and policies.

- **User:** "I need guidance on complying with the new tax regulations for international transactions. Can you provide me with the latest information?"
- **Chatbot:** "Of course, I can help with that. The latest tax regulations for international transactions require that all transactions above $10,000 be reported to the tax authority within 30 days. Additionally, there have been changes to the withholding tax rates for non-resident entities. Would you like more details on these changes, or is there anything specific you'd like to know?"
- **User:** "Please provide more details on the changes to withholding tax rates."
- **Chatbot:** "Certainly. The new withholding tax rates for non-resident entities are as follows:
  - Dividend income: 15%
  - Interest income: 20%
  - Royalty income: 25%
  
  It's important to ensure that these rates are applied correctly when dealing with non-resident entities. Do you need any further information, or is there anything else related to financial compliance you'd like to know?"
- **User:** "Thank you for the information. Can you also guide me on the documentation required for reporting transactions above $10,000?"
- **Chatbot:** "Certainly. To report transactions above $10,000, you will need to provide the following documentation:
  - A detailed description of the transaction.
  - The names and addresses of all parties involved.
  - The transaction date and amount.
  - Any supporting documents or contracts related to the transaction.
  
  It's essential to maintain accurate records for compliance. Is there anything else you'd like to know or any other financial compliance questions you have?"
- **User:** "That's all for now. Thanks for your help."
- **Chatbot:** "You're welcome. If you have more questions or need assistance in the future, don't hesitate to reach out. Stay compliant and have a great day!"

This example highlights how the AI agent can provide timely and accurate information about complex financial regulations, ensuring that employees adhere to the latest compliance requirements. This not only mitigates the risk of non-compliance but also promotes transparency and trust within the organization.

## 4. AI Agent Backend Logs (Sample Logs)

The log excerpts provided below are samples for reference and auditing purposes. They showcase the AI agent's capability to handle user queries and provide accurate responses. It's important to emphasize that these are simplified log entries for demonstration purposes, and the actual AI agent's performance will be much more advanced and precise in real-world scenarios.

### 4.1 Encashing vacation leaves

```shell
get_response("How much will I be paid if I encash my unused VLS?")

Entering a new AgentExecutor chain...
I need to check the timekeeping policies and the employee data to calculate the amount.
Action: Timekeeping Policies
Action Input: Check the policy on VL encashment
Observation: According to the HR Policy Manual Leave Policy, Vacation Leave can be encashed at the end of the year at the basic salary rate. The encashment rate is basic salary divided by 30 days multiplied by unused leaves to be encashed.
Thought: Now I need to get the basic salary rate and the number of unused VLS from the employee data.
Action: Employee Data
Action Input: df[df['name'] = 'Alexander Verdad'][['basic_pay_in_php', 'vacation_leave']]
Observation: basic pay_in_php vacation_leave
1
15000
45
Thought: Now I can calculate the amount.
Action: Calculator
Action Input: (15000/30)*45
Entering a new LLMMathChain chain...
(15000/30)*45
(15000/30) 45 ...numexpr.evaluate(" (15000/30) "45")...
Answer: 22500.0
Finished chain.
Observation: Answer: 22500.0
Thought: I now know the final answer.
Final Answer: You will be paid Php 22,500.00 if you encash your unused VLS.
Finished chain.
'You will be paid Php 22,500.00 if you encash your unused VLS.'
```

In this example, the system demonstrates its ability to provide precise answers by combining information from various sources and performing calculations as required.

### 4.2 Project Assignment and Prerequisites

```shell
get_response("What are the prerequisites for joining Project C?")

Entering a new AgentExecutor chain...
I need to retrieve the prerequisites for Project C from the project data.
Action: Project Data
Action Input: Prerequisites for Project C
Observation: Prerequisites for Project C:
- Strong background in machine learning and natural language processing.
- Good understanding of deep learning frameworks like TensorFlow and PyTorch.
- Strong programming skills in Python.
- Preferable experience with research publication in this field.
Thought: Now I can check if the user meets these prerequisites.
Action: User Profile
Action Input: User skills and experience
Observation: User profile:
- Machine learning experience: Yes
- Deep learning frameworks knowledge: Yes
- Strong Python programming skills: Yes
- Research publication experience: No
Thought: The user meets all prerequisites except for research publication experience.
Final Answer: You meet the prerequisites for Project C except for research publication experience. You can still join the project, but improving your research publication skills would be beneficial.
Finished chain.
'You meet the prerequisites for Project C except for research publication experience. You can still join the project, but improving your research publication skills would be beneficial.'
```

This log entry showcases the AI agent's ability to retrieve and provide specific project prerequisites, evaluate the user's qualifications, and offer personalized advice, demonstrating how the AI agent can help users make informed decisions about their project assignments.

### 4.3 Financial Compliance Guidance

```shell
get_response("Please provide more details on the changes to withholding tax rates.")

Entering a new AgentExecutor chain...
I need to fetch the latest withholding tax rate changes for non-resident entities from the tax regulations data.
Action: Tax Regulations Data
Action Input: Withholding tax rate changes for non-resident entities
Observation: Latest withholding tax rate changes for non-resident entities:
- Dividend income: 15%
- Interest income: 20%
- Royalty income: 25%
Thought: The user asked for more details on the changes.
Final Answer: The new withholding tax rates for non-resident entities are as follows:
- Dividend income: 15%
- Interest income: 20%
- Royalty income: 25%
Finished chain.
'The new withholding tax rates for non-resident entities are as follows:
- Dividend income: 15%
- Interest income: 20%
- Royalty income: 25%'
```

This log entry demonstrates the AI agent's capability to access and provide up-to-date information from complex data sources, in this case, the tax regulations data. It ensures that users receive precise and relevant details regarding the requested information, contributing to compliance and informed decision-making.
