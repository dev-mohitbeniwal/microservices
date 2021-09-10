FROM beevelop/ionic AS ionic
WORKDIR /usr/src/app
COPY package*.json ./
COPY ionic.config.json ./
# RUN npm install node-sass
RUN npm ci
COPY . .
RUN ionic build
FROM nginx:alpine
COPY --from=ionic  /usr/src/app/www /usr/share/nginx/html