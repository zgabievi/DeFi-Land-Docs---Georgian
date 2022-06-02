# ტექნოლოგია

### თამაშის ძრავი

DeFi Land შექმნილია Unity Engine 2021.2.1-ის გამოყენებით, რაც გვაძლევს საშუალებას შევქმნათ ინტერაქტიული 3D გამოცდილება ჩვენი ფერმერებისთვის. მოცემული ძრავი გვაძლევს საშუალებას, რომ გავუშვათ თამაში ბრაუზერში WebGL ტექნოლოგიის დამსახურებით და შევქმნათ PC და მობილური ვერსიებიც ახლო მომავალში. DeFi Land-ის ბრაუზერში გაშვება გვერხმარება ჩავაშენოთ სხვადასხვა არსებული პროტოკოლი JavaScript-ის დახმარებით.

### DeFi SDK

ჩვენ გადავწყვიტეთ შეგვექმნა JavaScript SDK, რადგან ჩვენი მიზანია თამაშად ვაქციოთ DeFi გამოცდილება და ბლოქჩეინის ოპერაციები მომხმარებლებისთვის ყველაზე მარტივი და ხარჯთეფექტური გზით. ჩვენი SDK აერთიანებს არსებულ პროტოკოლებს, ამარტივებს და ამცირებს მათი ინტეგრაციის დროს. მოგვიანებით SDK ყველასთვის ღია იქნება, რათა დეველოპერებმა მოახერხონ სხვადასხვა პროტოკოლების ინტეგრაცია უფასოდ.

### Backend

ჩვენი ბექენდი განთავსებულია Amazon Web Services (AWS)-ზე, ყოვლისმომცველ და ფართოდ მიღებულ ღრუბლოვან პლატფორმაზე. ძირითადი ბექენდ ინფრასტრუქტურა აწყობილია Serverless მოდელით, რაც გვეხმარება ვმართოთ სისტემა ZeroOps-ით.

To bring the fastest in-game experience to users, we decided to build an Asynchronous System. The backbone of our backend is implemented using CQRS and Event Sourcing microservices architectural patterns that allows the system to be rewinded to or replayed from a particular user's game state. AWS Lambda and AWS ECS Fargate are used as our prime compute engine resources. Our core messaging protocol for microservices is built on top of AWS SNS and AWS SQS. AWS DynamoDB is the main persistence layer for the game but we also use AWS S3 for storing static data and warehousing. To reduce the time of game delivery to users, we distribute static content in many AWS CloudFront Edge Locations around the globe. Endpoints for our APIs are fanned out as well. AWS Cognito helps us to implement user authentication and authorization in the simplest and most convenient way.

### მონიტორინგი და ბოტის კონტროლი

The logs from AWS CloudWatch and our proprietary event logging tool are ingested into AWS Athena, giving us the ability to monitor specific user interactions. This mechanism also enables us to gain insight into user engagement for specific features. Implementing bot control is one of the most challenging parts of our project. Currently, we are using AWS WAF and AWS Shield to prevent the system from vulnerabilities. Smart rules for AWS WAF are updated using log analysis and statistical inference. Since we have experience in ML and data science, we are also working on our own solution.
