---
template: post
title: 'Getting To Know the Space Daemon'
slug: space-daemon-getting-started
draft: false
date: 2020-08-12T12:18:31.636+00:00
description: Get ready for some one-on-one time with the Space Daemon. Learn what it does and how you can leverage it for your projects!
category: General
socialImage: https://fleek-team-bucket.storage.fleek.co/SpaceDaemon.png
tags:
- general

---
![](https://fleek-team-bucket.storage.fleek.co/SpaceDaemon.png)

The Space Daemon is a our latest open source project aimed at developers wanting to build the next great app by leveraging encrypted file storage on IPFS.

In the next few minutes, we will discuss the Space Daemon, what it is, what it does and how to make use of it.

### Why the Space Daemon was created
![](https://fleekblog-team-bucket.storage.fleek.co/space-daemon-getting-started/and-its-gone.jpg)

Necessity is the mother of invention, and at Fleek we've identified an area of the modern internet necessitating a new invention.

As a case study, let's discuss Twitter. Recently, many high-profile Twitter accounts from the likes of Barack Obama, Joe Biden, Jeff Bezos, Elon Musk and many more got [badly hacked](https://www.bbc.com/news/technology-53445090). This hack exposed the frailty of modern security practices. Furthermore, it highlighted how vulnerable users are to centralised big tech control.

### Private privacy and secure security
![](https://fleekblog-team-bucket.storage.fleek.co/space-daemon-getting-started/little-privacy.jpg)

Encryption is like underwear for data. It safeguards your privacy by preventing those for whom it's not their business to take a little peek.

However, there's an important distinction between the encryption schemes of the Space Daemon and those of tech companies like Twitter.

For example, Twitter encrypts the content of the databases containing private messages (which people suspect were laeked in the hack) as they should be. But who controls the keys to decrypt the data? It is Twitter. This gives the companies and/or hackers access your data.

That is why we've decided that the Space Daemon give power back to the users. Files uploaded using the Space Daemon are encrypted not in a remote server but locally on the user's machines. The keys are kept in the possession of the user himself. No one can access user data, but the user.

Also, the Space Daemon is built on IPFS, a peer-to-peer, content addressed protocol for transferring data. What does it mean for users? It means IPFS has no central point of failure and, as such, it cannot be censured.

Additionally, new technologies like Filecoin will allow data to be backed up in a decentralised manner, thus enforcing the robustness of the system even further.

### Daemon or Space Desktop app?

What is the difference between the [Space app](https://blog.space.storage/posts/Introducing-Space) and the Space Daemon?

The Space Desktop app is an encrypted file storage platform competing with the likes of Dropbox and Google Drive. It will be open source so users can verify themselves that no weird shenanigans is going on with their data.

The Space Daemon (also [open source](https://github.com/FleekHQ/space-daemon)), on the other hand, is the backbone of the Space Desktop app. It handles the brunt of the work by handling encryption, peer-to-peer functionality and other tasks.

That being said, we've built the Space Daemon not just for the Space Desktop app, but for ALL developers of privacy-focused apps.

### It's easy to develop for!

We've made it easy to develop on top of the Space Daemon through thorough documentation, a simple-to-use client and plenty of educational content.

So whether you want to build the next great app or just want to experiment, you will have minimal friction with the Space Daemon.

Also, since we've open sourced the Daemon itself, any developer can add new features whether it is support for a new web3 protocol,  integrating an ethereum node to the Daemon, or extending the client's methods it can all be added and we will be happy to include your pull requests.

### I want to build! Now what?

First, you need an idea. Good thing that there's ton of potential products to be built with the Space Daemon. Basically, any product existing today in the web2 field could make use of a web3 make over supported by the Space Daemon. Apps like Google docs, Gmail, Github, Reddit, Youtube, Photo Album apps and more.

Of course, the Dweb field being such a melting pot of innovation, we're also expecting products no one has even thought about yet.

Second, you will need resources to get you started.
To start, the documentation provides a [great introduction to the Space Daemon](https://docs.fleek.co/space-daemon/getting-started/), including how to setup and an exhaustive listing of all the methods available through the Space Client.


Additionally, we also have a [Space Daemon playlist](https://www.youtube.com/playlist?list=PL3v9ZaTBrN9F8V5AjUTJm2jhKM24abPbk) of video tutorials on the Fleek Youtube Channel.


And finally, we have an [educational example of an electron app](https://github.com/FleekHQ/space-client-workshop) integrating the Space Daemon and showcasing basic functionality that you can study.

### Share your creations!

We are excited to see what cool projects you will come up with using the Space Daemon, so share your ideas with us on [Twitter](https://twitter.com/spacestorage).

Happy hacking!

* [Sign up](https://app.fleek.co "Sign Up") to try Fleek
* Join our [Community Chat](https://join.slack.com/t/fleek-public/shared_invite/zt-bxna7y1d-PbVdut4rgHt5jM6Zjg9g9A "Fleek's Slack")
* Follow us on [Twitter](https://twitter.com/FleekHQ "Fleek's Twitter")
* Subscribe to our [Youtube channel](https://www.youtube.com/channel/UCBzlwYM0JjZpjDZ52-SLUmw "Fleek's Youtube Channel")
* Check out our [Tech Docs](https://docs.fleek.co/ "Fleek Docs")
* Contact us at support@fleek.co