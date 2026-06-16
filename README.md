# OmniAgent — Autonomous AI Assistant

An AI-powered assistant built with a **LangChain ReAct agent** that autonomously decides when to invoke real-time web search, send emails, or respond directly. Features persistent chat history, auto-generated titles, and full JWT authentication.

## Architecture

```
OmniAgent/
├── Backend/          # Node.js + Express API server
│   ├── src/
│   │   ├── controllers/   # Auth & chat controllers
│   │   ├── models/        # Mongoose schemas (User, Chat)
│   │   ├── routes/        # Express route definitions
│   │   ├── services/      # AI agent (LangChain), mail (Nodemailer)
│   │   └── middlewares/   # JWT auth middleware
│   └── server.js
├── Frontend/         # React + Vite SPA
│   └── src/
│       ├── app/           # Store, routes, theme
│       └── features/      # Auth & Chat feature modules
└── README.md
```

## Tech Stack

| Layer | Technologies |
|-------|-------------|
| **AI Agent** | LangChain, Mistral AI, Gemini, ReAct pattern |
| **Web Search** | Tavily API (real-time internet search tool) |
| **Email** | Nodemailer + Google OAuth2 |
| **Backend** | Node.js, Express, Socket.IO, JWT, bcrypt |
| **Frontend** | React 19, Redux Toolkit, React Router v7, Tailwind CSS |
| **Database** | MongoDB (Mongoose) |

## Features

- **ReAct AI Agent** — Autonomously reasons, searches the web, and sends emails via tool-calling
- **Real-time Chat** — Socket.IO-powered bidirectional messaging
- **Auto-generated Titles** — AI creates chat titles using Mistral
- **Markdown Rendering** — Full GFM support (tables, code blocks, lists)
- **JWT Authentication** — Register, login, email verification flow
- **Persistent History** — Multi-turn conversations stored in MongoDB

## Getting Started

### Prerequisites

- Node.js 18+
- MongoDB Atlas account (or local MongoDB)
- API keys: Gemini, Mistral, Tavily
- Google OAuth2 credentials (for email features)

### Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/aarjav812/OmniAgent.git
   cd OmniAgent
   ```

2. **Backend setup**
   ```bash
   cd Backend
   cp .env.example .env    # Fill in your credentials
   npm install
   npm run dev
   ```

3. **Frontend setup** (in a new terminal)
   ```bash
   cd Frontend
   npm install
   npm run dev
   ```

4. Open `http://localhost:5173` in your browser.

### Environment Variables

See [`Backend/.env.example`](Backend/.env.example) for all required variables.

## License

MIT
