# 🚀 Tryliate

**AI Agent Builder Platform** - Build, Connect & Deploy AI Agents with Real-World Integrations

---

## 📋 Overview

Tryliate is a next-generation AI Agent Builder Platform designed to empower developers and businesses to create, configure, and deploy intelligent AI agents that seamlessly integrate with real-world tools and services. Our platform enables you to build production-ready AI agents without the complexity of managing infrastructure, authentication flows, or API integrations.

### ✨ Key Features

- 🤖 **Visual Agent Builder** - Intuitive interface for designing AI agent workflows
- 🔌 **Real-World Integrations** - Connect to YouTube, Notion, Twitter, Airtable, and more
- 🔐 **Secure OAuth2 Authentication** - Built-in authentication for all connected services
- ⚡ **Real-Time Updates** - Live status updates for agent connections and execution
- 📊 **Agent Insights** - Monitor performance and track agent activities
- 🌐 **Globally Scalable** - Built on modern serverless architecture
- 💾 **TrySpaces** - Save and share your agent configurations
- 📱 **TryFeed** - Community-driven feed showcasing what others are building

> **Note:** This repository contains the foundational framework for the Tryliate platform. Core business logic and proprietary algorithms are maintained separately to protect intellectual property.

---

## 🛠️ Tech Stack

Tryliate is built with a modern, scalable technology stack optimized for performance and developer experience:

### Frontend
- **Next.js 15** (App Router) - React framework with server-side rendering
- **Tailwind CSS** - Utility-first CSS framework
- **shadcn/ui** - Re-usable component library
- **React Query** - Data fetching and state management
- **Zustand** - Lightweight state management

### Backend & Infrastructure
- **Supabase** - PostgreSQL database with real-time capabilities
- **Supabase Auth** - Authentication with OAuth2 support (Google, GitHub, Discord)
- **Next.js API Routes** - Serverless API endpoints
- **Vercel** - Global edge deployment and hosting

### AI & Integration Layer
- **Perplexity API** (configurable) - Primary AI inference engine
- **OpenAI API** (optional) - Alternative AI provider
- **Custom API Connectors** - YouTube, Notion, Twitter, Airtable integrations
- **WebSockets** - Real-time communication for live updates

### Monitoring & Analytics
- **Vercel Analytics** - Performance monitoring
- **Logflare** - Real-time log management

### Payments (Roadmap)
- **Lemon Squeezy** / **Stripe** - Monetization and subscription management

---

## 📅 1-Week MVP Launch Roadmap

Our rapid development approach leverages GitHub Copilot Pro and VS Code to deliver a production-ready MVP in just 7 days:

### 🗓️ Day 1 - Foundation Setup
- Initialize Next.js 15 project with TypeScript
- Setup Tailwind CSS and shadcn/ui components
- Configure Supabase client
- Create base pages: `/try-spaces`, `/try-feeds`
- Implement dark crystal UI theme

### 🗓️ Day 2 - Authentication & Layout
- Implement Supabase Auth (Magic Link + OAuth)
- Build persistent sidebar navigation
- Create layout components (Build Agent, TrySpaces, TryFeed)
- Setup session management

### 🗓️ Day 3 - Agent Builder Core
- Middle Panel: Agent Overview UI
- Editable agent name and description
- Run button with loading states
- Right Panel: Connected tools display
- Database schema: `agents`, `tools_connected` tables

### 🗓️ Day 4 - Integration APIs
- `/api/connect/youtube` - YouTube OAuth2 flow
- `/api/connect/notion` - Notion API integration
- `/api/connect/twitter` - Twitter/X API setup
- Secure token storage in Supabase
- Connection status validation

### 🗓️ Day 5 - AI Integration & Steps Panel
- Integrate Perplexity/OpenAI API
- AI-powered agent overview generation
- Dynamic steps panel with AI suggestions
- Tool recommendation engine
- Prompt engineering for agent behaviors

### 🗓️ Day 6 - Community Features
- `/try-feeds` - User-generated content feed
- `/try-spaces` - Saved agent workflows
- Sharing functionality
- Public/private agent visibility

### 🗓️ Day 7 - Polish & Deploy
- UI/UX refinements
- Loading states and error handling
- Edge case testing
- Deploy to Vercel production
- Performance optimization
- Supabase edge caching configuration

---

