# Production Docker image for Strapi V4

It's quite frustrate when looking for a Docker image to run (in production) Strapi with minimal setup. All the answers out there are not clear. And that's why this repo is born

# Usage
It's very simple to start strapi that's ready for production, you can run it with Docker, Compose or Kubernetes,...

For example with Docker Compose:
```yml
version: '3'

services: 
  strapi:
    image: maitrungduc1410/prod-strapi
    restart: always
    ports:
      - "1337:1337"
    environment:
      APP_KEYS: appkey1,appkey2 # add as many as app keys you want
      API_TOKEN_SALT: apitokensalt
      ADMIN_JWT_SECRET: adminsupersecret
      TRANSFER_TOKEN_SALT: transfer_token_salt
      JWT_SECRET: supersecret
      # Database
      DATABASE_CLIENT: mysql
      DATABASE_HOST: localhost
      DATABASE_PORT: "3306"
      DATABASE_NAME: strapi
      DATABASE_USERNAME: root
      DATABASE_PASSWORD: myrootpass
      DATABASE_SSL: "false"
```
# Deployment
There's no difference between deploy your own Strapi to a real host and running in localhost
# Note
This image is generated with latest version of Strapi using `strapi new`, no additional code, everything is default.

The purpose of this image is to provide a production ready image that you can simply run it without the need of building it.