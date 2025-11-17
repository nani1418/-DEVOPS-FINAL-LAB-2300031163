# Car Rental Management System - Frontend

React-based frontend for the Car Rental Management System with Docker support.

## Prerequisites

- Docker & Docker Compose installed
- Or Node.js 18+ for local development

## Quick Start - Single Command Deployment

### Using Docker Compose (Recommended for Admin Team)

**Single command to deploy:**

\\\ash
docker-compose up --build
\\\

This will:
1. Build the Docker image
2. Install dependencies
3. Build the React application
4. Start the production server on port 5173

### Access the Application

Open your browser and navigate to: **http://localhost:5173**

## Alternative Commands

### Run in background
\\\ash
docker-compose up -d --build
\\\

### View logs
\\\ash
docker-compose logs -f
\\\

### Stop the application
\\\ash
docker-compose down
\\\

### Rebuild without cache
\\\ash
docker-compose up --build --no-cache
\\\

## Local Development Setup

### Install dependencies
\\\ash
npm install
\\\

### Run development server
\\\ash
npm run dev
\\\

Server runs on http://localhost:5173

### Build for production
\\\ash
npm run build
\\\

### Preview production build
\\\ash
npm run preview
\\\

## Docker Configuration

### docker-compose.yml
- **Service**: carrental-frontend-app
- **Port**: 5173
- **Network**: carrental-network (for multi-container apps)
- **Health Check**: Automatic container health monitoring
- **Restart Policy**: unless-stopped (auto-restart on failure)

### Dockerfile Features
- Multi-stage build for optimized image size
- Alpine Linux for minimal overhead
- Production-ready with 'serve'
- Health checks included

## Environment Variables

Create a .env file in the project root (copy from .env.example):

\\\env
VITE_API_BASE_URL=http://localhost:8080
NODE_ENV=production
\\\

## Project Structure

\\\
carrental-frontend/
 src/              # React components and pages
 public/           # Static files
 docker-compose.yml # Docker Compose configuration
 Dockerfile        # Docker build instructions
 .dockerignore      # Docker build exclusions
 .env.example       # Environment variables template
 vite.config.js    # Vite configuration
 package.json      # Project dependencies
\\\

## Technologies

- React 19.1
- Vite 7.1
- React Router 7.9
- Axios 1.12
- Docker & Docker Compose

## Troubleshooting

### Port 5173 already in use
\\\ash
docker-compose down
# or change port in docker-compose.yml
\\\

### Container won't start
\\\ash
docker-compose logs
# Check the error messages
\\\

### Clear everything and restart
\\\ash
docker-compose down -v
docker-compose up --build
\\\

## For Admin Team

**Simplified deployment workflow:**
1. Clone repository
2. Run: \docker-compose up --build\
3. Access at http://localhost:5173
4. Done! 

That's it - no manual setup required!
