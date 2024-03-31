# Choose the Node.js base image
FROM node:14

# Set the working directory inside the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Bundle app source
COPY . .

# Your app binds to port 8080, so you'll use the EXPOSE instruction to have it mapped by the docker daemon
EXPOSE 8080

CMD [ "node", "server.js" ]