# Use the official Node.js image as the base image
FROM node:14 AS build

# Set the working directory in the container
WORKDIR /app

# Copy the package.json and package-lock.json to the container
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the Angular app source code to the container
COPY . .

# Build the Angular app for production
RUN npm run build --prod   # Assuming you want a production build

# Use a lightweight Nginx image as the final production image
FROM nginx:alpine

# Copy the built Angular app files to the Nginx web server directory
COPY --from=build /app/dist /usr/share/nginx/html

# Expose port 80 (default for HTTP)
EXPOSE 80

# Start Nginx when the container runs
CMD ["nginx", "-g", "daemon off;"]
