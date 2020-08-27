FROM ubuntu AS clone
RUN apt-get update
RUN apt-get install -y git
WORKDIR /workspace
RUN git clone https://github.com/kkenan/basic-microservices

FROM node:10
WORKDIR /workspace
COPY --from=clone /workspace/basic-microservices/node-app /workspace
RUN ls
RUN npm install
EXPOSE  8081
CMD [ "node", "index.js"]