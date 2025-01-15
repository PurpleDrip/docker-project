# Use a lightweight Node.js image
FROM node:18-alpine

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install

# Copy the rest of the backend files
COPY . .

# Expose the backend port (adjust according to your app's configuration)
EXPOSE 3000

# Start the backend server
CMD ["node", "index.js"]
