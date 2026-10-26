FROM nginx:alpine
WORKDIR /usr/share/nginx/html
ENV APP_VERSION="1.0"
COPY index.html .
RUN echo "$APP_VERSION" > build-info.txt
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
