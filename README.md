# Android Code Test

1. Create an Android App from the scratch using Kotlin or Java.

2. The App should be able to register an user using the GraphQL API provided

3. The App should be able to register an user using the FB oAuth Service Provided

4. It is a plus if your app have a readable structure and well-defined architecture

5. It is a plus if your app is well designed

Please, create a fork of this repository and upload your code there. Let us know when you're done with the test so we can check what you've done. Thanks!


### Network Layer

You can use whatever you want to make the network calls to the REST API (We use it for small stuff, like oAuth). We recommend you to check out https://github.com/kittinunf/Fuel; it is a lightweight network library written in Kotlin, but there is plenty others that you may want to use. For the purpose of this test, you'll need to consume our oAuth API that works like the following image:

![](https://www.hivemq.com/wp-content/uploads/oauth-simple.png)

You'll need to setup your project to use our facebook app resources; and we'll give you access as developer in our facebook interface, so please send us your facebook_id somewhere so you can be added to the developers portal as soon as possible. After configuring your app to work with facebook resources, you'll need to ask for the access_token and authenticate the user using the following endpoint:

```javascript
GET /auth/facebook/token?access_token=<TOKEN_HERE>
```

### Android Apollo GraphQL

We recommend you to start by visiting https://github.com/apollographql/apollo-android; it will provide you the necessary tools to access to a GraphQL API. It will generates your models and the network interface to consume the API, manage and parse all the objects. 

### GraphQL API

The GraphQL endpoint is https://app.crowdswap.com/graphql and if you want to test your queries and mutations you should try https://app.crowdswap.com/graphiql. 

The following query example will return all the user given names registered in our database:

```graphql
query {
  allSwappers {
    nodes {
      givenName
      
    }
  }
}
```

The following mutation example will create a new user in our database: 

```graphql
mutation {
  registerSwapper(input: { email:"df@crowdswap.com", password:"hola123", birthDate:"1992-12-23", givenName:"Daniel", familyName:"Marulanda", username:"dfmarulanda69"}) {
    jwtToken
  }
}
```



If you have any question regarding this test, please write us at d@crowdswap.com or c@crowdswap.com.

If you want to checkout our actual design of the app you can visit: https://projects.invisionapp.com/share/CTNXF5GZVRN

Good luck!

