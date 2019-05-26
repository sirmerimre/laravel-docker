# App

## Setup Development Environment

  Fetch Code
 
 `git@github.com:sirmerimre/laravel-docker.git`
 
 Add .env file 
 
 Add docker-compose.yml:
 
 ```
version: '3.3'
services:
  db:
    image: mysql:5.7
    restart: always
    environment:
      MYSQL_DATABASE: 'db'
      # So you don't have to use root, but you can if you like
      MYSQL_USER: 'user'
      # You can use whatever password you like
      MYSQL_PASSWORD: 'password'
      # Password for root access
      MYSQL_ROOT_PASSWORD: 'password'
    ports:
      # <Port exposed> : < MySQL Port running inside container>
      - '3306:3306'
    expose:
      # Opens port 3306 on the container
      - '3306'
      # Where our data will be persisted
    volumes:
      - my-db:/var/lib/mysql
# Names our volume
volumes:
  my-db:
  
 ```
 
 Start Docker:
 
 ```
 docker-compose up -d
 ```
 
 Stop Docker:
 
 ```
 docker-compose down
 ```
 
 Install required Atlantis packages:
 
 `composer install`
 
 
 Start local server:
 
 `
 php artisan serve --port=8080
 `