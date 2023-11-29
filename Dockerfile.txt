# Use an official Node runtime as a parent image
FROM node:14

# Set the working directory to /app
WORKDIR /app

# Copy package.json and package-lock.json to /app
COPY package*.json ./

# Install any needed packages specified in package.json
RUN npm install

# Copy all other source code to /app
COPY . .

# Make port 80 available to the world outside this container
EXPOSE 80

# Define the command to run your app
CMD ["npm", "start"]
