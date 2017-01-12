#Senior Java Code Challange

###Frameworks/Libraries to be used
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

>The projects will be used for hotel reservations
Please create two projects, one will be used as a client and the other as a service

####Service Project:
    - Allow to get/insert/update/delete hotels
    - Allow to get/insert/update/delete hotel reservations
    - Allow to check if the hotel has available rooms by specifying the room type and hotel stars
    - Allow to get a summery of reserved rooms, total rooms, available rooms 
    - It should be fully RESTfull API (NO User Interface needed)
    - Every reservation made or canceled should send a message through RabbitMQ as an event including the hotel name, room type, start date, end date
    - Every new hotel created/deleted/updated should send a message through RabbitMQ
    - The project should use Spring Security OAuth2 provider to secure the REST endpoints
    - The project should use Redis for caching hotels API
    - The project should use Java 8 API as much as possible (Lambda Expressions, Streams, Optionals, Date Time)
    - Write unit/integration tests for this project

####Client Project:
    - Will be a fully RESTfull API which will make requests to the second Service Project to make hotel reservations
    - It will make all requests using REST API to the Service Project
    - It should be fully RESTfull API (NO User Interface needed)
    - It should listen the RabbitMQ channel for messages from Service Project about reservations done and log to console the message

####The hotels must have the following definitions
    - Hotel Stars (how many stars the hotel has, 1 to 5)
    - Hotel total rooms
    - Hotel rooms types (single-room, double-room)

####The hotel room types must have the following definitions
    - Hotel Id
    - Hotel room type
    - Hotel room price per day

####The hotel reservation must have the following definitions
    - Hotel Id
    - Hotel room type
    - Reservation Start and End Date
    - Reservation price calculated by date of reservation
