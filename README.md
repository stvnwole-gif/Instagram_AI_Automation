Instagram AI Customer Service & Sales Automation

An AI-powered customer service and sales automation workflow built with n8n, OpenAI, ManyChat, Google Sheets, and Slack. It helps automate Instagram customer conversations, identify order intent, maintain conversation history, manage order information, and escalate payment requests and customer complaints to human staff.

Overview

This project streamlines customer communication for a writing-services business by combining AI-generated responses with structured workflow logic and human handover.

The workflow is designed to help handle customer inquiries consistently while allowing the human team to take over when necessary.

Features

AI-Powered Responses: Generates replies to customer inquiries using OpenAI and business-specific information.

Order Intent Detection: Identifies potential orders and relevant order details from customer messages.

Conversation History: Stores individual customer and AI messages in Google Sheets to support conversation continuity.

Customer Database: Maintains records for customers with confirmed orders.

Order Tracking: Stores and updates confirmed order records.

Human Handover: Routes customer conversations to human staff when escalation is required.

Customer Care: Identifies complaints and messages the AI cannot reliably answer.

Payment Handover: Routes payment-related requests requiring human assistance for follow-up and verification.

Business Rules: Uses configured service prices, payment terms, revision policies, and delivery-time rules.

Tech Stack

n8n — Workflow automation and orchestration

OpenAI — AI-generated customer responses and intent analysis

ManyChat — Instagram messaging integration

Google Sheets — Business knowledge, conversation history, customer records, and order records

Slack — Team notifications and human handover

How It Works

Receive a Message: The workflow receives an incoming Instagram customer message.

Prepare Context: Customer information, conversation history, and business knowledge are collected.

Generate an AI Response: OpenAI processes the message using the available context and business rules.

Detect Intent: The workflow evaluates the message and AI response to identify order-related actions and potential handover requirements.

Store Conversation Data: Customer and AI messages are recorded in the conversation database.

Update Records: Confirmed customer and order information is stored in the appropriate Google Sheets tables.

Route the Conversation: Messages requiring human attention are directed to the appropriate team.

Send the Reply: The resulting customer response is passed back through the configured messaging integration.

Data Storage

The project uses three separate Google Sheets databases:

Database

Purpose

instagram_conversations

Stores individual customer and AI messages.

clients_database

Stores customer records for confirmed orders.

orders_database

Stores confirmed order records.

A separate business_knowledge sheet provides business information used by the AI.

Customer Handover

Human intervention may be required when:

A customer submits a complaint.

The AI cannot reliably answer a question.

A payment request requires the team to provide payment details.

A customer reports that payment has been sent and verification is needed.

A conversation requires further review or assistance.

The workflow is designed to support human takeover rather than allowing the AI to make unverified commitments.

Business Rules

The AI uses configured business information to respond to inquiries about writing services, pricing, delivery times, payment requirements, and revisions.

For example, the configured Article Writing rate is $0.10 per word, with three revisions included and a 50% upfront payment via USDT required to start.

Actual service terms and delivery estimates should always match the current business knowledge configuration.

Setup

To run this workflow, you will need:

An n8n instance.

An OpenAI API connection.

A ManyChat account configured for Instagram messaging.

Google Sheets access and the required database spreadsheets.

A Slack workspace and the appropriate notification channels.

The workflow's required credentials, node settings, prompts, and data mappings.

Configuration

Before activating the workflow:

Import the workflow into n8n.

Configure the required credentials and integrations.

Set up the Google Sheets databases and verify their column headers.

Check the AI prompt and business knowledge data.

Verify the human-handover conditions and Slack routing.

Test the workflow using sample messages before enabling it for live conversations.

Important: Do not commit API keys, access tokens, passwords, private customer data, or payment credentials to GitHub. Use n8n credentials or environment variables to manage secrets securely.

Testing

Test the workflow with scenarios such as:

General service and pricing inquiries.

New order requests and changes to an existing request.

Follow-up messages that depend on conversation history.

Delivery-time requests that need confirmation.

Customer complaints and unclear messages.

Payment-detail requests and payment-verification requests.

Messages that require human takeover.

Verify both the customer-facing response and the resulting database updates and notifications.

Project Status

This repository contains an automation workflow intended to support AI-assisted Instagram customer service and sales. Before production use, review the workflow configuration, credentials, business rules, database mappings, and handover conditions for your environment.

License

Add a license file if you intend to distribute or allow others to reuse this project. Without a specified license, do not assume that others have permission to reuse the code.
