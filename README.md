# Accounts & Email AsyncAPIs

All the resources you need to implement a functional simple architecture with an Accounts and an Email services using AsyncAPI, Anypoint Code Builder, and brokers like AnypointMQ and Kafka.

Architecture based on this article by AsyncAPI: 
- 📘 [Understanding AsyncAPIs with a Practical Example](https://www.asyncapi.com/blog/understanding-asyncapis)

## Similar repos

[![](https://github-readme-stats.vercel.app/api/pin/?username=alexandramartinez&repo=asyncapi-mule-sfpe&theme=material-palenight)](https://github.com/alexandramartinez/asyncapi-mule-sfpe)

## Resources

Follow these videos to build your own AsyncAPIs:

- ▶️ [Design AsyncAPI Specifications in Design Center](https://www.youtube.com/watch?v=GQXRW5C6U0s)
- ▶️ [Implement AsyncAPIs with Anypoint MQ and Anypoint Code Builder](https://www.youtube.com/watch?v=sf7zx_KHxLA)
- ▶️ [Design, Govern, and Implement AsyncAPIs Locally with Kafka](https://www.youtube.com/watch?v=825T7VpyaBk)

Complement your learnings with these blog posts:

- [Design AsyncAPI Specifications With a Practical Example](https://blogs.mulesoft.com/dev-guides/how-to-design-asyncapi-specifications/)
- [Develop AsyncAPIs With Anypoint MQ and Anypoint Code Builder](https://blogs.mulesoft.com/dev-guides/develop-asyncapis-with-anypoint-mq-and-anypoint-code-builder/)
- [Develop AsyncAPIs on Anypoint Code Builder with Solace PubSub+ locally (Docker)](https://www.prostdev.com/post/how-to-develop-asyncapis-on-anypoint-code-builder-with-solace-pubsub-locally-docker)
- [Design, Govern, and Implement AsyncAPIs in Anypoint Code Builder](https://blogs.mulesoft.com/dev-guides/asyncapis-in-anypoint-code-builder/)
- TBD - [Designing AsyncAPIs using Salesforce Platform Events vs. CDC](https://blogs.mulesoft.com/)

## Folders structure

### Anypoint MQ

> [!IMPORTANT]
> Make sure you are using an Anypoint Platform Enterprise account to be able to create queues in AnypointMQ. For detailed instructions see the resources at the top.

1. Go to the [anypointmq/](/anypointmq/) folder
2. Create the Accounts Service AsyncAPI in Design Center using this specification: [accounts-service.yaml](anypointmq/specifications/accounts-service.yaml)
3. Create the Email Service AsyncAPI in Design Center using this specification: [email-service.yaml](anypointmq/specifications/email-service.yaml)
4. Publish them both to Exchange
5. Create new Mule projects in ACB for both Accounts and Email services OR use the code from the [mule-projects/](anypointmq/mule-projects/) folder:
    - [accounts-service/](anypointmq/mule-projects/accounts-service/)
    - [email-service/](anypointmq/mule-projects/email-service/)
    - (I recommend you create them from scratch and just use these as a guide)
6. Make sure you add your properties inside the `dev-properties.properties` files (also add your orgID in the last property)

### Kafka (locally)

> [!IMPORTANT]
> Make sure you are running Kafka locally in port 9092 or change it in the specifications before implementing them. For more information to run Kafka locally, see [this](https://github.com/sahansera/kafka-docker). For detailed instructions see the resources at the top.

1. Go to the [kafka/](/kafka/) folder
2. Create the Accounts Service AsyncAPI in Anypoint Code Builder using this specification: [accounts-service.yaml](kafka/specifications/accounts-service.yaml)
3. Publish it to Exchange and implement it in Anypoint Code Builder. Take a look at the code in [accounts-service/](kafka/mule-projects/accounts-service/) for guidance
4. In another VS Code window, create the Email Service AsyncAPI in Anypoint Code Builder using this specification: [email-service.yaml](kafka/specifications/email-service.yaml)
5. Publish it to Exchange and implement it in Anypoint Code Builder. Take a look at the code in [email-service/](kafka/mule-projects/email-service/) for guidance
6. Run both projects locally (since ACB doesn't allow this, as workaround, change the Mule runtime version from one of the projects to a different one. For example, accounts with runtime 4.8 and email with runtime 4.7)

### Salesforce Platform Events

> [!IMPORTANT]
> Set up your Salesforce Platform Event, Object (and Tab), and Trigger Flow before creating the Mule specification/project. For detailed instructions see the resources at the top.

> [!NOTE]
> This example takes one Platform Event and publishes another one. As opposed to Anypoint MQ, Kafka, and Solace, in this example there are two channels and only one AsyncAPI spec/app.

1. Go to the [sfplatformevents/](/sfplatformevents/) folder
2. Create the Email Service AsyncAPI in Anypoint Code Builder using this specification: [email-service.yaml](/sfplatformevents/specifications/email-service.yaml) - note that you will have to adjust it to your own Platform Event / Object fields
3. Publish it to Exchange and implement it in Anypoint Code Builder. Take a look at the code in [email-service/](/sfplatformevents/mule-projects/email-service/) for guidance
4. Make sure you add your properties inside the `dev-properties.properties` file

### Salesforce CDC (Change Data Capture)

> [!IMPORTANT]
> Set up your Salesforce Object (and Tab) and CDC before creating the Mule specification/project. For detailed instructions see the resources at the top.

> [!NOTE]
> This example only includes subscription to CDC, not publication.

1. Go to the [sfcdc/](/sfcdc/) folder
2. Create the Email Service AsyncAPI in Anypoint Code Builder using this specification: [email-service.yaml](/sfcdc/specifications/email-service.yaml) - note that you will have to adjust it to your own Object fields
3. Publish it to Exchange and implement it in Anypoint Code Builder. Take a look at the code in [email-service/](/sfcdc/mule-projects/email-service/) for guidance
4. Make sure you add your properties inside the `dev-properties.properties` file

### Solace (locally)

> [!IMPORTANT]
> Make sure you are running Solace locally before implementing the specifications. For more information to run Solace locally, see [this](https://www.prostdev.com/post/how-to-develop-asyncapis-on-anypoint-code-builder-with-solace-pubsub-locally-docker).

1. Go to the [solace/local/](/solace/local/) folder
2. Create the Accounts Service AsyncAPI in Anypoint Code Builder using this specification: [accounts-service.yaml](solace/local/specifications/accounts-service.yaml)
3. Publish it to Exchange and implement it in Anypoint Code Builder. Take a look at the code in [accounts-service/](solace/local/mule-projects/accounts-service/) for guidance
4. In another VS Code window, create the Email Service AsyncAPI in Anypoint Code Builder using this specification: [email-service.yaml](solace/local/specifications/email-service.yaml)
5. Publish it to Exchange and implement it in Anypoint Code Builder. Take a look at the code in [email-service/](solace/local/mule-projects/email-service/) for guidance
6. Run both projects locally (since ACB doesn't allow this, as workaround, change the Mule runtime version from one of the projects to a different one. For example, accounts with runtime 4.8 and email with runtime 4.7)
