# WELCOME documentation-shopping-car
>documentation to use shopping car. In this section I will show you how to use the APIS to use shopping carts

>In e-commerce, the shopping cart is a piece of software where your customers can store the products they like and might purchase after browsing merch in your catalog. But other than serving as a storage of items for purchase, an e-commerce shopping cart offers several important functions.

>Once a customer adds an item to their shopping cart, they can easily review and manage their selections.  Customers can continue browsing your website and then add products or remove them from the cart. When they're done browsing, they can go back to their shopping cart and select the items they want to check out.

>A shopping cart also shows the different shipping and payment options. After the customer makes a payment, the cart organizes all the order information and sends it to you as the retailer, and to other parties, such as your bank and delivery partners for order fulfillment.

 
![shoppingcard](https://github.com/FernandoClimaco/device-security-cuscatlan-service/blob/main/Shopping-cart-trick-1-1024x410.png)

##
## Architecture
![Architecture](https://github.com/FernandoClimaco/device-security-cuscatlan-service/blob/main/shoppingCardarquitecture.png)


##
## CURLS: import collection in your postman for using the apis shopping car.
>Dowloand:
![JSON COLLECTION](https://github.com/FernandoClimaco/shopping-car-cuscatlan-service/blob/main/src/main/resources/shopping-card-cuscatlan-services.postman_collection.json)

> view collection:
![collection](https://github.com/FernandoClimaco/shopping-car-cuscatlan-service/blob/main/CURLS.PNG)




## CONFIGURATION application properties: variable Vault: talk to a devops
>-SERVICES: device-security-cuscatlan-service 
>
>
 

```
server.port=${SERVER_PORT:2023}

#Configuration connection mysql
spring.datasource.url=${SPRING_DATASOURCE_URL:jdbc:mysql://localhost:3306/cuscatlanshoppingcard?createDatabaseIfNotExist=true&autoReconnect=true&useSSL=false}
spring.datasource.username=${SPRING_DATASOURCE_USERNAME:root}
spring.datasource.password=${SPRING_DATASOURCE_PASSWORD:}
spring.datasource.platform=${SPRING_DATASOURCE_PLATORM:mysql}

#sql validation
spring.datasource.dbcp2.validation-query=select 1 from dual


#Configuration connection redis
spring.redis.database=${SPRING_REDIS_DATABASE:6}
spring.redis.host=${SPRING_REDIS_HOST:localhost}
spring.redis.port=${SPRING_REDIS_PORT:6379}
spring.redis.password=${SPRING_REDIS_PASSWORD:}
spring.redis.ttl=${SPRING_REDIS_TTL:60}

#Configuration log
logging.pattern.console=%d{yyyy-MM-dd HH:mm:ss} %-5level %logger{36} - %msg%n
logging.level.org.hibernate.SQL=WARN
logging.level.root=INFO


request.bearer=${REQUEST_BEARER:Bearer}

#Configuration JWT secret
jwt.secret=${JWT_SECRETS:fern4nd0}

```


>
>



>-SERVICES: shopping-card-cuscatlan-service

```
server.port=${SERVER_PORT:2024}

#Configuration connection mysql
spring.datasource.url=${SPRING_DATASOURCE_URL:jdbc:mysql://localhost:3306/cuscatlanshoppingcard?createDatabaseIfNotExist=true&autoReconnect=true&useSSL=false}
spring.datasource.username=${SPRING_DATASOURCE_USERNAME:root}
spring.datasource.password=${SPRING_DATASOURCE_PASSWORD:}
spring.datasource.platform=${SPRING_DATASOURCE_PLATORM:mysql}
spring.datasource.driver-class-name=${SPRING_DATASOURCE_DRIVER_CLASS_NAME:com.mysql.cj.jdbc.Driver}


#For generate database
spring.sql.init.mode=always
spring.jpa.hibernate.ddl-auto=create
spring.jpa.defer-datasource-initialization=true


#Consumer API:
fake.store.api.url=${FAKE_STORE_API_URL:https://fakestoreapi.com/}
device.security.cuscatlan.service.url=${DEVICE_SECURITY_CUSCATLAN_SERVICE_URL:http://localhost:2023}
device.security.cuscatlan.service.auth.validate.endpoint=${DEVICE_SECURITY_CUSCATLAN_SERVICE_AUTH_VALIDATE_ENDPOINT:/auth/validation}

spring.jackson.default-property-inclusion = NON_NULL
```