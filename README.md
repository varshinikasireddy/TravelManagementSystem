Docker Frontend Application
A React application containerized using Docker for easy development and deployment.

Prerequisites
Before you begin, ensure you have the following installed on your machine:

Docker Desktop

Node.js (for local development without Docker)

VS Code (recommended)

Project Structure
text
DockerFE/
├── dockerfile
├── package.json
├── package-lock.json
├── src/
├── public/
└── README.md
Setup Instructions
1. Clone the Repository
bash
git clone <your-repository-url>
cd DockerFE
2. Using Docker (Recommended)
Build the Docker Image
bash
docker build -t dockereximage .
Run the Application
bash
docker run -p 5173:5173 dockereximage npm run dev -- --host
Alternative run command with detached mode:
bash
docker run -d -p 5173:5173 --name react-app dockereximage
3. Access the Application
Once running, open your browser and navigate to:

text
http://localhost:5173
Development
Without Docker (Local Development)
bash
npm install
npm run dev
Docker Commands Reference
Command	Description
docker build -t dockereximage .	Build Docker image
docker images	List all Docker images
docker run -p 5173:5173 dockereximage	Run the container
docker ps	List running containers
docker stop <container_id>	Stop a running container
docker rm <container_id>	Remove a container
docker rmi dockereximage	Remove the image
Dockerfile Details
The Dockerfile uses:

Node.js 20 as base image

Port 5173 exposed for the development server

Multi-stage build for optimized image size

Automatic dependency installation

Features
✅ React application with Vite

✅ Docker containerization

✅ Hot-reload development server

✅ Optimized build process

Troubleshooting
Common Issues
Port already in use:

bash
# Use a different port
docker run -p 5174:5173 dockereximage
Docker build fails:

Ensure Docker Desktop is running

Check internet connection for downloading dependencies

Container not starting:

bash
# Check container logs
docker logs <container_id>
Contributing
Fork the repository

Create your feature branch (git checkout -b feature/AmazingFeature)

Commit your changes (git commit -m 'Add some AmazingFeature')

Push to the branch (git push origin feature/AmazingFeature)

Open a Pull Request