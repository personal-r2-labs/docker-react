###----BUILD---###
FROM node:alpine as builder
WORKDIR /app
COPY package.json .
RUN npm install
COPY . . 
RUN npm run build

###----RUN----###
FROM nginx:alpine
COPY --from=builder /app/build /usr/share/nginx/html
