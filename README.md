# todo-nodejs-app

#### Dockerfile
```bash
FROM node:12.2.0-alpine
WORKDIR app
COPY . .
RUN npm install
RUN npm run test
EXPOSE 8000
CMD ["node","app.js"]
```

#### Build the Image from Dockerfile

```bash
docker build -t myApp .
```

```
# Verify the image
docker images
```

#### Create the container from image you built
```
docker run -d -p 8000:8000 --name my_node_app myApp
```

```
# To see whether container is running or not
docker ps
docker ps -a
```

### docker-compose.yaml file
```bash
version: '3'
services:
  todo-nodejs-app:
    build:
      context: .
      dockerfile: Dockerfile   # If your Dockerfile is in a different directory, adjust the path
    ports:
      - "8000:8000"  # Map host port to container port
```

```
# To run the application
docker-compose up
```






