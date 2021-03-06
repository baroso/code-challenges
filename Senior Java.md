# Senior Java Code Challenge

### Frameworks/Libraries to be used
  * Spring Boot
  * Spring Web
  * Spring Data JPA
  * Spring Security
  * Spring Security OAuth
  * Spring AMQP
  * Spring Test
  * OAuth2 and JWT
  * Java 8 (Streams API)
  * MySQL
  * RabbitMQ
  * Redis

>The projects will be used for hotel reservations.
>Please create two projects, one will be used as a client and the other as a service.

>No need to setup a database or other software infrastructure.
>Just write the functional code with JPA entities and required repositories and services, use JSON for data.

#### Service Project:
    - It should be based on a completly RESTfull API *(NO User Interface needed)*
    - Allow to get/insert/update/delete hotels
    - Allow to get/insert/update/delete hotel reservations
    - Allow to check if the hotel has available rooms by specifying the room type and hotel stars
    - Allow to get a summary of reserved rooms, total rooms, available rooms
    - Every reservation made or canceled should send a message through RabbitMQ as an event including the hotel name, room type, start and end date
    - Every new hotel created/deleted/updated should send a message through RabbitMQ
    - The project should use Spring Security OAuth2 provider to secure the REST endpoints
    - The project should use Redis for caching hotels API
    - The project should use Java 8 API as much as possible (Lambda Expressions, Streams, Optionals, Date Time)
    - Write unit/integration tests for this project

#### Client Project:
    - It should be based on a completly RESTfull API *(NO User Interface needed)*
    - It will make requests to the Service Project to make hotel reservations
    - It will make all requests using REST API to the Service Project
    - It should listen on a RabbitMQ channel for messages from the Service Project about reservations done and log the resulting messages to the console

#### The hotels must have the following definitions
    - Hotel Stars (how many stars the hotel has, 1 to 5)
    - Hotel total rooms
    - Hotel rooms types (single, double)

#### The hotel room types must have the following definitions
    - Hotel Id
    - Hotel room type
    - Hotel room price per day

#### The hotel reservation must have the following definitions
    - Hotel Id
    - Hotel room type
    - Reservation start and end date
    - Reservation price calculated by date of reservation
