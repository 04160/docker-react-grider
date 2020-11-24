docker build -f Dockerfile.dev .
docker run -p 3000:3000 {DOCKER image id}
docker run -p 3000:3000 -v /app/node_modules -v $(pwd):/app {DOCKER image id}
docker run -it {DOCKER image id} npm run test

docker run -it -p 3000:3000 -v /app/node_modules -v $(pwd):/app -e CHOKIDAR_USEPOLLING=true CONTAINER_ID
winpty docker run -it -p 3000:3000 -v /app/node_modules -v "/$(pwd)":/app -e CHOKIDAR_USEPOLLING=true CONTAINER_ID

docker-compose down && docker-compose up --build