FROM node:20-buster

WORKDIR /backend

COPY package.json package-lock.json index.js utils.js ./

RUN npm install

ENV PORT=8000

VOLUME /backend/history.log

EXPOSE 8000

CMD ["node", "index.js"]