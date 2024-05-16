FROM node:16.15.1

# Why do we install these?
# RUN apk add --no-cache --virtual .gyp python make g++ 

WORKDIR /app

# We copy just the dependencies first to leverage Docker cache
COPY package.json /app
COPY package-lock.json /app

# RUN apt-get update && apt-get install -y \
#     build-essential \
#     python \
#     g++ \
#     make \
#     && rm -rf /var/lib/apt/lists/*

RUN npm install
# RUN npm rebuild node-sass

COPY . /app

CMD ["npm", "start"]
