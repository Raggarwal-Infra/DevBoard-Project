FROM node:20-alpine

WORKDIR /app

# used to improve layering while image re-build.
COPY package*.json ./
RUN npm ci # build dependencies for the frontend application.

COPY . .
RUN npm run build # build the frontend application

# 0.0.0.0 so the server is reachable from outside the container.
CMD ["npm", "run", "preview", "--", "--host", "0.0.0.0", "--port", "4173"]
