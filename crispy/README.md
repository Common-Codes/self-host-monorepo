# Self-Hosting [Crispy](https://crispychat.tech)
**This guide is for users who have a basic understanding of hosting locally or on VPS service's**

## Forking the repo
Simple enough.<br>
Either go to the repository at [Common-Codes/crispy](https://github.com/Common-Codes/crispy) and press the fork button, follow this [link](https://github.com/Common-Codes/crispy/fork), create a fork from the GitHub desktop app, create a fork using Git in your CLI, or go to the repository and press download as zip.

## Hosting Crispy
To host Crispy on the Global Instance, simply start hosting the repo on localhost or the VPS of your choice.

**External Instance**: To host Crispy on an external instance, simply change the `firebaseConfig` in `index.html`.

*We recommend hosting Crispy on Firebase, which it was designed for. For Firestore security rules, go to [`SECURITY.md`](https://github.com/Common-Codes/self-host-monorepo/blob/main/crispy/SECURITY.md).

Crispy **can** be hosted on other SQL/NoSQL backends, but some major changes are needed. This may get covered in a future update of these docs.

### Advanced
**💡Tip:** We recommend hosting Crispy and verbose on the same VPS.

*If using localhost, you can accomplish this by hosting both services on separate ports. Port 5500 is recommended for hosting the main platform.

If you do, however, choose to host your own verbose instance, remember to change the address for the image proxy and embed generator in `message.js`.
