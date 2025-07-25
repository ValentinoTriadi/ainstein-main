# 🧠 Ainstein - AI-Powered Educational Platform

Ainstein is a comprehensive AI-driven educational platform that revolutionizes learning through intelligent content processing, personalized study materials, and interactive learning experiences. Named after Albert Einstein, this platform combines cutting-edge AI technology with modern educational methodologies to create an adaptive learning environment.

The platform consists of three main components: an AI processing pipeline for content understanding, a robust backend API for study management, and a cross-platform mobile application for seamless learning experiences.

---

## 🤖 Ainstein AI - RAG Content Processing Pipeline

### Overview
The AI component serves as the intelligent core of the platform, implementing a sophisticated Retrieval-Augmented Generation (RAG) system. This pipeline processes educational content, creates vector embeddings, and enables semantic search capabilities for enhanced learning experiences. Built specifically for handling Manim documentation and source code, it provides contextual responses to educational queries.

### Tech Stack
- **Framework**: FastAPI for high-performance REST API
- **Vector Database**: ChromaDB for persistent vector storage
- **AI/ML**: LlamaIndex for advanced document retrieval and processing
- **Language Models**: OpenAI GPT integration for intelligent responses
- **Data Processing**: LangChain for document processing pipelines
- **Infrastructure**: Docker containerization with docker-compose
- **Logging**: Comprehensive logging system for monitoring
- **Language**: Python 3.13+

### How to Run

#### Prerequisites
- Python 3.13+
- OpenAI API key
- Docker (optional)

#### Local Development
```bash
# Navigate to AI directory
cd ainstein-ai

# Setup environment
chmod +x setup.sh
./setup.sh

# Configure environment variables
cp .env.example .env
# Edit .env and add your OpenAI API key
OPENAI_API_KEY=your_key_here

# Add your educational documents
cp -r /path/to/docs ./docs/
cp -r /path/to/source ./src/

# Run the API server
python -m app.main
```

#### Docker Deployment
```bash
cd ainstein-ai
docker-compose up --build
```

#### Available Endpoints
- `GET /` - Root endpoint and API documentation
- `POST /query` - Main RAG query for educational content
- `POST /rebuild-index` - Refresh vector index
- `GET /search` - Simple document search
- `GET /health` - System health check

---

## 🚀 Ainstein Backend - Study Management API

### Overview
The backend serves as the central hub for all educational data and user interactions. Built with modern TypeScript and Hono framework, it provides a comprehensive API for managing study kits, videos, flashcards, quizzes, and user conversations. The system features robust authentication, database management with PostgreSQL, and seamless integration with the AI pipeline for enhanced learning experiences.

### Tech Stack
- **Framework**: Hono.js for lightweight, fast API development
- **Runtime**: Bun for high-performance JavaScript execution
- **Database**: PostgreSQL with Drizzle ORM for type-safe queries
- **Authentication**: Better Auth with bcrypt for secure user management
- **AI Integration**: OpenAI SDK and AI SDK for intelligent features
- **API Documentation**: Swagger UI and Scalar for comprehensive API docs
- **Language**: TypeScript for enhanced developer experience
- **Validation**: Zod for runtime type checking and validation
- **Cloud**: AWS Lambda integration ready

### How to Run

#### Prerequisites
- Bun runtime installed
- PostgreSQL database
- Environment variables configured

#### Local Development
```bash
# Navigate to backend directory
cd ainstein-backend

# Install dependencies
bun install

# Setup environment variables
cp .env.example .env
# Configure database URL, JWT secrets, and API keys

# Generate and run database migrations
bun run db:generate
bun run db:migrate

# Start development server
bun run dev
```

#### Production Deployment
```bash
# Build and start
bun run start

# Database management
bun run db:studio  # Open database studio
```

#### Key Features
- RESTful API with OpenAPI specification
- Study kit and group management
- Video content processing and metadata
- Flashcard and quiz generation
- Real-time conversation handling
- User authentication and session management

---

## 📱 Ainstein Mobile - Cross-Platform Learning App

### Overview
The mobile application provides a seamless, intuitive learning experience across iOS, Android, and web platforms. Built with React Native and Expo, it offers a modern, responsive interface for accessing study materials, interacting with AI tutors, watching educational videos, and tracking learning progress. The app features a beautiful, Einstein-inspired design with advanced UI components and smooth animations.

### Tech Stack
- **Framework**: React Native with Expo SDK 53
- **Routing**: Expo Router for file-based navigation
- **UI Library**: Gluestack UI with NativeWind for modern styling
- **Styling**: Tailwind CSS with React Native CSS Interop
- **State Management**: Zustand for global state handling
- **Authentication**: Better Auth Expo integration
- **Video**: Expo AV for educational content playback
- **HTTP Client**: Axios for API communication
- **Icons**: Expo Vector Icons and Lucide React Native
- **Language**: TypeScript for type safety

### How to Run

#### Prerequisites
- Node.js 18+ and npm/yarn
- Expo CLI installed globally
- iOS Simulator (Mac) or Android Emulator
- Expo Go app (for physical device testing)

#### Local Development
```bash
# Navigate to mobile directory
cd ainstein-mobile

# Install dependencies
npm install

# Start Expo development server
npx expo start

# Platform-specific commands
npm run ios      # Start iOS simulator
npm run android  # Start Android emulator
npm run web      # Start web version
```

#### Environment Setup
```bash
# The app uses environment configuration in app.json
# Configure API endpoints:
"extra": {
  "apiUrl": "http://localhost:3000/api",  # Local development
  "authUrl": "http://localhost:3000"
}
```

#### Key Features
- Intuitive study kit browsing and management
- AI-powered chat interface for learning assistance
- Video player with educational content
- Interactive flashcards and quizzes
- Progress tracking and analytics
- Offline support for downloaded content
- Cross-platform compatibility (iOS, Android, Web)

---

## 🏗️ Project Architecture

The Ainstein platform follows a microservices architecture where each component serves a specific purpose:

1. **AI Pipeline** processes and understands educational content
2. **Backend API** manages data, users, and business logic  
3. **Mobile App** provides the user interface and experience

All components communicate through well-defined APIs and share a common authentication system for seamless user experiences.
