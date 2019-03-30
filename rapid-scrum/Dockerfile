ARG BUILD

FROM alpine/git as clone
WORKDIR /usr/src
RUN git clone https://github.com/gilmario-kpslow/rapid-scrum.git /usr/src

FROM node:11 as compile
WORKDIR /usr/src
COPY --from=clone /usr/src /usr/src
RUN npm i && npm run $BUILD

FROM nginx:latest
WORKDIR /usr/src
COPY --from=compile /usr/src/dist /usr/share/nginx/html
COPY ./nginx.conf /etc/nginx/conf.d/default.conf
EXPOSE 80
