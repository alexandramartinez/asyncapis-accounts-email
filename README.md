# Accounts & Email AsyncAPIs

All the resources you need to implement a functional simple architecture with an Accounts and an Email services using AsyncAPI, Anypoint Code Builder, and brokers like AnypointMQ and Kafka.

Projects and specifications created during this live stream on July 30, 2024: 
- ▶️ [Accounts/Email AsyncAPIs with ACB and AnypointMQ](https://www.twitch.tv/videos/2211325574)

Architecture based on this article by AsyncAPI: 
- 📘 [Understanding AsyncAPIs with a Practical Example](https://www.asyncapi.com/blog/understanding-asyncapis)

## Resources

Follow these videos to build your own AsyncAPIs:

- ▶️ [Design AsyncAPI Specifications in Design Center](https://www.youtube.com/watch?v=GQXRW5C6U0s)
- ▶️ [Implement AsyncAPIs with Anypoint MQ and Anypoint Code Builder](https://www.youtube.com/watch?v=sf7zx_KHxLA)
- ▶️ [Design, Govern, and Implement AsyncAPIs Locally with Kafka](https://www.youtube.com/watch?v=825T7VpyaBk)

## Folders structure

### Anypoint MQ

1. Go to the [anypointmq/](/anypointmq/) folder
2. Create the Accounts Service AsyncAPI in Design Center using this specification: [accounts-service.yaml](anypointmq/specifications/accounts-service.yaml)
3. Create the Email Service AsyncAPI in Design Center using this specification: [email-service.yaml](anypointmq/specifications/email-service.yaml)
4. Publish them both to Exchange
5. Create new Mule projects in ACB for both Accounts and Email services OR use the code from the [mule-projects/](anypointmq/mule-projects/) folder:
    - [accounts-service/](anypointmq/mule-projects/accounts-service/)
    - [email-service/](anypointmq/mule-projects/email-service/)
    - (I recommend you create them from scratch and just use these as a guide)
6. Make sure you add your properties inside the `dev-properties.properties` files (also add your orgID in the last property)

> [!IMPORTANT]
> Make sure you are using an Anypoint Platform Enterprise account to be able to create queues in AnypointMQ

### Kafka (locally)

1. Go to the [kafka/](/kafka/) folder
2. Create the Accounts Service AsyncAPI in Anypoint Code Builder using this specification: [accounts-service.yaml](kafka/specifications/accounts-service.yaml)
3. Publish it to Exchange and implement it in Anypoint Code Builder. Take a look at the code in [accounts-service/](kafka/mule-projects/accounts-service/) for guidance
4. In another VS Code window, create the Email Service AsyncAPI in Anypoint Code Builder using this specification: [email-service.yaml](kafka/specifications/email-service.yaml)
5. Publish it to Exchange and implement it in Anypoint Code Builder. Take a look at the code in [email-service/](kafka/mule-projects/email-service/) for guidance
6. Run both projects locally (since ACB doesn't allow this, as workaround, change the version from one of the projects to a different one)

> [!IMPORTANT]
> Make sure you are running Kafka locally in port 9092 or change it in the specifications before implementing them. For more information to run Kafka locally, see [this](https://github.com/sahansera/kafka-docker).