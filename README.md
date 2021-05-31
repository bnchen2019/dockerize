#dockerize django application

docker build --tag dockerize:latest .
docker run --name dockerize -d -p 8000:8000 dockerize:latest

docker tag dockerize:latest repo/dockerize:latest
docker push repo/dockerize:latest

docker pull repo/dockerize:latest
docker tag dockerize:latest gcr.io/project/dockerize
docker push gcr.io/project/dockerize
