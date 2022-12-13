# Security Rules for Crispy
###### Before starting we really recommend you read and somewhat understand [the docs](https://firebase.google.com/docs/firestore/security/get-started), as they can be really helpful for you to secure data in a different way than we do.

## Firestore Data Rules
> These Firestore rules allow for authenticated users to navigate the whole `users` & `guilds` collections of the Crisp API, stored on Firebase Firestore. They are important to allow user accessibility while maintaining security. Note: `badges` are a read-only sub-collection of the user's collection, while `joined` is a sub-collection only visible to the same user as the one logged in.

We use rules version 1, as Crispy doesn't rely on [collection group queries](https://firebase.google.com/docs/firestore/query-data/queries#collection-group-query).

1. **The `users` collection**

```
match /users/{userId} {
      allow read, create: if request.auth.uid != null;
      allow write, delete: if request.auth.uid == userId;

      match /badges/{badge} {
        	allow read: if request.auth.uid != null;
      }

      match /joined/{join} {
        	allow create, read, write, delete: if request.auth.uid == userId;
      }
}
```

2. **The `guilds` collection**

```
match /guilds/{guildId} {
      allow create, write: if request.auth.uid != null;
      allow read;
}
```
> The `guilds` collection is openly readable for API Stats.
