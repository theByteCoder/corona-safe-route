FROM node:latest as node
LABEL author="Subhaish.Ghosh"
WORKDIR /app
COPY . .
RUN npm install
# ARG env=prod
RUN npm run build --prod

FROM nginx:alpine
VOLUME [ "/var/cache/nginx" ]
COPY --from=node /app/dist/ /usr/share/nginx/html
# COPY nginx.conf /usr/local/etc/nginx/nginx.conf
# EXPOSE 80
# CMD [ "nginx", "-g", "daemon off;" ]