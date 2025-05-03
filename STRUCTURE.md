# SambaNova Webinar Project Structure

This project is a comprehensive AI agent application that routes user requests to four different specialized agents:
1. General Assistant Agent
2. Sales Leads Agent
3. Deep Research Agent
4. Financial Analysis Agent

The agents process large volumes of tokens to generate fast and accurate results. The application demonstrates how to build scalable research agents using SambaNova Cloud and Weights & Biases Weave for tracking agent interactions.

## Repository Structure

```
.
├── assets/                          # Static assets for the project
│   ├── wandb_logo-dark.svg          # Weights & Biases logo for dark mode
│   └── wandb_logo-light.svg         # Weights & Biases logo for light mode
│
├── backend/                         # Backend application code
│   ├── agent/                       # Agent implementations
│   │   ├── convo_newsletter_crew/   # Newsletter creation agent crew
│   │   │   ├── config/              # Configuration for newsletter crew
│   │   │   └── tools/               # Tools for newsletter crew
│   │   ├── financial_analysis/      # Financial analysis agent crew
│   │   ├── samba_research_flow/     # Research flow implementation
│   │   │   └── crews/               # Different research crews
│   │   │       ├── edu_content_writer/  # Educational content writer
│   │   │       ├── edu_doc_summariser/  # Document summarization
│   │   │       └── edu_research/        # Educational research
│   │   └── lead_generation_crew.py  # Lead generation agent
│   │
│   ├── api/                         # API implementation
│   │   ├── agents/                  # Agent API endpoints
│   │   │   └── open_deep_research/  # Deep research agent endpoints
│   │   └── services/                # API services
│   │
│   ├── config/                      # Configuration files
│   ├── images/                      # Images for documentation
│   ├── services/                    # Backend services
│   ├── tests/                       # Test files
│   ├── tools/                       # Agent tools
│   └── utils/                       # Utility functions
│
├── frontend/                        # Frontend application code
│   └── sales-agent-crew/            # Vue.js frontend application
│       ├── public/                  # Public assets
│       │   └── Images/              # Image assets
│       └── src/                     # Source code
│           ├── assets/              # Frontend assets
│           ├── components/          # Vue components
│           │   ├── ChatMain/        # Chat interface components
│           │   │   └── ResponseTypes/ # Different response visualizations
│           │   ├── Common/          # Common UI components
│           │   └── icons/           # Icon components
│           ├── router/              # Vue router configuration
│           ├── services/            # Frontend services
│           ├── stores/              # State management
│           ├── utils/               # Utility functions
│           └── views/               # Vue views/pages
│
├── CONTRIBUTING.md                  # Contribution guidelines
├── README.md                        # Project documentation
├── STRUCTURE.md                     # This file - project structure overview
└── docker-compose.yml               # Docker Compose configuration
```

## Key Components

### Backend

1. **Agent System**:
   - Multiple specialized agent crews for different tasks
   - CrewAI integration for agent orchestration
   - SambaNova Cloud integration for LLM capabilities

2. **API Layer**:
   - FastAPI implementation for RESTful endpoints
   - WebSocket support for real-time communication
   - Authentication via Clerk

3. **Services**:
   - Document processing
   - Query routing
   - Market and company research
   - Financial analysis

4. **Tools**:
   - Various specialized tools for agents to use
   - Integration with external APIs (Exa, Tavily)

5. **Data Storage**:
   - Redis for caching and session management
   - Secure storage for API keys and user data

### Frontend

1. **Vue.js Application**:
   - Modern Vue 3 with Composition API
   - Responsive UI with TailwindCSS
   - Component-based architecture

2. **Features**:
   - Real-time chat interface
   - Different response type visualizations
   - Document upload and management
   - API key management

3. **Authentication**:
   - Clerk integration for secure user authentication

## Deployment

The application is containerized using Docker with three main services:

1. **Backend**: FastAPI application with agent logic
2. **Frontend**: Vue.js application served via Nginx
3. **Redis**: For caching and data storage

The `docker-compose.yml` file defines the configuration for these services, including resource limits, networking, and volume mounts.

## Technology Stack

### Backend
- FastAPI
- CrewAI
- SambaNova Agentic Cloud
- Exa Search API
- Tavily API
- Redis
- Financial Data APIs

### Frontend
- Vue.js 3 (Composition API)
- TailwindCSS
- Vite
- Clerk for authentication

## Features

1. **Intelligent Query Routing**: Automatically determines the best agent for user queries
2. **Voice Input Support**: Audio input with speech-to-text transcription
3. **Secure API Key Management**: Encrypted storage of API keys
4. **Chat History Tracking**: Persistent conversation history
5. **Results Export**: Download and share insights
6. **Detailed Company Insights**: In-depth business data
7. **Financial Analysis**: Real-time financial analytics
8. **AI-Generated Templates**: Outreach templates and content generation

## Integration with Weights & Biases

The application uses Weave by Weights & Biases to track agent interactions, providing visibility into:
- Agent decision-making processes
- Tool usage patterns
- Performance metrics
- Conversation flows

This integration enables better debugging, optimization, and understanding of agent behavior.

