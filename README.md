# question2answer-docker
Question2Answer docker image

## Using plain docker
TBA

## Deploy q2a for kubernetes
```
kubectl apply -f kubernetes/q2a 
kubectl apply -f kubernetes/mysql 
```


Here's an example of a `docker-compose.yml` file
```yaml
question2answer:
    image: ofekedri/question2answer:latest
    links:
        - db:mysql
    environment:
        QUESTION2ANSWER_DB_USER: question2answer_user
        QUESTION2ANSWER_DB_PASSWORD: 12345678
        QUESTION2ANSWER_DB_NAME: question2answer


db:
    image: mysql:8
    environment:
        MYSQL_USER: question2answer_user
        MYSQL_PASSWORD: 12345678
        MYSQL_DATABASE: question2answer
        MYSQL_ROOT_PASSWORD: <something secret>

```
