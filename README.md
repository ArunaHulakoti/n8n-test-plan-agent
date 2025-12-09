AI Test Plan Generator with Google Gemini (n8n Workflow)
This project is an AI-powered Test Plan Generator built using n8n, Google Gemini, and the n8n AI Chat Trigger.
It automatically generates comprehensive test plans based on user input and sends the structured output to a configured email address.

Overview
This workflow allows a user to submit a requirement or feature description through an AI chat endpoint.

The workflow then uses Google Gemini to produce a complete test plan that includes:
Test Objectives
Test Strategy
Test Scope
Detailed Test Cases
Test Data Requirements
Test Environment
Entry and Exit Criteria
Risk Assessment
Estimated Timeline
The generated test plan is formatted and automatically emailed to the configured recipient.

Workflow Structure
The workflow consists of the following nodes:
When Chat Message Received
Entry point triggered when a chat message is received through n8n's AI chat interface.
Workflow Configuration
Stores configuration values such as test plan template type and recipient email.
Test Plan Generator Agent
LangChain-based agent that prepares the system prompt and sends the user request to the LLM.
Google Gemini Chat Model
The underlying LLM used to generate the structured test plan output.
Prepare Email Content
Builds the email subject and email body using the user input and the generated test plan.
Send Test Plan Email
Sends the formatted test plan to the configured email address using Gmail OAuth2.

How It Works
The user submits a requirement or prompt using the n8n chat URL.
The chat trigger captures the input and passes it to the agent.
The agent sends a structured prompt to the Google Gemini model.
Gemini returns a complete, multi-section test plan.

An email message is automatically created, including:
Timestamp
User’s request
Generated test plan
The email is sent to the configured recipient.
Requirements

The workflow requires:
n8n (Cloud or Self-Hosted)
Google Gemini (PaLM) API credentials
Gmail OAuth2 credentials for sending the email
These must be configured under n8n Credentials.

Setup Instructions:
Import the workflow JSON file into n8n.
Configure your Google Gemini API credentials.
Configure Gmail OAuth2 credentials.
Update the email recipient in the Send Test Plan Email node if required.
Enable and execute the workflow using the AI Chat URL.
Configuration
Change Email Recipient

In the node Send Test Plan Email, update the sendTo field:
={{ "your-email@example.com" }}

Use Cases
QA teams generating test documentation
Automation testers preparing structured test plans
Teams documenting feature-level testing requirements
Faster test planning for new features or modules
