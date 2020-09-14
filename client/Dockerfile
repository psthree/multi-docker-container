FROM node:alpine as builder
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY . .
RUN npm run build
#CMD ["npm", "run", "start"]

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /ect/nginx/conf.d/default.conf
COPY --from=builder /app/build /user/share/nginx/html


# docker build -f Dockerfile .
# docker run <id> docker run 6b4224d98e0d