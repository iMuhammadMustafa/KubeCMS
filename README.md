# Structor.CMS
 
docker run --name postsdb -d -p 5400:5432 -e POSTGRES_PASSWORD=mysecretpassword postgres
docker run --name redis -d -p 6300:6379 redis:alpine
docker run --name rabbit -d -p 5600:5672 -p 5700:15672  masstransit/rabbitmq

docker run --name commentsdb -d -p 3300:3306 -e MYSQL_ROOT_PASSWORD=P4ssword! -e MYSQL_USER=newuser -e MYSQL_PASSWORD=P4ssword! -e MYSQL_DATABASE=CommentsService mysql


docker run --name ratingsdb -d -p 27000:27017 -e MONGO_INITDB_ROOT_USERNAME=mongoadmin -e MONGO_INITDB_ROOT_PASSWORD=mysecretpassword -e MONGO_INITDB_DATABASE=StructorCMS mongo



---

kubectl apply -f redis-depl.yaml
kubectl apply -f rabbit-depl.yaml
kubectl apply -f comments-db-depl.yaml
kubectl apply -f posts-db-depl.yaml

kubectl apply -f posts-depl.yaml
kubectl apply -f comments-depl.yaml
kubectl apply -f ratings-depl.yaml