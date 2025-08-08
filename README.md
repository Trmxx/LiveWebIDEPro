# LiveWebIDEPro
Smart AI assistant that understands your code and project context One-click code generation for common development tasks Professional GitHub deployment workflow with visual feedback Collapsible panels for optimal workspace organization Persistent settings and improved user experience
# Overview

This is a WebIDE Pro - a professional web-based integrated development environment (IDE) that provides Monaco editor integration, live preview capabilities, GitHub integration, and advanced code editing features. The application is built as a full-stack web application with a React frontend and Express backend, designed to offer a complete development experience in the browser.

The IDE allows users to create, edit, and preview web projects with real-time updates, featuring a file explorer, Monaco code editor, live preview panel, console output, and deployment capabilities to GitHub. It's designed to be a comprehensive solution for web development with modern tooling and user experience.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture
The frontend is built with React 18 using TypeScript and modern development practices:

- **Framework**: React with TypeScript, using Vite as the build tool
- **UI Framework**: shadcn/ui components built on Radix UI primitives with Tailwind CSS for styling
- **State Management**: React Query (@tanstack/react-query) for server state management and React hooks for local state
- **Routing**: Wouter for client-side routing (lightweight alternative to React Router)
- **Code Editor**: Monaco Editor integration loaded via CDN for syntax highlighting and code editing
- **Styling**: Tailwind CSS with custom CSS variables for theming, supporting both light and dark modes

The architecture follows a component-based design with specialized IDE components:
- File Explorer for project navigation
- Monaco Editor with syntax highlighting and multi-tab support
- Preview Panel with responsive device modes
- Console Panel for output and debugging
- Toolbar with development actions and GitHub integration

## Backend Architecture
The backend uses Express.js with TypeScript in an ESM module setup:

- **Framework**: Express.js with TypeScript support
- **Data Storage**: In-memory storage implementation with interface-based design for easy database integration
- **API Design**: RESTful API endpoints for project management
- **Development Setup**: Hot reloading with tsx and Vite integration in development mode
- **Build Process**: esbuild for backend bundling with external packages

The storage layer uses an interface-based approach (`IStorage`) allowing for easy switching between in-memory storage and database implementations. Currently implements `MemStorage` for development with default project scaffolding.

## Data Management
The application uses a shared schema approach:

- **Schema Definition**: Drizzle ORM schemas with Zod validation in the shared directory
- **Database Ready**: Configured for PostgreSQL with Drizzle migrations
- **Validation**: Zod schemas for API request/response validation
- **Type Safety**: Shared TypeScript types between frontend and backend

The project structure includes users and projects tables with JSON fields for flexible file storage and settings management.

## Development Workflow
The architecture supports a modern development experience:

- **Hot Reloading**: Vite HMR for frontend and tsx for backend development
- **Type Checking**: Comprehensive TypeScript configuration with path mapping
- **Code Quality**: ESLint and Prettier integration (implied by modern setup)
- **Build Optimization**: Separate build processes for client and server with proper bundling

## File Organization
The codebase follows a monorepo structure with clear separation:

- `/client` - React frontend application
- `/server` - Express backend application  
- `/shared` - Common schemas and types
- Clear path mapping for imports with `@/` aliases

This structure promotes code reusability and maintains type safety across the full stack while keeping concerns properly separated.

# External Dependencies

## Database & ORM
- **PostgreSQL**: Primary database (configured via Drizzle but not yet implemented)
- **Drizzle ORM**: Type-safe database operations and migrations with PostgreSQL dialect
- **Neon Database**: Serverless PostgreSQL provider (@neondatabase/serverless)

## Frontend Libraries
- **React Ecosystem**: React 18, React DOM, React Query for state management
- **UI Components**: Extensive Radix UI primitives for accessible components
- **Styling**: Tailwind CSS with PostCSS, class-variance-authority for component variants
- **Code Editor**: Monaco Editor via CDN for syntax highlighting and editing
- **Utilities**: date-fns for date manipulation, clsx and tailwind-merge for conditional styling

## Backend Services
- **Web Framework**: Express.js with TypeScript support
- **Development Tools**: Vite for development server and HMR integration
- **Session Management**: connect-pg-simple for PostgreSQL session storage
- **Build Tools**: esbuild for production bundling

## Development & Build Tools
- **Build System**: Vite for frontend bundling and development server
- **TypeScript**: Full TypeScript support with strict configuration
- **Hot Reloading**: tsx for backend development with automatic restarts
- **Replit Integration**: Custom Vite plugins for Replit development environment

## GitHub Integration
The application includes GitHub deployment capabilities:
- **Octokit**: GitHub API integration for repository management
- **File Deployment**: Automated deployment of project files to GitHub repositories
- **Authentication**: GitHub token-based authentication for repository access

## Fonts & CDN Resources
- **Google Fonts**: Inter and JetBrains Mono for modern typography
- **Monaco Editor CDN**: External CDN for Monaco editor resources to reduce bundle size
