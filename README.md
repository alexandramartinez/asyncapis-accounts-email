# Accounts & Email AsyncAPIs

All the resources you need to implement a functional simple architecture with an Accounts and an Email services using AsyncAPI, Anypoint Code Builder, and AnypointMQ.

Projects and specifications created during this live stream on July 30, 2024: 
- ▶️ [Accounts/Email AsyncAPIs with ACB and AnypointMQ](https://www.twitch.tv/videos/2211325574)

Architecture based on this article by AsyncAPI: 
- 📘 [Understanding AsyncAPIs with a Practical Example](https://www.asyncapi.com/blog/understanding-asyncapis)

## Folders structure

1. Create the Accounts Service AsyncAPI in Design Center using this specification: [accounts-service.yaml](/specifications/accounts-service.yaml)
2. Create the Email Service AsyncAPI in Design Center using this specification: [email-service.yaml](/specifications/email-service.yaml)
3. Publish them both to Exchange
4. Create new Mule projects in ACB for both Accounts and Email services OR use the code from the [mule-projects/](/mule-projects/) folder:
    - [accounts-service/](/mule-projects/accounts-service/)
    - [email-service/](/mule-projects/email-service/)
    - (I recommend you create them from scratch and just use these as a guide)
5. Make sure you add your properties inside the `dev-properties.properties` files (also add your orgID in the last property)

> [!IMPORTANT]
> Make sure you are using an Anypoint Platform Enterprise account to be able to create queues in AnypointMQ
