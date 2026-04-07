
# Base image for backend
FROM node:21  AS backend-builder    

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install required dependencies
RUN npm install

# Run test

RUN npm run test

# Copy the rest of the application code to the working directory
COPY . .


FROM node:21-slim

WORKDIR /app

COPY --from=backend-builder /app .



COPY .env.sample .env
# Expose the port the app runs on
EXPOSE 5000

# Command to start the backend server
CMD ["npm", "start"]


