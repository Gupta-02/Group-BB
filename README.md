# 🎬 YouPac AI - YouTube Content Creation Assistant

<div align="center">

[![React Router](https://img.shields.io/badge/React%20Router-v7-61DAFB?logo=react&logoColor=white)](https://reactrouter.com)
[![Convex](https://img.shields.io/badge/Convex-Real%20Time-6B5B95)](https://www.convex.dev)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Vercel](https://img.shields.io/badge/Deployed%20on-Vercel-000000?logo=vercel&logoColor=white)](https://vercel.com)

**Transform Your YouTube Workflow with AI-Powered Content Generation**

Generate SEO-optimized titles, comprehensive descriptions, stunning thumbnails, and viral-ready social media posts in minutes.

[🚀 Get Started](#getting-started) • [📖 Documentation](#documentation) • [🏗️ Architecture](#architecture) • [🤝 Contributing](#contributing)

</div>

---

## 📋 Abstract

**YouPac AI** is a cutting-edge, AI-powered platform designed to revolutionize YouTube content creation. By leveraging advanced artificial intelligence, real-time collaboration features, and modern web technologies, YouPac AI empowers creators to automate the most time-consuming aspects of content marketing—from title optimization to thumbnail generation.

Built on **React Router v7** for full-stack capabilities, **Convex** for real-time database synchronization, and **OpenAI** for intelligent content generation, YouPac AI combines a beautiful, intuitive user interface with powerful backend processing. Upload your video once, and let our AI agents work their magic to generate multiple variations of titles, descriptions, and social media content tailored to your channel's unique voice and audience.

With drag-and-drop workflow canvas, smart AI chat integration, and collaborative sharing features, YouPac AI reduces content creation time from hours to minutes while maintaining professional quality across all platforms.

---

## ✨ Core Features

### 🎯 Video Upload & Processing
- Upload videos up to **1GB** with automatic transcription
- AI-powered video analysis and metadata extraction
- Support for multiple video formats

### 🤖 AI Content Generation
Generate optimized content with our intelligent AI agents:
- **📝 Title Agent** - Catchy, SEO-optimized video titles
- **📄 Description Agent** - Comprehensive, engaging descriptions
- **🖼️ Thumbnail Agent** - Visual concepts powered by DALL-E 3
- **🐦 Social Media Agent** - Twitter/X threads for promotion

### 🎨 Interactive Canvas
- Drag-and-drop visual workflow interface
- Real-time node connections and validation
- Auto-save every 5 seconds
- Visual content management

### 💬 Smart Chat Integration
- Chat with specific AI agents using @mentions
- Request modifications and regenerations
- Context-aware AI responses based on your video

### 👁️ Content Preview
- Live YouTube-style preview
- Twitter/X thread preview
- What-you-see-is-what-you-get editing

### 🔗 Collaboration
- Share read-only canvas views with team members
- Real-time synchronization
- Access control management

### 🔐 Advanced Security
- Secure authentication with Clerk
- Role-based access control
- Data encryption in transit and at rest

---

## 🛠️ Tech Stack

### Frontend
| Technology | Purpose |
|-----------|---------|
| **React Router v7** | Full-stack React framework with SSR |
| **React Flow** | Interactive canvas for visual workflows |
| **TailwindCSS v4** | Utility-first CSS framework |
| **shadcn/ui** | Modern component library with Radix UI |
| **Lucide React** | Beautiful icon library |
| **Sonner** | Toast notifications |

### Backend & Services
| Technology | Purpose |
|-----------|---------|
| **Convex** | Real-time database & serverless functions |
| **Clerk** | Authentication & user management |
| **OpenAI** | GPT-4 & DALL-E 3 integration |
| **ElevenLabs** | Speech-to-text transcription |
| **FFmpeg** | Video processing & audio extraction |

### DevOps & Deployment
| Technology | Purpose |
|-----------|---------|
| **Vite** | Lightning-fast build tool |
| **TypeScript** | End-to-end type safety |
| **Vercel** | Deployment platform |
| **Docker** | Containerization |

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────────────────┐
│                          CLIENT LAYER (Browser)                         │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                           │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐      │
│  │  Homepage/Auth   │  │   Dashboard      │  │  Canvas Editor   │      │
│  │                  │  │  - Projects      │  │  - Visual Flow   │      │
│  │  - Landing Page  │  │  - Settings      │  │  - Chat Panel    │      │
│  │  - Sign In/Up    │  │  - Profile       │  │  - Preview Pane  │      │
│  └────────┬─────────┘  └────────┬─────────┘  └────────┬─────────┘      │
│           │                     │                     │                 │
│           └─────────────────────┴─────────────────────┘                 │
│                          ▼                                               │
│           ┌────────────────────────────────────┐                        │
│           │    React Router v7 (Full-Stack)    │                        │
│           │  - Client-side Routing             │                        │
│           │  - Server-side Rendering (SSR)     │                        │
│           │  - API Route Handlers              │                        │
│           └────────────┬───────────────────────┘                        │
│                        │                                                 │
└────────────────────────┼─────────────────────────────────────────────────┘
                         │
                         ▼
    ┌────────────────────────────────────────────────────────┐
    │         AUTHENTICATION LAYER                            │
    ├────────────────────────────────────────────────────────┤
    │                                                          │
    │  ┌──────────────────────────────────────────────────┐  │
    │  │         Clerk Authentication                     │  │
    │  │  - User Management & Sessions                    │  │
    │  │  - JWT Token Generation                          │  │
    │  │  - Role-Based Access Control                     │  │
    │  └──────────────────────────────────────────────────┘  │
    │                                                          │
    └────────────────────┬─────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                    REAL-TIME DATA LAYER (Convex)                        │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                           │
│  ┌────────────────────┐  ┌─────────────────┐  ┌──────────────────┐    │
│  │   Projects DB      │  │   Videos DB     │  │  Canvas DB       │    │
│  │  - Project Meta    │  │  - Video Info   │  │  - Nodes         │    │
│  │  - Ownership       │  │  - Status       │  │  - Edges         │    │
│  │  - Timestamps      │  │  - URLs         │  │  - Layout        │    │
│  └────────┬───────────┘  └────────┬────────┘  └────────┬─────────┘    │
│           │                       │                    │               │
│           └───────────────────────┼────────────────────┘               │
│                                   ▼                                     │
│           ┌──────────────────────────────────────┐                     │
│           │   WebSocket Real-time Sync          │                     │
│           │  - Live Collaboration               │                     │
│           │  - Auto-save Every 5s               │                     │
│           │  - Instant Updates Across Clients   │                     │
│           └────────────┬─────────────────────────┘                     │
│                        │                                                │
└────────────────────────┼─────────────────────────────────────────────────┘
                         │
                         ▼
    ┌────────────────────────────────────────────────────────┐
    │         SERVERLESS BACKEND (Convex Functions)          │
    ├────────────────────────────────────────────────────────┤
    │                                                          │
    │  ┌──────────────────────────────────────────────────┐  │
    │  │      Video Processing Pipeline                   │  │
    │  │  - Upload Handler                               │  │
    │  │  - Audio Extraction (FFmpeg)                    │  │
    │  │  - Metadata Extraction                          │  │
    │  └──────────────────────────────────────────────────┘  │
    │                                                          │
    │  ┌──────────────────────────────────────────────────┐  │
    │  │      Transcription Service                       │  │
    │  │  - ElevenLabs Integration                       │  │
    │  │  - Text Processing & Chunking                   │  │
    │  │  - Storage in Convex DB                         │  │
    │  └──────────────────────────────────────────────────┘  │
    │                                                          │
    │  ┌──────────────────────────────────────────────────┐  │
    │  │      AI Agent Orchestration                      │  │
    │  │  - Distribute tasks to AI engines                │  │
    │  │  - Manage agent queue & workflows                │  │
    │  │  - Handle regeneration requests                  │  │
    │  └──────────────────────────────────────────────────┘  │
    │                                                          │
    │  ┌──────────────────────────────────────────────────┐  │
    │  │      Content Management                          │  │
    │  │  - Canvas CRUD operations                        │  │
    │  │  - Share token generation                        │  │
    │  │  - Export functionality                          │  │
    │  └──────────────────────────────────────────────────┘  │
    │                                                          │
    └────────────────────┬─────────────────────────────────────┘
                         │
         ┌───────────────┼───────────────┐
         ▼               ▼               ▼
    ┌─────────┐    ┌──────────┐    ┌─────────┐
    │ OpenAI  │    │  DALL-E  │    │Eleven   │
    │ GPT-4   │    │   v3     │    │ Labs    │
    │         │    │          │    │         │
    │• Title  │    │• Thumbs  │    │• Speech │
    │• Desc   │    │• Concepts│    │  to     │
    │• Social │    │• Images  │    │  Text   │
    └─────────┘    └──────────┘    └─────────┘

                    ▲
                    │
        ┌───────────┴───────────┐
        ▼                       ▼
    ┌──────────┐          ┌──────────┐
    │ Storage  │          │ Analytics│
    │          │          │          │
    │• Vectors │          │• Logging │
    │• Videos  │          │• Metrics │
    │• Assets  │          │• Errors  │
    └──────────┘          └──────────┘

```

---

## 📊 Data Flow

```
User Upload Video
    │
    ├─→ [Validation] → File size, format check
    │
    ├─→ [Extraction] → Audio extraction (FFmpeg)
    │
    ├─→ [Transcription] → ElevenLabs API → Store in Convex DB
    │
    ├─→ [Analysis] → Extract metadata (duration, resolution, etc.)
    │
    ├─→ [AI Generation] → Dispatch to AI Agents
    │   │
    │   ├─→ Title Agent (GPT-4) → Generate titles
    │   ├─→ Description Agent (GPT-4) → Generate descriptions
    │   ├─→ Thumbnail Agent (DALL-E 3) → Generate images
    │   └─→ Social Agent (GPT-4) → Generate tweets
    │
    ├─→ [Canvas Creation] → Create visual workflow
    │
    └─→ [User Review] → Chat refinement → Export/Share
```

---

## 🚀 Getting Started

### Prerequisites

Before you begin, ensure you have:
- **Node.js** 18+ installed
- **npm** or **yarn** package manager
- Git for version control

### Required Accounts

- [Clerk](https://clerk.com) - Authentication
- [Convex](https://www.convex.dev) - Database
- [OpenAI](https://platform.openai.com) - API access
- [ElevenLabs](https://elevenlabs.io) - Transcription API

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/youpac-ai.git
   cd youpac-ai
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure environment variables**
   ```bash
   cp .env.example .env.local
   ```

4. **Set up your `.env.local`**
   ```env
   # Convex Configuration
   CONVEX_DEPLOYMENT=your_convex_deployment_here
   VITE_CONVEX_URL=your_convex_url_here

   # Clerk Authentication
   VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key_here
   CLERK_SECRET_KEY=your_clerk_secret_key_here

   # OpenAI Configuration
   OPENAI_API_KEY=your_openai_api_key_here

   # ElevenLabs Configuration
   ELEVENLABS_API_KEY=your_elevenlabs_api_key_here

   # Frontend URL
   FRONTEND_URL=http://localhost:5173
   ```

5. **Initialize Convex**
   ```bash
   npx convex dev
   ```

6. **Set Convex environment variables**
   - Go to your Convex dashboard
   - Add these secrets:
     - `OPENAI_API_KEY`
     - `ELEVENLABS_API_KEY`

### Development

Start the development server with hot module replacement:
```bash
npm run dev
```

Your application will be available at **http://localhost:5173**

### Building for Production

Create an optimized production build:
```bash
npm run build
```

Start the production server:
```bash
npm run start
```

---

## 📦 Project Structure

```
youpac-ai/
├── app/
│   ├── components/
│   │   ├── ui/                 # shadcn/ui components
│   │   ├── canvas/             # Canvas and node components
│   │   ├── homepage/           # Landing page sections
│   │   ├── dashboard/          # Dashboard layout
│   │   └── preview/            # YouTube/Twitter previews
│   ├── routes/
│   │   ├── dashboard/          # Protected routes
│   │   ├── canvas/             # Canvas editor
│   │   ├── share/              # Shared canvas view
│   │   └── auth/               # Authentication pages
│   ├── lib/
│   │   ├── api/                # API helpers
│   │   ├── utils/              # Utility functions
│   │   └── hooks/              # React hooks
│   └── styles/                 # Global styles
├── convex/
│   ├── schema.ts               # Database schema
│   ├── videos.ts               # Video operations
│   ├── projects.ts             # Project management
│   ├── agents.ts               # AI agent functions
│   ├── aiHackathon.ts          # AI generation
│   └── http.ts                 # HTTP endpoints
├── public/                     # Static assets
├── docs/                       # Documentation
├── package.json
├── tsconfig.json
├── tailwind.config.ts
├── vite.config.ts
└── react-router.config.ts
```

---

## 🚢 Deployment

### Vercel (Recommended)

1. **Push your code to GitHub**
2. **Connect your repository to Vercel**
3. **Add environment variables in Vercel dashboard**
4. **Deploy automatically on push**

The `react-router.config.ts` includes the Vercel preset for seamless deployment.

### Docker Deployment

```bash
# Build the Docker image
docker build -t youpac-ai .

# Run the container
docker run -p 3000:3000 youpac-ai
```

Deploy to any Docker-compatible platform:
- AWS ECS
- Google Cloud Run
- Azure Container Apps
- Digital Ocean App Platform
- Fly.io
- Railway

### Output Structure

```
build/
├── client/    # Static assets & client bundle
└── server/    # Server-side code & API routes
```

---

## 📚 Documentation

### How It Works

#### 1️⃣ Upload Your Video
- Upload any video file (up to 1GB)
- Automatic transcription using ElevenLabs
- Extract metadata (duration, resolution, format)

#### 2️⃣ Generate Content
- AI agents analyze your video and transcription
- Generate optimized titles, descriptions, thumbnails
- Each agent can be regenerated individually

#### 3️⃣ Refine with Chat
- Use @mentions to chat with specific agents
- Request changes or regenerate content
- AI understands context from your video

#### 4️⃣ Preview & Export
- Preview on YouTube and Twitter/X
- Copy content to clipboard
- Export as markdown files
- Share canvas with collaborators

### API Endpoints

All API endpoints are handled through Convex functions. Key operations:

- **Video Upload** - Handle file upload and processing
- **Generate Content** - Trigger AI agent content generation
- **Canvas Operations** - CRUD for canvas and nodes
- **Share Management** - Create and manage share tokens
- **Chat** - Real-time messaging with AI agents

---

## 🔐 Environment Variables

### Required

```env
# Clerk
VITE_CLERK_PUBLISHABLE_KEY=pk_test_...
CLERK_SECRET_KEY=sk_test_...

# Convex
VITE_CONVEX_URL=https://...
CONVEX_DEPLOYMENT=...

# Frontend
FRONTEND_URL=http://localhost:5173
```

### Convex Dashboard (Server-side)

```env
OPENAI_API_KEY=sk-...
ELEVENLABS_API_KEY=...
```

---

## 🎯 Key Routes

| Route | Purpose |
|-------|---------|
| `/` | Homepage with features overview |
| `/sign-in` | User authentication |
| `/sign-up` | User registration |
| `/dashboard` | Projects dashboard |
| `/dashboard/settings` | Profile configuration |
| `/canvas/:projectId` | Interactive content canvas |
| `/share/:shareId` | Read-only shared canvas |

---

## 📝 npm Scripts

```bash
# Development
npm run dev          # Start dev server with Convex

# Building
npm run build        # Build for production
npm run start        # Start production server

# Quality Assurance
npm run typecheck    # Run TypeScript checks
npm run lint         # Run ESLint
npm run format       # Format code with Prettier

# Convex
npm run convex:deploy  # Deploy Convex functions
```

---

## 🤝 Contributing

We welcome contributions from the community! Here's how to get involved:

1. **Fork the repository**
2. **Create your feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Commit your changes**
   ```bash
   git commit -m 'Add amazing feature'
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```
5. **Open a Pull Request**

### Development Guidelines

- Write clear, descriptive commit messages
- Follow the existing code style
- Add tests for new features
- Update documentation as needed
- Ensure TypeScript types are correct

---

## 🗺️ Roadmap

- [ ] YouTube URL import support
- [ ] Batch export functionality
- [ ] Team collaboration features
- [ ] Analytics integration & dashboard
- [ ] Support for more social media platforms (TikTok, Instagram)
- [ ] Custom AI prompt templates
- [ ] Video trimming and editing tools
- [ ] Advanced thumbnail editor
- [ ] API for third-party integrations
- [ ] Mobile app support

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 💬 Support & Community

- 📧 **Email**: support@youpac-ai.com
- 💬 **Discord**: [Join our community](https://discord.gg/youpac-ai)
- 🐙 **GitHub Issues**: [Report bugs or request features](https://github.com/yourusername/youpac-ai/issues)
- 📖 **Documentation**: [Read the full docs](https://docs.youpac-ai.com)

---

## 🙏 Acknowledgments

- [React Router](https://reactrouter.com) - Modern full-stack framework
- [Convex](https://www.convex.dev) - Real-time database
- [OpenAI](https://openai.com) - AI models
- [ElevenLabs](https://elevenlabs.io) - Speech technology
- [Vercel](https://vercel.com) - Deployment platform
- All open-source contributors

---

<div align="center">

**Made with ❤️ by the YouPac AI Team**

[⭐ Star us on GitHub](https://github.com/yourusername/youpac-ai) • [🐦 Follow on Twitter](https://twitter.com/youpac_ai)

</div>
