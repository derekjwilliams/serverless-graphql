# Notes

In quickstart 

At https://github.com/derekjwilliams/serverless-graphql


## Let's use DynamoDB

See the DynamoDB section under Quick Start (Serverless Offline)

### Start backend
cd app-backend/dynamodb
yarn start

### Hiccup

Browsing to localhost:4000/graphiql gives a 404

```
{
  "statusCode": 404,
  "error": "Serverless-offline: route not found.",
  "currentRoute": "get - /",
  "existingRoutes": [
    "post - /graphql",
    "get - /graphql"
 ]
}
```

### Fix Hiccup

Use public served playground instead https://www.graphqlbin.com/v2/6RQ6TM

with http://localhost:4000/graphql

Or desktop application: https://github.com/prisma/graphql-playground


```brew cask install graphql-playground```

Whew... 

----

## Frontend

Use 

```
cd app-client/apollo-client/
yarn start
```

Then open playground, point to http://localhost:4000/graphql

Running this query works

```{
  getUserInfo(handle: "Madalyn61") {
    name
    tweets {
      items {
        retweeted
        retweet_count
        favorited
        tweet
      }
    }
    topTweet {
      retweeted
      retweet_count
      favorited
    }
  }
}
```

Yay!

## Deployment

Fun

Follow instructions in the [2min walkthrough link](https://www.youtube.com/watch?v=mRkUnA3mEt4)

### Details

User: serverless



Backup old credentials first, because default is used by serverless command line tool.




Change package.json to use homepage of "."
