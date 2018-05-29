FROM node:8.11.1-alpine

# Use node user from carbon image
USER node

# Needed because WORKDIR creates directories as root
# Should add && cd /home/node/api and delete WORKDIR line
RUN mkdir -p /home/node/api

# Create app directory, doesnt take USER in mind
WORKDIR /home/node/api

# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
COPY package*.json ./

RUN npm install
# If you are building your code for production
# RUN npm install --only=production

# Bundle app source
COPY . .

EXPOSE 3000

CMD ["node", "index.js"]
