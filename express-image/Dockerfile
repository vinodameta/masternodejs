FROM node:6-alpine

# Create a server directory
RUN mkdir -p /home/node/app
WORKDIR /home/node/app

# Install server dependencies
COPY /express-image/package.json /home/node/app
npm config set proxy http://user:password@proxy.example.com:8181
npm config set https-proxy http://user:password@proxy.example.com:8181
#COPY /express-image/resolve /etc/docker/daemon.json
#COPY /express-image/resolve1 /etc/hosts
RUN npm install --loglevel verbose
# Copy node Application
COPY app.js /home/node/app

# Open port
EXPOSE 9000

CMD ["npm", "start"]
