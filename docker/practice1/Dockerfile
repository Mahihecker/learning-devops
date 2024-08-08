#base image
FROM node:19-alpine
# Copy package.json, wildcard used so both package.json AND package-lock.json are copied
# slash '/' at the end of app is important, so it created an app directory, otherwise you'll get an error
COPY package.json /app/
COPY server.js /app/
# Create app directory & set default dir so that next commands executes in /app dir, liked cd-ing into /app to execute npm install
WORKDIR /app
# Clear npm cache and install dependencies
RUN npm cache clean --force && npm install
# Expose port 80
EXPOSE 3000

# Set default environment variable
ENV MESSAGE="Welcome to my awesome app!"

# Start the application
CMD ["node", "server.js"]


