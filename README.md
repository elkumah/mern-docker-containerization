# MERN Stack Containerization Project

This project demonstrates the full-stack containerization of a MERN (MongoDB, Express, React, Node) application. The primary goal was to create a reproducible, scalable development environment using Docker and Docker Compose, eliminating the "it works on my machine" problem

## **Technical Highlights**

### **Technology Stack**

| Category                    | Technologies                                                 |
| --------------------------- | ------------------------------------------------------------ |
| **Frontend**                | React 18, Vite, Tailwind CSS, React Router, Cypress          |
| **Backend**                 | Node.js, Express.js, REST APIs, CORS                         |
| **Database**                | MongoDB                                                      |
| **DevOps/Containerization** | Docker, Docker Compose, Volume Management, Custom Networking |
| **Testing**                 | Cypress E2E Testing Framework                                |
| **Build Tools**             | Vite, PostCSS, ESLint                                        |

## **Key Professional Competencies Demonstrated**

**Docker Containerization** - Multi-container orchestration with custom Dockerfile optimization  
**Container Orchestration** - Docker Compose service management, networking, and volume persistence  
**Microservices Architecture** - Isolated services with proper dependency management  
 **Database Management** - MongoDB containerization with persistent data storage

**Infrastructure as Code** - Docker Compose configuration for reproducible environments

## **Project Architecture**

```
MERN-docker-compose/
├── docker-compose.yaml          # Orchestration & service configuration
├── mern/
│   ├── backend/                 # Node.js + Express REST API
│   │   ├── Dockerfile           # Backend container image
│   │   ├── server.js            # Express server entry point
│   │   ├── package.json         # Dependencies management
│   │   ├── db/
│   │   │   └── connection.js    # MongoDB connection logic
│   │   └── routes/
│   │       └── record.js        # API routes & CRUD operations
│   │
│   └── frontend/                # React + Vite SPA
│       ├── Dockerfile           # Frontend container image
│       ├── package.json         # React dependencies
│       ├── vite.config.js       # Vite bundler configuration
│       ├── tailwind.config.js   # Tailwind CSS customization
│       ├── cypress.json         # E2E testing configuration
│       ├── src/
│       │   ├── App.jsx          # Main React component
│       │   ├── components/      # Reusable React components
│       │   │   ├── Navbar.jsx   # Navigation component
│       │   │   ├── Record.jsx   # Record display component
│       │   │   └── RecordList.jsx # List management component
│       │   └── main.jsx         # React entry point
│       └── cypress/             # E2E test suite
│           └── integration/
│               └── endToEnd.spec.js
```

## **Container Services**

| Service      | Port  | Environment    | Purpose                                  |
| ------------ | ----- | -------------- | ---------------------------------------- |
| **backend**  | 5050  | Docker Network | Express REST API server                  |
| **frontend** | 5173  | Docker Network | React Vite development/production server |
| **mongodb**  | 27017 | Docker Network | NoSQL database with persistent volumes   |

## **Quick Start Guide**

### **Prerequisites**

- Docker & Docker Compose installed
- Git

### **Installation & Running**

1. **Clone and navigate to project:**

   ```bash
   git clone https://github.com/your-username/mern-containerization-project.git
   cd mern-containerization-project
   ```

2. **Start all services:**

   ```bash
   docker-compose up -d --build
   ```

3. **Access applications:**
   - Frontend: http://localhost:5173
   - API: http://localhost:5050
   - MongoDB: mongodb://localhost:27017

4. **View logs:**

   ```bash
   docker compose logs -f
   ```

5. **Stop services:**
   ```bash
   docker compose down
   ```

### **Local Development (Without Docker)**

If you prefer running locally:

**Backend:**

```bash
cd mern/backend
npm install
npm start
```

**Frontend:**

```bash
cd mern/frontend
npm install
npm run dev
```

## **Development Commands**

| Command                                    | Purpose                            |
| ------------------------------------------ | ---------------------------------- |
| `docker compose up -d`                     | Start all services in background   |
| `docker compose logs -f`                   | Stream logs from all services      |
| `docker compose exec backend npm start`    | Restart backend service            |
| `docker compose exec frontend npm run dev` | Rebuild frontend                   |
| `docker compose down -v`                   | Stop all services & remove volumes |

## **Deployment Ready**

This project can be easily deployed to:

- Docker Swarm
- Kubernetes clusters
- Cloud platforms (AWS ECS, Google Cloud Run, Azure Container Instances)
- Development/staging/production environments with minimal configuration changes
