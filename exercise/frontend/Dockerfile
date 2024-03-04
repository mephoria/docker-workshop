FROM node:20-buster as builder

WORKDIR /frontend

ENV REACT_APP_BACKEND_URL=http://localhost:8000

COPY package.json package-lock.json tailwind.config.js ./
COPY src ./src
COPY public ./public

RUN npm install && npm run build

FROM node:20-buster-slim

RUN npm install -g serve

WORKDIR /frontend

COPY --from=builder /frontend/build /frontend/build

EXPOSE 3000

CMD ["serve", "-s", "build", "-l", "3000"]