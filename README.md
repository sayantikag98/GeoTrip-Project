## 📌 GeoTrip - Microservices Based Ride Booking System   
A scalable ride-booking application built with Spring Boot microservices architecture.

## 📂 Microservices Repositories

| Microservice       | Description                                      | Repository Link |
|--------------------|--------------------------------------------------|----------------|
| **Auth Service**   | Handles user authentication (JWT)               | [GeoTrip-AuthService](https://github.com/sayantikag98/GeoTrip-AuthService) |
| **Booking Service** | Manages ride bookings & assignments             | [GeoTrip-BookingService](https://github.com/sayantikag98/GeoTrip-BookingService) |
| **Location Service** | Tracks drivers using Redis geospatial data     | [GeoTrip-LocationService](https://github.com/sayantikag98/GeoTrip-LocationService) |
| **Entity Service** | Defines shared entity models                     | [GeoTrip-EntityService](https://github.com/sayantikag98/GeoTrip-EntityService) |
| **API Gateway**   | Routes requests & enforces authentication        | [GeoTrip-ApiGateway](https://github.com/sayantikag98/GeoTrip-ApiGatewayService) |
| **Eureka Server** | Handles service discovery                        | [GeoTrip-EurekaServer](https://github.com/sayantikag98/GeoTrip-EurekaServer) |
| **Exception Handler** | Provides global error handling                | [GeoTrip-ExceptionHandler](https://github.com/sayantikag98/GeoTrip-ExceptionHandler) |

## 🚀 Project Overview   
GeoTrip is a distributed ride-booking system built using the microservices architecture. It enables users (passengers) to book rides while drivers can accept and complete trips in real-time.

## 🏗️ Architecture    
Spring Boot (Java 21)    
Spring Cloud (Eureka, Gateway)    
Spring Security + JWT Authentication   
Spring Data JPA + MySQL    
Redis (Geospatial Queries)    
Kafka (Event-Driven Communication)   
Docker & Kubernetes (For Future Scalability)     

## 📌 Features    
✅ User Authentication: JWT-based login & registration (Driver/Passenger)    
✅ Ride Booking: Passengers can request rides, and drivers can accept trips     
✅ Driver Tracking: Real-time driver locations stored in Redis    
✅ Microservices Communication: Feign Clients + Eureka Service Discovery    
✅ Centralized API Gateway: Handles authentication & request routing     
✅ Global Exception Handling: Standardized error messages across all services    

## 📂 How to Set Up & Run  

1️⃣ Clone All Microservices
```sh
git clone https://github.com/sayantikag98/GeoTrip-AuthService.git
git clone https://github.com/sayantikag98/GeoTrip-BookingService.git
git clone https://github.com/sayantikag98/GeoTrip-LocationService.git
git clone https://github.com/sayantikag98/GeoTrip-EntityService.git
git clone https://github.com/sayantikag98/GeoTrip-ApiGatewayService.git
git clone https://github.com/sayantikag98/GeoTrip-EurekaServer.git
git clone https://github.com/sayantikag98/GeoTrip-ExceptionHandler.git
```
2️⃣ Start Eureka Server (Service Discovery)
```sh
cd GeoTrip-EurekaServer
./gradlew bootRun
```
Eureka will be available at http://localhost:8761

3️⃣ Start API Gateway
```sh
cd ../GeoTrip-ApiGateway
./gradlew bootRun
```
API Gateway will be available at http://localhost:8080

4️⃣ Start All Microservices
```sh
cd ../GeoTrip-AuthService && ./gradlew bootRun
cd ../GeoTrip-BookingService && ./gradlew bootRun
cd ../GeoTrip-LocationService && ./gradlew bootRun
cd ../GeoTrip-EntityService && ./gradlew bootRun
cd ../GeoTrip-ExceptionHandler && ./gradlew bootRun
```
##📡 API Endpoints
| Service | Method | Endpoint | Description |
|---------|--------|----------|-------------|
| **Auth Service** | `POST` | `/api/v1/auth/login` | User login (JWT) |
| **Auth Service** | `POST` | `/api/v1/auth/register/driver` | Register a driver |
| **Auth Service** | `POST` | `/api/v1/auth/register/passenger` | Register a passenger |
| **Booking Service** | `POST` | `/api/v1/booking` | Create a new ride booking |
| **Booking Service** | `GET` | `/api/v1/booking/{id}` | Retrieve booking details |
| **Location Service** | `POST` | `/api/v1/location/drivers` | Save driver location |
| **Location Service** | `POST` | `/api/v1/location/drivers/nearby` | Get nearby drivers |

📌 All requests (except authentication) must pass through API Gateway (http://localhost:8080).

## 🔑 Security & Authentication    
Uses JWT-based authentication (Spring Security).    
All requests must include a Bearer Token (Authorization: Bearer <token>).    
Tokens are validated at API Gateway, and microservices trust headers (X-User-Email, X-User-Role).   

## 📌 Future Enhancements    
🔹 Implement Kafka for Asynchronous Communication   
🔹 WebSockets for Live Ride Tracking   
🔹 Docker & Kubernetes for Scalability   
🔹 GraphQL APIs for Flexible Data Retrieval   

## 👨‍💻 Contributors    
Sayantika – [GitHub Profile](https://github.com/sayantikag98)    
Feel free to contribute and open issues! Show Some Support!   
If you like this project, ⭐️ star this repository and follow me on GitHub!  
Happy coding!    
