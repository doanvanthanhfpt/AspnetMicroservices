# AspnetMicroservices

**Refer the POC landscape**

![microservices_remastered](https://user-images.githubusercontent.com/1147445/110304529-c5b70180-800c-11eb-832b-a2751b5bda76.png)

This is a microservices webapp which implemented as **e-commerce** simulation using **Catalog, Basket, Discount** and **Ordering** microservices with **NoSQL (MongoDB, Redis)** and **Relational databases (PostgreSQL, Sql Server)** with communicating over **RabbitMQ Event Driven Communication** and using **Ocelot API Gateway**.

## Run The Project
You will need the following tools:

* [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/)
* [.Net Core 5 or later](https://dotnet.microsoft.com/download/dotnet-core/5)
* [Docker Desktop](https://www.docker.com/products/docker-desktop)

### Installing
Follow these steps to get your development environment set up: (Before Run Start the Docker Desktop)
1. Clone the repository
2. For Docker Desktop, have to configure the minimum amount of memory and CPU like so:
* **Memory: 4 GB**
* CPU: 2
3. At the root directory which include **docker-compose.yml** files, run below command:
```csharp
docker-compose -f docker-compose.yml -f docker-compose.override.yml up -d
```
Note --> to stop containers use:
```csharp
docker-compose -f docker-compose.yml -f docker-compose.override.yml down
```
Note --> to build and run containers use:
```csharp
docker-compose -f docker-compose.yml -f docker-compose.override.yml --build
```
3. Wait for docker compose all microservices.

4. Webapp **launch microservices** as below urls:

* **Catalog API -> http://host.docker.internal:8000/swagger/index.html**
* **Basket API -> http://host.docker.internal:8001/swagger/index.html**
* **Discount API -> http://host.docker.internal:8002/swagger/index.html**
* **Ordering API -> http://host.docker.internal:8004/swagger/index.html**
* **Shopping.Aggregator -> http://host.docker.internal:8005/swagger/index.html**
* **API Gateway -> http://host.docker.internal:8010/Catalog**
* **Rabbit Management Dashboard -> http://host.docker.internal:15672**   -- guest/guest
* **Portainer -> http://host.docker.internal:9000**   -- done
* **pgAdmin PostgreSQL -> http://host.docker.internal:5050**   -- admin@aspnetrun.com/admin1234
* **Elasticsearch -> http://host.docker.internal:9200** -- done
* **Kibana -> http://host.docker.internal:5601** -- done
* **Web Status -> http://host.docker.internal:8007** -- done
* **Web UI -> http://host.docker.internal:8006**

5. Launch http://host.docker.internal:8007 in the browser to view the Web Status. Make sure that every microservices are healthy.
6. Launch http://host.docker.internal:8006 in the browser to view the Web UI. Can use Web project in order to **call microservices over API Gateway**. Once perform **checkout the basket** then follow **queue record on RabbitMQ dashboard**.

![mainscreen2](https://user-images.githubusercontent.com/1147445/81381837-08226000-9116-11ea-9489-82645b8dbfc4.png)


## Authors Credit
* Thanks **[mehmetozkaya](https://github.com/mehmetozkaya)** for *Initial work*.


