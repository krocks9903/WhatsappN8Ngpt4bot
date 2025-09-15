# WhatsApp AI Bot Workflow

An intelligent WhatsApp chatbot built with n8n that can hold conversations with memory and context using AI.

## Overview

This workflow creates an automated WhatsApp bot that:
- Receives messages from WhatsApp users
- Processes them through GPT-4o-mini via OpenRouter
- Maintains conversation context and memory
- Responds intelligently back to WhatsApp

## Features

- **Intelligent Responses**: Powered by GPT-4o-mini for natural conversations
- **Memory Management**: Remembers conversation history for contextual responses
- **Real-time Processing**: Instant message processing and response
- **Scalable Architecture**: Built on n8n for easy modifications and scaling
- **WhatsApp Integration**: Works directly with WhatsApp Business API

## Workflow Components

### 1. WhatsApp Trigger
- Listens for incoming WhatsApp messages
- Automatically captures message content
- Triggers the workflow when new messages arrive

### 2. AI Agent
- Processes incoming messages with AI
- Uses a simple greeting prompt: "hi [user message]"
- Generates contextually appropriate responses

### 3. OpenRouter Chat Model
- Connects to GPT-4o-mini via OpenRouter API
- Handles the AI processing and response generation
- Cost-effective alternative to direct OpenAI integration

### 4. Simple Memory
- Stores conversation history using session key "chat_summary"
- Enables the AI to maintain context across messages
- Improves conversation quality and continuity

### 5. Send Message
- Delivers AI responses back to WhatsApp
- Completes the conversation loop
- Ensures seamless user experience

## Setup Instructions

### Prerequisites
- n8n instance (cloud or self-hosted)
- WhatsApp Business Account
- OpenRouter API account

### Required Credentials
1. **WhatsApp OAuth Account** - For receiving messages
2. **WhatsApp API Account** - For sending messages
3. **OpenRouter API** - For AI processing

### Configuration Steps

1. **Import the Workflow**
   - Import the provided JSON file into your n8n instance
   - Replace all placeholder credential IDs with your actual credentials

2. **WhatsApp Setup**
   - Configure WhatsApp Business API
   - Set up webhook endpoints
   - Replace `YOUR_PHONE_NUMBER_ID` with your WhatsApp Business phone number ID
   - Replace `RECIPIENT_PHONE_NUMBER` with the target phone number

3. **OpenRouter Configuration**
   - Create an OpenRouter account
   - Generate API key
   - Configure the OpenRouter Chat Model node with your credentials

4. **Webhook Configuration**
   - Replace `YOUR_WEBHOOK_ID` and `YOUR_SEND_WEBHOOK_ID` with actual webhook IDs
   - Configure webhook URLs in WhatsApp Business API settings

5. **Activate Workflow**
   - Test the connections
   - Activate the workflow in n8n

## Usage

1. Send a message to your WhatsApp Business number
2. The bot will receive and process the message
3. AI generates a response based on the message and conversation history
4. Response is sent back to the user via WhatsApp

## Customization Options

### Modify AI Behavior
- Edit the prompt in the AI Agent node
- Adjust the greeting message or add system instructions
- Fine-tune response style and tone

### Memory Configuration
- Change the session key for different conversation contexts
- Adjust memory window size for longer/shorter context retention
- Implement user-specific memory sessions

### Response Formatting
- Modify the text body parameter in Send Message node
- Add rich media support (images, documents, etc.)
- Implement response templates

## Technical Specifications

- **Platform**: n8n workflow automation
- **AI Model**: GPT-4o-mini via OpenRouter
- **Memory**: Buffer window with custom session keys
- **Integration**: WhatsApp Business API
- **Execution**: Event-driven (triggered by incoming messages)

## Potential Extensions

- Multi-language support
- Integration with CRM systems
- Advanced conversation routing
- Analytics and reporting
- Custom knowledge base integration
- Voice message processing

## Business Applications

- Customer support automation
- Lead qualification
- FAQ handling
- Appointment scheduling
- Order processing
- Multi-language communication

## Next Steps

This workflow serves as the foundation for more complex AI-powered communication systems, including:
- Translation services
- Multi-channel support
- Enterprise customer service solutions
- Automated sales pipelines

## Contributing

Feel free to fork this workflow and adapt it for your specific needs. Share improvements and extensions with the community.

## License

Open source - feel free to use and modify for your projects.

---

*Built as part of exploring agentic AI workflows and preparing for a WhatsApp translation business venture.*
