## Task 1
**Question**<br>
Run docker with the python:3.13 image. Use an entrypoint bash to interact with the container.
What's the version of pip in the image?<br>
**Solution**<br>
`docker run --rm -it --entrypoint bash python:3.13 -c "pip --version"`
<img src="images/task1_1.jpg" width="800" height="220" alt="docker run"/><br>
**Answer**<br>
25.3<br>

## Task 2
**Question**<br>
Given the following `docker-compose.yaml`, what is the hostname and port that pgadmin should use to connect to the postgres database?
```yaml
services:
  db:
    container_name: postgres
    image: postgres:17-alpine
    environment:
      POSTGRES_USER: 'postgres'
      POSTGRES_PASSWORD: 'postgres'
      POSTGRES_DB: 'ny_taxi'
    ports:
      - '5433:5432'
    volumes:
      - vol-pgdata:/var/lib/postgresql/data

  pgadmin:
    container_name: pgadmin
    image: dpage/pgadmin4:latest
    environment:
      PGADMIN_DEFAULT_EMAIL: "pgadmin@pgadmin.com"
      PGADMIN_DEFAULT_PASSWORD: "pgadmin"
    ports:
      - "8080:80"
    volumes:
      - vol-pgadmin_data:/var/lib/pgadmin

volumes:
  vol-pgdata:
    name: vol-pgdata
  vol-pgadmin_data:
    name: vol-pgadmin_data
```
**Solution**<br>
Containers run within the same network. So pgadmin will use host of the service with postgres (`db`) and port, which is used within container with postgres (`5432`)<br>
**Answer**<br>
db:5432<br>
