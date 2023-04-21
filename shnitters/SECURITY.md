# Security Rules for Shnitters
###### Before starting we really recommend you read and somewhat understand [the docs](https://firebase.google.com/docs/firestore/security/get-started), as they can be really helpful for you to secure data in a different way than we do.

## Firestore Data Rules
> These Firestore rules allow for authenticated users to navigate the whole `status`, `handles` & `users` collections of the Shnit API, stored on Firebase Firestore. They are important to allow user accessibility while maintaining security. Note: `handles` are an otherwise read-only collection that can only be modified by the same user who's data pertains.

We use rules version 2, as Shnitters uses [collection group queries](https://firebase.google.com/docs/firestore/query-data/queries#collection-group-query).

1. **The `status` collection**

```
match /status/{statusId} {
    allow read;
    allow write, create: if request.auth.uid != null
    allow update: if request.auth.uid == userId;
    
    match /comments/{comment} {
        allow read;
        allow write, create, update, delete: if request.auth.uid != null;
    }
}
```
> Openly Readable, no need to login to see status updates.

2. **The `users` collection**

```
match /users/{userId} {
    allow read;
    allow create: if request.auth.uid != null;
    allow write, update, delete: if request.auth.uid == userId;
}
```
> Openly Readable, no private data stored.

3. **The `handles` private collection**
```
match /handles/{handle} {
    allow read;
    allow write: if request.auth.uid != null;
}
```
> Openly Readable. Not allowed to delete existing data. Permitted to write to self to let service know if handle is available.
