# Dockerfile
FROM node:14

# Create app directory
WORKDIR /usr/src/app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install app dependencies
RUN npm install

# Install Jest globally
RUN npm install -g jest

# Copy app source code
COPY . .

# Expose port (if your application uses one)
EXPOSE 8080

# Define command to run tests
CMD ["npm", "test"]
