# Digital Evidence System

[![Next.js](https://img.shields.io/badge/Next.js-15.5.2-black?logo=next.js)](https://nextjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue?logo=typescript)](https://www.typescriptlang.org/)
[![Supabase](https://img.shields.io/badge/Supabase-Database-green?logo=supabase)](https://supabase.com/)
[![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3.0-38B2AC?logo=tailwind-css)](https://tailwindcss.com/)
[![Radix UI](https://img.shields.io/badge/Radix_UI-Components-purple?logo=radix-ui)](https://radix-ui.com/)

Multi-tenant digital evidence management system with facial recognition, vehicle blacklist, and AI analysis capabilities.

## 🎯 Project Overview

This is a comprehensive digital evidence management system designed for law enforcement and security organizations. The system supports multiple tenants with complete data isolation, advanced AI-powered analysis, and comprehensive audit capabilities.

### Key Features

- 🏢 **Multi-Tenant Architecture** with complete data isolation
- 🔐 **Role-based Access Control** (Superadmin, Tenant Admin, Operator, Viewer)
- 👤 **Facial Recognition** with blacklist management and matching
- 🚗 **Vehicle Blacklist** with license plate recognition
- 📊 **AI-Powered Analysis** using OpenAI Vision API
- 📝 **Incident Reports** with comprehensive workflow
- 🔍 **Digital Evidence** management with chain of custody
- 📈 **Analytics & Reporting** with real-time insights
- 🛡️ **Complete Audit Trail** for compliance

## 🏗️ Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Client Apps   │────│  Next.js App    │────│   Supabase      │
│  (Subdomains)   │    │   (Middleware)  │    │   PostgreSQL    │
└─────────────────┘    └─────────────────┘    └─────────────────┘
                              │                        │
                       ┌──────▼──────┐        ┌───────▼───────┐
                       │ API Routes  │        │ Row Level     │
                       │ Edge Funcs  │        │ Security (RLS)│
                       └─────────────┘        └───────────────┘
```

### Tech Stack

- **Frontend**: Next.js 15 with App Router, TypeScript, Tailwind CSS
- **UI Components**: Radix UI primitives with custom styling
- **Backend**: Next.js API routes, Supabase Edge Functions
- **Database**: PostgreSQL with Row Level Security (RLS)
- **Authentication**: Supabase Auth with role-based permissions
- **File Storage**: Supabase Storage for evidence files
- **AI/ML**: OpenAI Vision API for image analysis
- **Testing**: Playwright, Jest for unit testing

## 🚀 Quick Start

### Prerequisites

- Node.js 18+ and npm
- Supabase account and project
- OpenAI API key (for AI features)

### Installation

```bash
# Clone the repository
git clone https://github.com/kinopsis/digital-evidence-system.git
cd digital-evidence-system

# Install dependencies
npm install

# Set up environment variables
cp .env.example .env.local
# Edit .env.local with your credentials

# Run database migrations (see database/schema.sql)
# Configure Supabase Storage buckets

# Start development server
npm run dev
```

### Environment Variables

```bash
# Supabase
NEXT_PUBLIC_SUPABASE_URL=your-supabase-url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your-anonymous-key
SUPABASE_SERVICE_ROLE_KEY=your-service-role-key

# OpenAI (for AI features)
OPENAI_API_KEY=your-openai-api-key

# NextAuth
NEXTAUTH_SECRET=your-random-secret
NEXTAUTH_URL=http://localhost:3000
```

## 🔧 Development

### Available Scripts

```bash
npm run dev          # Start development server
npm run build        # Build for production
npm start           # Start production server
npm run lint        # Run ESLint
npm run test        # Run Jest tests
npm run test:e2e    # Run Playwright E2E tests
npm run type-check  # TypeScript type checking
```

### Project Structure

```
src/
├── app/                 # Next.js App Router
│   ├── api/            # API route handlers
│   ├── dashboard/      # Main application pages
│   └── login/          # Authentication pages
├── components/         # React components
│   ├── auth/           # Authentication components
│   ├── dashboard/      # Dashboard-specific components
│   ├── evidence/       # Evidence management UI
│   ├── ui/             # Reusable UI components
│   └── ...
├── lib/                # Core utilities and configuration
├── types/              # TypeScript type definitions
├── utils/              # Utility functions
└── middleware.ts       # Next.js middleware
```

## 🔒 Security

- **Row Level Security (RLS)** for complete tenant isolation
- **Role-based permissions** with granular access control
- **Audit logging** for all system activities
- **File integrity** with SHA-256 hashing
- **Secure authentication** via Supabase Auth

## 🧪 Testing

The project includes comprehensive testing:

- **Unit Tests**: Jest with React Testing Library
- **E2E Tests**: Playwright for cross-browser testing
- **Component Tests**: Individual component testing
- **Permission Tests**: Role-based access verification

Run tests:

```bash
npm run test        # Unit tests
npm run test:e2e    # E2E tests
npm run test:watch  # Watch mode
```

## 📝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Recent Updates

- ✅ **Fixed HTML Validation Issues**: Replaced custom Select component with proper Radix UI implementation
- ✅ **Multi-tenant Administration**: Complete tenant management with user invitations
- ✅ **Audit System**: Comprehensive logging with advanced filtering and CSV export
- ✅ **Permission System**: Granular role-based access control

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Support

For support and questions, please open an issue in the GitHub repository.

---

**Built with ❤️ using Next.js, Supabase, and modern web technologies**