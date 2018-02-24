# docker-aspnetcore-app

# run with docker-compose.yml

> docker-compose up -d

```
version: "2"
services:
    aspnetcore.app:
        image: cowpanda/aspnetcore-app:2.0
        container_name: aspnetcore.app.test
        working_dir: /app
        network_mode: bridge
        volumes:
            - {your_publish_release_path}:/app
        environment:
            - APP=./your_app_dll
        ports:
            - 8081:80
```

# run in command line

```
    docker run --rm -d --name {container_name}  -v {your_publish_release_path}:/app -w /app -p 8923:80 -e  APP={your_app_dll}  cowpanda/aspnetcore-app:2.0

```

