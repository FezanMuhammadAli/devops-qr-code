FROM node:18-alpine

WORKDIR /app

# Copy only npm-related files for dependency installation
COPY package.json package-lock.json ./

# Install dependencies using npm
RUN npm ci

# Copy rest of the project files
COPY . .

# Build the application
RUN npm run build

# Expose the port the app runs on
EXPOSE 3000

# Start the application
CMD ["npm", "start"]
