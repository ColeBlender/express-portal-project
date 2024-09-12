# MGM Grand WiFi Simulation Project

This project simulates the WiFi login experience at MGM Grand, Las Vegas. It is built using multiple microservices deployed on separate DigitalOcean Droplets with Docker, and uses NATS for communication between services.

## Project Overview

The project is composed of three key microservices:

1. **[Express Portal](https://github.com/ColeBlender/express-portal)**: A full-stack web app that simulates the WiFi login experience for hotel guests, with a responsive frontend and a Node.js/Express backend.
   - **Frontend**: HTML, CSS, JavaScript, and TypeScript
   - **Backend**: Node.js, Express, Supabase (database), Docker

2. **[Guests Microservice](https://github.com/ColeBlender/guests-microservice)**: Handles guest operations, including check-ins and managing WiFi login counts, via gRPC.
   - **Features**: Guest registration, retrieving guest details, and updating WiFi login counts
   - **Database**: Supabase
   - **Deployment**: Docker

3. **[WiFi Microservice](https://github.com/ColeBlender/wifi-microservice)**: Manages the WiFi login process for guests by communicating with the Guests Microservice using gRPC.
   - **Features**: Validating guest credentials and incrementing login counts
   - **Deployment**: Docker

### Communication

The two microservices (Guests and WiFi) use **gRPC** for direct communication and interact with a **NATS server** for message brokering and asynchronous communication where necessary. The NATS server is hosted on a separate server, also deployed on a DigitalOcean Droplet.

## Live Demo

The live version of the main Express Portal can be accessed at:  
[mgm.coleblender.com](https://mgm.coleblender.com)

## Technologies

- **Frontend**: HTML, CSS, JavaScript, TypeScript
- **Backend**: Node.js, Express, Supabase, gRPC, NATS
- **Deployment**: Docker, DigitalOcean Droplets

## Architecture

- **Express Portal**: User-facing web app
- **Guests Microservice**: Manages guest check-ins and details
- **WiFi Microservice**: Handles WiFi login process
- **NATS Server**: Facilitates communication between microservices

Each service is independently deployed and containerized using Docker, providing scalability and flexibility for future updates.
