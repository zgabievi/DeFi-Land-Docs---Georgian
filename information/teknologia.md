# ტექნოლოგია

### Game engine

DeFi Land is built using Unity Engine 2021.2.1, which allows us to create an interactive 3D experience for our farmers. The cross-platform nature of the engine gives us the ability to run the game in the browser using WebGL technology and create PC and mobile versions as well in near future. Running DeFi Land on the web helps us to integrate the many existing protocols with ease using JavaScript.

### DeFi SDK

We decided to create our own JavaScript SDK since our goal is to gamify the DeFi experience and blockchain operations for users in the easiest and most cost-efficient way. Our SDK unites existing protocols under the same interface and simplifies and reduces the time it takes to integrate new protocols. Later, we will be opening it for everyone, so developers will be able to bring new integrations to the platform easily and for free.

### Backend

Our backend is hosted on Amazon Web Services (AWS), the world’s most comprehensive and widely adopted cloud platform. The core backend infrastructure of the game is built using the Serverless Model that helps us to develop and maintain our system with near ZeroOps.&#x20;

To bring the fastest in-game experience to users, we decided to build an Asynchronous System. The backbone of our backend is implemented using CQRS and Event Sourcing microservices architectural patterns that allows the system to be rewinded to or replayed from a particular user's game state. AWS Lambda and AWS ECS Fargate are used as our prime compute engine resources. Our core messaging protocol for microservices is built on top of AWS SNS and AWS SQS. AWS DynamoDB is the main persistence layer for the game but we also use AWS S3 for storing static data and warehousing. To reduce the time of game delivery to users, we distribute static content in many AWS CloudFront Edge Locations around the globe. Endpoints for our APIs are fanned out as well. AWS Cognito helps us to implement user authentication and authorization in the simplest and most convenient way.

### Monitoring and bot control

The logs from AWS CloudWatch and our proprietary event logging tool are ingested into AWS Athena, giving us the ability to monitor specific user interactions. This mechanism also enables us to gain insight into user engagement for specific features. Implementing bot control is one of the most challenging parts of our project. Currently, we are using AWS WAF and AWS Shield to prevent the system from vulnerabilities. Smart rules for AWS WAF are updated using log analysis and statistical inference. Since we have experience in ML and data science, we are also working on our own solution.
