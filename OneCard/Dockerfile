# Use a lightweight Node.js image
FROM node:18-alpine

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install

# Copy the rest of the frontend files
COPY . .

# Build the app for production
RUN npm run build

# Use an Nginx image to serve the built frontend
FROM nginx:alpine

# Copy the built files to the Nginx default public directory
COPY --from=0 /app/dist /usr/share/nginx/html

# Expose the default port for Nginx
EXPOSE 80

# Start the Nginx server
CMD ["nginx", "-g", "daemon off;"]
