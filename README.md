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






