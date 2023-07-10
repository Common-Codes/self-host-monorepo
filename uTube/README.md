# Self-Hosting [uTube](https://common-codes.github.io/shnitters) (a.k.a "OpenSource-uTube", "OS-uTube", "osutube", contd.)
**This guide is for users who have a basic understanding of hosting locally or on VPS service's**

## Forking the repo
Simple enough.<br>
Either go to the repository at [github.com/Common-Codes/uTube](https://github.com/Common-Codes/OpenSource-uTube) and press the fork button, follow this [link](https://github.com/Common-Codes/OpenSource-uTube/fork), create a fork from the GitHub desktop app, create a fork using Git in your CLI, or go to the repository and press download as zip.

## Hosting uTube
To host uTube on the Global Instance, simply start hosting the repo on localhost or the VPS of your choice.

**External Instance**: To host uTube on an external instance (not recommended), you can change the `firebaseConfig` in `index.html`.

*We recommend hosting uTube with Firebase, which it was designed for. For Firestore security rules, go to [`SECURITY.md`](https://github.com/Common-Codes/self-host-monorepo/blob/main/uTube/SECURITY.md).

### Advanced
*The simple randomising algorithm in `populator.js` can be tweaked or replaced to give different recommendations, based on different data, etc. You can leave this as-is if you want, and you'll just get all video data displayed in a random order each time.
