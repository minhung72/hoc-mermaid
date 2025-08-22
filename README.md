```mermaid
graph TB
subgraph "Frontend Layer"
Web[Website<br/>React + Redux]
Mobile[Mobile App<br/>React Native]
Admin[Admin Panel<br/>Vue.js]
end
subgraph "API Gateway Layer"
API[API Gateway<br/>Kong/Nginx]
Auth[Auth Service<br/>JWT + OAuth2]
RateLimit[Rate Limiter<br/>100 req/min]
end
subgraph "Microservices Layer"
UserSvc[User Service<br/>Node.js]
ProductSvc[Product Service<br/>Java Spring]
OrderSvc[Order Service<br/>Python FastAPI]
PaymentSvc[Payment Service<br/>Go]
NotifySvc[Notification Service<br/>Node.js]
end
subgraph "Data Layer"
UserDB[(User DB<br/>PostgreSQL)]
ProductDB[(Product DB<br/>MongoDB)]
OrderDB[(Order DB<br/>PostgreSQL)]
Cache[(Redis Cache<br/>Session + Data)]
Queue[RabbitMQ<br/>Event Queue]
end
subgraph "External Services"
PayGate[Payment Gateway<br/>Stripe/PayPal]
Ship[Shipping API<br/>GHN/Viettel]
Email[Email Service<br/>SendGrid]
SMS[SMS Gateway<br/>Twilio]
end
%% Connections
Web --> API
Mobile --> API
Admin --> API
API --> Auth
API --> RateLimit
Auth --> UserSvc
API --> ProductSvc
API --> OrderSvc
API --> PaymentSvc
UserSvc --> UserDB
UserSvc --> Cache
ProductSvc --> ProductDB
ProductSvc --> Cache
OrderSvc --> OrderDB
OrderSvc --> Queue
PaymentSvc --> PayGate
Queue --> NotifySvc
NotifySvc --> Email
NotifySvc --> SMS
OrderSvc --> Ship
%% Styling
style Web fill:#e1f5fe
style Mobile fill:#e1f5fe
style API fill:#fff3e0
style Auth fill:#f3e5f5
style Cache fill:#ffebee
style Queue fill:#e8f5e9
