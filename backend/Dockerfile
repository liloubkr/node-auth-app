FROM node:26-alpine

WORKDIR /app

COPY package.json package-lock.json ./
# production dependencies only
RUN npm ci --omit=dev
COPY src ./src

ENV NODE_ENV=production
EXPOSE 3000

# Run node directly (not via npm) so it receives the stop signal from Docker.
CMD ["node", "src/server.js"]
