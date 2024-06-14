
# Docker Volume Example

## Description

This repository provides an example of using Docker volumes with a Node.js application. It demonstrates how to use Docker volumes to persist data and share files between a host and a Docker container, which is useful for developers looking to manage data in a containerized environment.

## Requirements

- Node.js
- Docker
- Yarn or npm for package management

## Mode of Use

1. Clone the repository:
   ```bash
   git clone https://github.com/ferrerallan/docker-volume-example.git
   ```
2. Navigate to the project directory:
   ```bash
   cd docker-volume-example
   ```
3. Ensure you have Docker installed on your machine.
4. Build the Docker image:
   ```bash
   docker build -t docker-volume-example .
   ```
5. Run the Docker container with a volume:
   ```bash
   docker run -d -p 3000:3000 -v /host/path:/container/path docker-volume-example
   ```

## Implementation Details

- **Dockerfile**: Contains instructions for building the Docker image.
- **src/**: Contains the Node.js application source code.

### Example of Use

Here is an example of a simple Dockerfile for a Node.js application that uses volumes:

```dockerfile
# Use the official Node.js image as a base
FROM node:14

# Set the working directory
WORKDIR /usr/src/app

# Copy package.json and package-lock.json files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Expose the application port
EXPOSE 3000

# Command to run the application
CMD ["node", "app.js"]
```

This Dockerfile sets up a Node.js application environment, installs dependencies, and runs the application. Docker volumes can be used to persist data and share files between the host and container.

## License

This project is licensed under the MIT License.

You can access the repository [here](https://github.com/ferrerallan/docker-volume-example).
