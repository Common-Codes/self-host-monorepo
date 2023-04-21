# Self-Hosting [Shnitters](https://common-codes.github.io/shnitters)
**This guide is for users who have a basic understanding of hosting locally or on VPS service's**

## Forking the repo
Simple enough.<br>
Either go to the repository at [codeberg.org/Common-Codes/shnitters](https://codeberg.org/Common-Codes/shnitters) and press the fork button, follow this [link](https://github.com/Common-Codes/shnitters/fork), create a fork from the GitHub desktop app, create a fork using Git in your CLI, or go to the repository and press download as zip.

## Hosting Shnitters
To host Crispy on the Global Instance, simply start hosting the repo on localhost or the VPS of your choice.

**External Instance**: To host Shnitters on an external instance, simply change the `firebaseConfig` in `index.html`.

*We recommend hosting Shnitters with Firebase, which it was designed for. For Firestore security rules, go to [`SECURITY.md`](https://github.com/Common-Codes/self-host-monorepo/blob/main/shnitters/SECURITY.md).

Shnitters **can** be hosted on other SQL/NoSQL backends, but some major changes are needed. This may get covered in a future update of these docs.

### Advanced
*The advanced ELO algorithm in `sharethelove.js` can be tweaked or replaced to give different recommendations, based on different data, etc. You can leave this as-is for somewhat accurate recommendations.

If you do, however, choose to modify the algorithm, remember to change any neccessary data on the frontend!
