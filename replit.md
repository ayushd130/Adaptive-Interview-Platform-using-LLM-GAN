# Overview

Interview Prep AI is a comprehensive interview preparation platform that leverages artificial intelligence to help users practice and improve their interview skills. The application combines LLM-powered question generation, real-time face analysis, speech recognition, and detailed analytics to provide a complete interview simulation experience. The platform supports both technical and non-technical interview types, offering personalized feedback and performance tracking to help users identify strengths and areas for improvement.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Backend Architecture
The application uses Flask as the web framework with SQLAlchemy for database operations. The backend follows a traditional MVC pattern with clear separation of concerns:

- **Flask Application Structure**: Core application logic in `app.py` with modular route handling in `routes.py`
- **Database Layer**: SQLAlchemy ORM with declarative base model for clean database interactions
- **Authentication**: Flask-Login integration for user session management and route protection
- **Configuration Management**: Environment-based configuration for database connections and API keys

## Database Design
The database schema supports a comprehensive interview tracking system:

- **User Management**: Core user table with authentication and profile information
- **Interview Sessions**: Hierarchical structure linking users to interviews to individual questions
- **Analytics Storage**: Dedicated tables for performance metrics and face analysis data
- **Question Management**: Flexible question storage supporting different types and difficulty levels

## AI Integration Architecture
The platform integrates multiple AI services for enhanced functionality:

- **Gemini LLM Service**: Primary AI engine for question generation and response analysis using Google's Gemini API
- **GAN Service**: Mock implementation for question diversity enhancement (production-ready interface for future GAN integration)
- **Face Analysis**: Client-side face detection using browser APIs for real-time emotion and engagement tracking
- **Speech Recognition**: Browser-based speech-to-text for answer transcription and analysis

## Frontend Architecture
The frontend uses a responsive design approach with modern web technologies:

- **Template Engine**: Jinja2 templating with Bootstrap for responsive UI components
- **Real-time Features**: JavaScript modules for webcam access, audio recording, and live analysis
- **Chart Visualization**: Chart.js integration for analytics dashboard and performance metrics
- **Progressive Enhancement**: Graceful degradation for browsers without advanced API support

## Security and Session Management
- **Password Security**: Werkzeug password hashing for secure credential storage
- **Session Handling**: Flask session management with secure secret key configuration
- **Proxy Support**: ProxyFix middleware for deployment behind reverse proxies
- **Database Security**: Connection pooling and ping mechanisms for reliable database connections

# External Dependencies

## AI and Machine Learning Services
- **Google Gemini API**: Primary LLM service for question generation and response analysis
- **Browser Face Detection API**: Native browser APIs for real-time face analysis and emotion detection
- **Web Speech API**: Browser-based speech recognition for answer transcription

## Database and Storage
- **PostgreSQL**: Primary database for user data, interview sessions, and analytics (configurable via DATABASE_URL)
- **SQLAlchemy**: ORM layer with connection pooling and health monitoring
- **File Storage**: Local file system for audio recordings and user uploads

## Frontend Libraries and Frameworks
- **Bootstrap**: UI framework with dark theme support for responsive design
- **Font Awesome**: Icon library for consistent visual elements
- **Chart.js**: JavaScript charting library for analytics visualization
- **MediaRecorder API**: Browser API for audio/video recording capabilities

## Authentication and Security
- **Flask-Login**: User session management and authentication flows
- **Werkzeug**: Security utilities for password hashing and middleware support

## Development and Deployment
- **Flask Development Server**: Built-in server for development and testing
- **Replit Environment**: Optimized for Replit deployment with environment variable configuration