## 💻 VS Code Local Setup Instructions

### Prerequisites

Ensure you have the following installed:
- **Node.js** 18.x or higher
- **npm** or **yarn** or **pnpm**
- **Git**
- **GitHub Copilot Pro** (recommended for accelerated development)
- **VS Code** with recommended extensions:
  - GitHub Copilot
  - ESLint
  - Prettier
  - Tailwind CSS IntelliSense

### Step 1: Clone the Repository

```bash
git clone https://github.com/VinodHatti7019/Tryliate.git
cd Tryliate
```

### Step 2: Install Dependencies

```bash
npm install
# or
yarn install
# or
pnpm install
```

### Step 3: Environment Configuration

Create a `.env.local` file in the root directory:

```env
# Supabase Configuration
NEXT_PUBLIC_SUPABASE_URL=your_supabase_project_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_service_role_key

# AI API Keys (Choose one or configure multiple)
PERPLEXITY_API_KEY=your_perplexity_api_key
OPENAI_API_KEY=your_openai_api_key  # Optional

# OAuth Credentials (Add as you integrate services)
YOUTUBE_CLIENT_ID=your_youtube_client_id
YOUTUBE_CLIENT_SECRET=your_youtube_client_secret
NOTION_CLIENT_ID=your_notion_client_id
NOTION_CLIENT_SECRET=your_notion_client_secret
TWITTER_CLIENT_ID=your_twitter_client_id
TWITTER_CLIENT_SECRET=your_twitter_client_secret

# Application URLs
NEXT_PUBLIC_APP_URL=http://localhost:3000
```

### Step 4: Setup Supabase

1. Create a new project at [supabase.com](https://supabase.com)
2. Run database migrations (SQL scripts will be added to `/supabase/migrations`)
3. Configure Authentication providers in Supabase Dashboard

### Step 5: Run Development Server

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### Step 6: GitHub Copilot Development Tips

**Maximize Copilot Efficiency:**
- Write clear comments describing what you want to build
- Use descriptive function and variable names
- Let Copilot suggest boilerplate for API routes and components
- Review and refine AI-generated code for best practices
- Use Copilot Chat for architectural questions

**Example Copilot Prompts:**
```javascript
// Create a server action to connect YouTube OAuth2
// This should handle the OAuth flow and store tokens securely in Supabase

// Build a React component for displaying connected integrations
// Should show service logo, connection status, and disconnect button
```

---

## 📁 Project Structure

```
Tryliate/
├── app/                    # Next.js 15 App Router
│   ├── (auth)/            # Authentication routes
│   ├── (dashboard)/       # Protected dashboard routes
│   ├── api/               # API routes & server actions
│   ├── try-spaces/        # TrySpaces feature
│   └── try-feeds/         # TryFeed community feature
├── components/            # Reusable React components
│   ├── ui/               # shadcn/ui components
│   ├── agent/            # Agent builder components
│   └── shared/           # Shared components
├── lib/                   # Utility functions & configurations
│   ├── supabase/         # Supabase client setup
│   ├── api/              # API helpers
│   └── hooks/            # Custom React hooks
├── public/                # Static assets
├── supabase/              # Supabase migrations & types
├── types/                 # TypeScript type definitions
└── README.md             # This file
```

---

## 🔒 Security & Privacy

- All OAuth tokens are encrypted and stored securely in Supabase
- Row Level Security (RLS) policies protect user data
- API routes validate authentication before processing requests
- Environment variables are never committed to the repository
- Regular security audits and dependency updates

> **Important:** This codebase does not include proprietary business logic or internal product strategies. Core algorithms and unique features are maintained in private repositories.

---

## 🤝 Contributing

We welcome contributions! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🌟 Acknowledgments

- Built with ❤️ by [Vinod Hatti](https://github.com/VinodHatti7019)
- Powered by Next.js, Supabase, and modern web technologies
- Accelerated by GitHub Copilot Pro

---

## 📞 Contact & Links

- **Website:** [tryliate.com](https://tryliate.com)
- **LinkedIn:** [Vinod Hatti](https://www.linkedin.com/in/vinodhatti/)
- **GitHub:** [@VinodHatti7019](https://github.com/VinodHatti7019)

---

<p align="center">
  <strong>⚡ Start building intelligent AI agents today with Tryliate!</strong>
</p>
