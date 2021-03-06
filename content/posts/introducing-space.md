---
template: post
draft: true
title: Introducing Space
slug: Introducing-Space-fleek
date: 2020-08-05T14:00:00.000+00:00
socialimage: https://fleek-team-bucket.storage.fleek.co/Space.png
description: 'Today the Fleek team is super excited to announce a brand new product
  we’ve been working on for the past few months: Space! Space is an open source file
  storage, sharing, and collaboration platform built on the distributed web.'
category: Announcement
tags:
- Space

---
![](https://fleek-team-bucket.storage.fleek.co/Space.png)

Today the Fleek team is super excited to announce a brand new product we’ve been working on for the past few months: Space!

Space is an open source file storage, sharing and collaboration platform built on the distributed web. You can think of V1 of Space as a private, encrypted, p2p version of dropbox or google drive, and you can use Space the same way that you would use those products. The big benefit of using Space over those other products is you don’t need to sacrifice your privacy and allow those companies to spy on you and control your files/data, because with Space everything is private, user owned, end-to-end encrypted, and peer-to-peer!

![](https://fleek-team-bucket.storage.fleek.co/SpaceScreenshot3.png)

Starting today, Space is accepting beta signups. If you’re interested in getting early access to Space and participating in the beta, sign up [here](https://space.storage) and we will reach out in the coming weeks when it’s your turn. This first version of Space is a desktop app available on Mac, Windows, and Linux. We plan to release a mobile app and web app in the future as well once it’s feasible (discussed more below).

Below is some additional info on Space, why we built it, and the product roadmap/vision.

## The Internet Is Broken

And we need to fix it now. Content is becoming more and more censored, hacks are becoming more and more serious, and big tech companies and governments are spying on users, violating their privacy, and abusing their data more and more everyday. In the past few months alone there have been multiple platforms ([Reddit](https://www.wsws.org/en/articles/2020/07/02/redd-j02.html), [Youtube](https://fee.org/articles/youtube-to-ban-content-that-contradicts-who-on-covid-19-despite-the-un-agency-s-catastrophic-track-record-of-misinformation/)) and governments ([Turkey](https://apnews.com/9abc40bdd22f6c8df763bad0b4c55924), [Hong Kong](https://fortune.com/2020/07/07/hong-kong-law-internet-freedom/)) increasing internet censorship, Twitter got [badly hacked](https://www.bbc.com/news/technology-53445090), and a [bill was introduced](https://www.cnet.com/news/republicans-push-bill-requiring-tech-companies-to-help-access-encrypted-data/) in the US that would force tech companies to unencrypt private data about users (if technically possible) and give it to the government. The trend is frightening, especially with things like personal health, genetic and brain data on the horizon, coupled with AI, we could be headed to a real dystopia if something isn’t done about this soon.

There’s only one possible way out of the current situation and to save the internet: distribute the web.

## Distributing The Web Is Our Only Way Out

All the issues with the current internet can be traced back to two main flaws: centralization & lack of encryption. And so the only way to fix the internet is to fix those two flaws. But the gatekeepers that control the current internet (google, apple, facebook, amazon, etc.) built their tremendous fortunes, power, and infrastructure around those flaws, so they aren’t going to help fix them. But luckily there are people like Juan Benet and Vitalik in the world who are creating new open source technologies that can serve as the foundation for a new, improved distributed internet that address the two main flaws of the current internet and finally gives control, ownership, privacy, and freedom back to users. And after 5+ years of several groups building and working on these new technologies/protocols, we feel they are now mature enough and ready to be combined/used to create a real distributed web stack and start building products/apps that leverage distributed web technologies to offer privacy, data ownership, censorship resistance, peer-to-peer, and other benefits to users, while still maintaining pretty much the exact same user experience internet/app users are accustomed to.

## Enter Space

Space is one of the first products fully built on the distributed web that provides a true Dweb (short for distributed web) experience to users. Space showcases the possibilities and benefits of the Dweb, which we hope encourages other developers to also build true Dweb sites & apps (and we’re building tools to make that super easy to do!). For Space, we chose to start with a file storage, sharing, and collaboration app because we feel that the technologies that make up the Dweb Stack (discussed below) are ready to handle this use case, and file storage/sharing also serves as a great base/foundational building block that other apps can now leverage to more easily create other use cases, products and experiences on the Dweb. That is why in conjunction with the open source Space desktop app, a few weeks ago we also recently released the open source [Space Daemon](https://blog.fleek.co/posts/daemon-release), which is essentially a standard interface that packages all the protocols in the Dweb stack into one easy to use daemon that can be shared across apps, so this way a user can just have one daemon on their machine that multiple Dweb apps can leverage. We already have several apps building on top of Space/Space Daemon and we highly encourage you to [check it out](https://github.com/FleekHQ/space-daemon)!

## What Underlying Technologies Power Space/Space Daemon (aka the ‘Dweb Stack’)?

Space is/will be built on top of IPFS, Textile, Filecoin, Ceramic, and Handshake (and potentially other distributed web protocols in the future). This combination is what we consider the initial ‘Dweb Stack’ - a set of open source protocols that together can create a true Dweb experience that rivals the current internet. Similar to DeFi starting by creating a separate, stand-alone, adjacent financial system that is now starting to blend with the traditional financial system over time, we felt the best approach for the Dweb would be to start out and grow in a similar way.

Space the desktop app was built using the open source Space Daemon mentioned above, which makes it super easy to build Dweb apps that leverage any/all of the underlying protocols in the Daemon (IPFS, Textile, Ceramic, Filecoin, Handshake, etc.), and enables a true Web3/distributed web experience for users (on desktop to start, and on mobile and in browser in the near future). What this means is that everything on Space is encrypted by default, owned by the user, peer-to-peer, self-hosted (functions without reliance on centralized companies/middlemen), censorship resistant, and users have the option to remain completely anonymous (no email or personal info required to use Space, and you can even use crypto to pay for Space Pro plans to remain completely anonymous). We plan on potentially adding other protocols to the Daemon in the future, such as Ethereum or others. We encourage other developers to contribute to the open source daemon repo and give input on it’s roadmap. The Space app will also be open source and will be added to our repo once it officially launches.

## Why Start With a Desktop App?

This decision was based on the current state of the Dweb Stack and the protocols under the hood (IPFS, Textile, etc.). In order to create a true Dweb user experience, you need to have nodes for these different protocols running on the users machine. These nodes don’t function perfectly on mobile or in browsers at the moment, but in a desktop app they work great. A ton of awesome work is being done that will make it feasible to create mobile and web versions of Space (and other apps built on Space/Space Daemon) in the coming months while maintaining the full Dweb user experience.

## How are Files/Data Stored and Transferred in Space?

Files can be stored locally on your machine(s) and shared completely privately/anonymously/peer-to-peer with other Space users (you can also privately/anonymously share files with users outside of Space using private links with optional password protection). Users/Teams also have the option to store backup encrypted copies of their files in ‘Space’. For now these backup encrypted copies of your files are stored on remote Space nodes (that consist of an IPFS, Textile, Filecoin, Ceramic, and Handshake nodes) that we run around the world. However we can never access your files or the contents of them, only you (and the people you share files with) can unencrypt them with the keys on your machine(s). We also will add Filecoin as an additional backup/encrypted storage option for users shortly after launch, so users will be able to choose if/where they want to store encrypted backups of their files/data. Users will also have the option to run their own backup Space nodes if they want. And at some point in the near future we hope to decentralize/open up the backup storage function completely (potentially via a token).

## What is the Benefit of Storing Backup Encrypted Copies of Files In Space?

Besides the privacy, encryption, p2p, censorship resistance, etc. benefits you get from using the Space app, the benefit of storing backup encrypted copies of your files/data in ‘Space’ (in addition to locally) is that you will have a backup/recovery mechanism in case you ever lose your device. Also in case someone you shared a file with is trying to access that file/data while you are offline, the file can still be served from ‘Space’ because those nodes are always online. Storing backup encrypted copies of your files in Space will be a paid feature, however it is completely optional to use, and you also have the option to pay for it in crypto if you choose to use it but prefer to remain anonymous.

The value prop of storing backup encrypted copies of your files in Space is similar to the value prop of cloud storage, except completely private, encrypted, anonymous, and nobody can access the content of your files/data besides you and the people you explicitly share/collaborate with. Plus Space is just cooler than ‘the Cloud’. Quite frankly, ‘the Cloud’ sucks: it isn’t private, it isn’t encrypted, it lets companies spy on you and abuse your data, it gets hacked all the time. Meanwhile Space doesn’t. Space > Cloud, period. Storing in the Cloud is such a lame, boomer move. Don’t be lame. Take back control of your data and privacy. Store in Space.

## How are Space and Fleek Related?

Right now they are completely separate products. But in the future we plan on adding features to Fleek to make it super easy to deploy true Dweb sites & build true Dweb apps on top of Space/Space Daemon (similar to how we make it easy today to deploy sites/apps directly to IPFS). So the plan is still for Fleek to become a Firebase type platform for building Dweb sites/apps. But Space will always remain a separate, fully open sourced project and product with an open app ecosystem (and hopefully a token at some point in the future).

## What’s the Vision… I Can Build Apps On Top of Space/Space Daemon?

Yes, that is the vision. We want Space the storage app to be just the first of many apps built on Space/Space Daemon. For developers we want Space/Space Daemon to serve as a super easy to use Dweb storage/db/interface layer for building Dweb apps that wow users while staying true to the Dweb principals/values (user privacy, data ownership, censorship resistance, self hosted, etc.). For example, some ideas for apps we think would be cool to build on top of Space would be true Dweb equivalents to apps like Google Docs, Sheets, Gmail, Github, Reddit, Youtube, or even simple things like a Notes app, a Photo Album app, or other interfaces/apps like that. The possibilities are endless, and the opportunities are massive. We’re happy to help any interested developers ideate and help support them build these apps. The idea is we will surface these apps/sites somewhere within the Space interface so users can easily access/discover Dweb sites and apps. But there won’t be any ‘app approval process’ or anything like that, it will be more like a browser in that sense where any Dweb site or app can be published in Space and discovered/accessed by anyone who wants to use it. And so for users the vision is that the Space interface can potentially become a gateway/browser/interface specifically for the Dweb in addition to being the place users store all their files and data from the Dweb and from elsewhere.

![](https://fleek-team-bucket.storage.fleek.co/DwebImage.png)

## And You Mentioned There Might Be A Token?

That’s the goal. It’s only right that a user owned internet (aka the Dweb) is in fact owned by users. But we still aren’t sure where exactly the best place is to insert one at this time. So we plan to follow a path similar to Compound where we launch the product first, get some real usage, see how Space and the Space Daemon progress, and then decide what the token model should be based on usage and what behaviors make sense to incentivize. One early idea we really like is liquidity mining with storage (aka the more you store in Space, the more tokens you earn). If that does end up being part of the model (which it likely will) we will count all usage/storage towards those rewards from the very beginning to reward early users. We also think a staking token for running Space back up storage nodes and handling payments to the underlying protocols as well as content routing could also be another interesting aspect of the token model (kinda like a layer 2 for filecoin). If you have ideas feel free to reach out, we’d be happy to chat about it!

## Final Thought: Data is the New Currency. Stop Letting People Steal It From You.

These big tech companies are getting rich off your data, without asking your permission, giving you nothing for it, and then turning around and using it against you. If you have the option between using products that abuse your data and privacy (Google Drive, Dropbox, etc.) vs. ones that don’t (Space, Signal, etc.), why would you choose to allow yourself to be spied on, robbed of value, and abused? It’s finally time to wake up. Take back control of your data and privacy. Use Space and help make the Dweb a reality!

We’re super excited to embark on this new Space journey and to help bring millions of users to the Dweb. We’d love to invite you all into our community to try out the new product and get your feedback. And if you feel there are opportunities to collaborate with us please reach out, we’d be happy to chat!

* Sign up for [Space Beta](https://space.storage)
* Follow us on [Twitter](https://twitter.com/spacestorage)
* Reach out at hi@space.storage
* Check out our [Tech Docs](https://docs.fleek.co/space-daemon/overview/)
* Spread the word

Also special thanks to the teams at Protocol Labs, Textile, Ceramic, Handshake, and the other companies in the Dweb space working on making the Dweb (and Space) a reality.

\- Harrison