---
template: post
draft: false
title:
  "To DFINITY and Beyond: Static Front-end Hosting, Internet Computer Gateway,
  and the Next Steps."
slug: to-dfinity-and-beyond-dfinity-frontend-hosting
date: 2021-03-09T03:00:00.000+00:00
socialImage: https://fleek-team-bucket.storage.fleek.co/Blog%20Inline/DfinitySites.png
canonical: https://blog.fleek.co/posts/to-dfinity-and-beyond-dfinity-frontend-hosting
description:
  It’s happening. DFINITY + Fleek are coming together to power front-end
  and sites hosting on the Internet Computer, a new Internet Computer Gateway, and
  our path forward into building trustless web services.
category: Release
tags:
  - Internet Computer
  - Hosting
  - Dfinity
---

![dfinity release](https://fleek-team-bucket.storage.fleek.co/Blog%20Inline/DfinitySites.png)

Major day for Fleek doesn’t begin to even cover it. Today, at a virtual event titled[ “Exploring Entrepreneurship in the Open Internet Boom”](https://dfinity.org/techcrunch/) hosted by the [DFINITY Foundation](https://dfinity.org/) in partnership with Techcrunch, we are revealing that we are joining the Internet Computer ecosystem in **full force** and going live on the Internet Computer!

It’s a special release day — we have a series of new Internet Computer specific features coming out onto the Fleek platform, like **Static Front-end Hosting**!

This means you can now host and experiment with websites and apps on the Internet Computer's Alpha, a trustless blockchain-based infrastructure; as well as use our Internet Computer Gateway for accessing canisters over HTTP; or our Canister Proxying for resolving sites on the Internet Computer.

But we are also sharing **our path forward on the Internet Computer, and into our idea of building a truly trustless, decentralized, and permissionless version** of our Open Web services (e.g., hosting, storage, etc.) using Internet Computer canisters!

Buckle up, because when we say “To DFINITY and Beyond” we mean it.

![dfinity and beyond](https://fleek-team-bucket.storage.fleek.co/Blog%20Inline/dfinitybeyond.webp)

### TL;DR Agenda

#### New Feature Releases:

1. [Static frontend Hosting on the Internet Computer](#new-features-static-frontend-hosting-on-dfinitys-internet-computer)
2. [Fleek's Internet Computer Gateway](#new-features-fleeks-internet-computer-gateway)
3. [Canister Proxying](#new-features-canister-proxying)

#### Next Steps

1. [Building Canister-based Services](#next-steps-building-canister-based-services)
2. [Why do it on the Internet Computer](#next-steps-why-do-it-on-the-internet-computer)
3. [Wrapping it up!](#next-steps-wrapping-it-up-)

---

## New Features: Static Frontend Hosting on DFINITY's Internet Computer

![internet computer hosting](https://fleek-team-bucket.storage.fleek.co/Blog Inline/dfinitydapp.png)

As of this moment, you can **take your static front-ends and host them on the Internet Computer with Fleek**! In just a couple of clicks, you can move your site further into Web 3.0 by hosting it on a computational blockchain network growing to become the trustless base layer of the new web.

It’s as easy as it is to host any static site on IPFS with Fleek. You just need to:

1. Connect your GitHub
2. Pick a repository
3. Select Internet Computer
4. Configure, build, and deploy

![internet computer fleek](https://fleek-team-bucket.storage.fleek.co/Blog%20Inline/host.gif)

That is all there is to it. **Fleek abstracts the entire process for you.** Canister creation, content updates, resolving, cycle management (though right now cycles are free-use on Mainnet, until they are fully implemented).

You can take any static site you used before in Fleek, and take it to the Internet Computer. All supported Jamstack sites on IPFS are **fully working** on the Internet Computer, and there is **no change whatsoever in build settings or requirements.**

**Need help getting started?** [Visit our docs page!](https://docs.fleek.co/internet-computer-hosting/overview/)

You can build **static frontends**, which means either static websites as we mentioned, or **Dapps or front-end apps** that don’t require a back-end infrastructure and leverage instead APIs from the FE to implement services/features!

### The Internet Computer's Alpha

**It's important to note that** this is an Alpha product, which we are launching and building on top of the **Internet Computer's Alpha/Testnet.** It is an experimental and early version that will help anyone test and build sites, apps or Dapps on the Internet Computer in preparation for the **Mainnet Beta genesis**!

Now's the time to test, experiment, and get your hands dirty building on the IC.

A minor limitation of this stage, for example, is a per-file size limit of 2MB, and a site/app total (for the entirety of the Canister) of about 2.5GB. This won't signify much on most static projects, but some media files (video/gifs/images) might be affected.

We'll progress the product as the Internet Computer progresses with the Mainnet, and once we reach the Mainnet's Beta, we will **do a migration/redeployment** of all sites to the Mainnet after Genesis arrives.

### How Does Fleek Achieve Frontend Hosting on the Internet Computer?

The process in the background is straightforward. When you connect your repository to Fleek, and make a deployment, Fleek uses the **DFINITY SDK** [(view documentation)](https://sdk.dfinity.org/docs/index.html) to create a front-end Canister on mainnet, and build and deploy your website’s code to it.

Right now, we do front-end canisters only (thus, static sites), but in the future we will allow for back-end as well.

![fleek canisters](https://fleek-team-bucket.storage.fleek.co/Blog Inline/flow.png)

Then, the continuous deployment process begins! With your canister up and running, upon any pushed changes to your linked repository’s branch, Fleek will use the DFINITY SDK again to make Canister calls and update your website’s content **reflecting changes immediately.** This means you get all the usual perks, but with your site on the Internet Computer:

- No content update delay
- No risk of conflicts
- Automatic SSL / DNS
- CDN and caching

All these are considered, in many ways, Web 2.0 elements that act as a bridge between the now evolving Web 3.0. As resolving becomes native to more devices and platforms (like browsers, or native apps and Dapps), each will be replaced by its Web 3.0 alternative.

### Domain Management and Resolving on the Internet Computer

When you deploy a new site on the Internet Computer with Fleek, **a free generic preview link** will be created, using Fleek’s Internet Computer Gateway and the your front-end Canister’s ID.

It will look something like this: \[CANISTER_ID\].ic.fleek.co

    https://x4ytk-6yaaa-aaaab-qaiqq-cai.ic.fleek.co/

![domains](https://fleek-team-bucket.storage.fleek.co/Blog Inline/checkdns.png)

This URL is a direct HTTP access to your site/app on the Internet Computer! We’ll go into the Gateways detail on the next point. But, of course, **we allow for custom DNS domains on the Internet Computer and the process is the same as it is with other environments.**

![dns](https://fleek-team-bucket.storage.fleek.co/Blog%20Inline/verifydns.png)

Simply specify your custom domain, click **verify DNS configuration**, and add the appropriate record to your domain’s CNAME (instructions might vary according to your provider). Once all is set and done, you can click verify again (wait a couple minutes until it propagates) and your site will be up and running on your own custom domain.

![custom domains ic](https://fleek-team-bucket.storage.fleek.co/Blog%20Inline/finished-add-domain.png)

What about **blockchain domains like ENS** (Ethereum Name Service) **or HNS** (Handshake)**?** We are working with all parties to combine the Internet Computer + Blockchain Domains, adding more and more options to peel off layers of centralization. We already have worked on experimental implementations, so expect news soon...

## New Features: Fleek's Internet Computer Gateway.

![gateway](https://fleek-team-bucket.storage.fleek.co/Blog%20Inline/portal-gateway.webp)

There are two main things we had to address when tackling Internet Computer Hosting on Fleek. First, there isn’t a standard and quick way of **accessing Canister data on the Internet Computer via HTTP**, on the current web standards, without having to make actual Canister calls.

What’s more, this goes for **all canisters and their data**, not just FE canisters created by Fleek.

Secondly, we also have to consider that even if hosted on the Internet Computer, if we wanted to surface static sites from the IC on the current Web 2.0 we would need to handle basic concepts such as SSL, CDN, and DNS for our users.

Combine these two issues, and a little bit of radioactive open source code, and you get the reason why [**Fleek’s Gateway was born**](https://github.com/FleekHQ/ic-proxy)**!** Our very own transdimensional portal, (minus the disintegration-risk) that **anyone, not just Fleek users,** can use to access their Internet Computer-hosted Canister data over HTTP and an accessible URL format.

The Fleek Internet Computer Gateway lives on: ic.fleek.co

To access any canister, just add your canister ID before the URL , to get a url like this:

    [CANISTER_ID].ic.fleek.co

For example, for this Create React App we mentioned above! [_https://x4ytk-6yaaa-aaaab-qaiqq-cai.ic.fleek.co/_](https://x4ytk-6yaaa-aaaab-qaiqq-cai.ic.fleek.co/ "https://x4ytk-6yaaa-aaaab-qaiqq-cai.ic.fleek.co/")

## New Features: Canister Proxying.

![canister proxying](https://fleek-team-bucket.storage.fleek.co/Blog%20Inline/proxy-service-workers@2x.png)

The Gateway itself as a proxy between users, and canisters on the Internet Computer. So, when it receives a request for a certain Canister ID, it translates that request, and the user receives the canister’s data through HTTP.

However, that is not all the Gateway does. Fleek’s Gateway gives users **two Canister proxying options,** or ways to connect visitors to your static site.

1. Using Fleek's seamless proxy (more centralized, but no loading state)
2. Using Fleek's service workers (less centralized, initial loading state)

![bots gateways](https://fleek-team-bucket.storage.fleek.co/Blog%20Inline/service-worker.jpeg)

### Using Fleek as a Proxy

The default option is using Fleek as a proxy, meaning the initial request will hit our servers, translate the user’s request, and return the data from the canister to the visitor. This experience is just as any current website, **seamless**, **but it does mean Fleek acts as a constant intermediary** between the user and the Internet Computer.

This is also the **default option for bots, crawlers, and extraterrestrial** requests. For example, search engines and social crawlers. This way we ensure your static site on the Internet Computer is crawlable, indexed, and its metadata is readable by bots for important details like… Displaying Twitter cards, or images when sharing links on social!

### Using Fleek's Service Workers

This alternative option is for users that want to further decentralize their experience, and **connect their users directly to the Internet Computer.** How does it work? If selected, **only the first request will hit our Gateway,** which will return a bootstrap script to the user, installing a Service Worker on their browser once, to connect them directly to the Internet Computer and retrieving all further requests directly from there, **without having Fleek as a constant intermediary.**

![fleek service workers](https://fleek-team-bucket.storage.fleek.co/Blog Inline/Loading (2).gif)

When you use the Service Workers option, a **loading animation will appear once** upon first visit (as the service worker is registered). All further visits are as seamless as the proxy, no loading screen, but without Fleek as a constant middleman.

## Next Steps: Building Canister-based Services

![canister services](https://fleek-team-bucket.storage.fleek.co/Blog Inline/Group 5643.png)

Now, let’s switch gears from **short-term to long-term planning.** What’s the “Beyond” in “To DFINITY and Beyond”? For a while now, at Fleek we have been working on becoming an aggregator of the base layer of the Open Web, combining its protocols (Internet Computer, IPFS, Filecoin, Ethereum, Textile, GunDB, ENS, etc.) to create the bits and pieces that together form the base layer of web services that the new internet needs.

The piece that was always left hanging was the centralization and lack of trustlessness in the infrastructure behind the services we provide. An issue that even Dapps today face, while relying on things like AWS in spite of having a partially decentralized infrastructure powered on Ethereum.

It’s an element of trust that is hard to remove, but has to be removed at some point in time so that we can have the base infrastructure of the new web built on trustless and decentralized technologies.

## Next Steps: Why do it on the Internet Computer

![dfinity base layer](https://fleek-team-bucket.storage.fleek.co/Blog%20Inline/whydfinity.png)

With DFINITY and the Internet Computer, we want to achieve that. It’s still pretty early, but V1 of this trustless hosting product is an amazing example of the steps we can take by combining a suite of tools built on IPFS, Filecoin, Ethereum, and so on, **with a trustless infrastructure living on the Internet Computer’s** blockchain network.

The Internet Computer, as a computational blockchain, **provides us with the missing link.** A computational blockchain with smart contract functionality, capable of powering and hosting web services in a trustless, permissionless, and decentralized way.

It’s like the benefits we see in using Ethereum for Dapps, but applied to the **core of the web, which is its supporting infrastructure (hosting / storage / serverless functions / and so on..)**. All this, software logic, data,

So, the natural next step for us is to begin transitioning Fleek from a centralized infrastructure and product, **to an Internet Computer, canister-based solution**. Today, our IPFS hosting and storage, for example, relies on us running the infrastructure for it, and the interface itself is dependent on a Web 2.0 infrastructure.

By moving everything, procedurally to the Internet Computer in a canister-setup that’s open and entirely user-controlled, we can **begin building the new set of canisters** for web services (hosting, storage, auth…). Entirely trustless, community-managed, and permissionless.

For us **the Internet Computer is an additive to all the protocols we currently work with**, not at all a replacement. In concept it would allow us to take an element of trust (us running an IPFS-node infrastructure for storage and hosting) and build it decentralized, on top of the Internet Computer, so that our suite of services is not reliant on Web 2.0 infrastructure only we control.

![teamwork](https://fleek-team-bucket.storage.fleek.co/Blog%20Inline/yeahteamwork.gif)

It acts, in a way, as the **base layer** that ensures all other protocols we work with, and the features they provide, are built on top of and supported by an open network, and not closed or centralized providers.

**We are on an exploratory phase,** but in our history of combining Open Web protocols, we have found nothing but great use cases. **IPFS and Filecoin** set the groundwork for new distributed ways of handling storage and hosting; its content addressing and hash model is simply AMAZING.

Much like we combined IPFS and Filecoin in the past (when building [Space](http://space.storage/), for example) to achieve things like user-controlled storage, but where users have Ethereum-based accounts, or can have web-based IPFS storage where keys are protected and decentralized thanks to [GunDB](https://gun.eco/).

We believe that marrying them both to the Internet Computer in the future, could open up amazing opportunities for creating performant and distributed content networks. A couple of things that we’re excited about is having **dual-hosting, on IPFS and the Internet Computer,** or on IPFS systems running on that network itself; which we are exploring.

## Next Steps: Wrapping it up 🚀

This deep dive into the Internet Computer's Alpha, and first batch of releases in Fleek features for it has helped us get our hands dirty, and really understand the potential behind the Internet Computer and what it could mean for the Open Web.

We’re pumped and as confident as ever, that reaching **fully decentralized, trustless, and user-controlled** services is not only possible, but the technology for it is already here, peeling off a bazillion of the remaining trust layers that today affect web services, Dapps, and more complex platforms that can’t be fully decentralized yet because they rely on services like AWS.

It’s month 3 on the year, and we have already announced Space, [the Space SDK](https://blog.fleek.co/posts/introducing-space-sdk-release), [Filecoin Archiving](https://blog.fleek.co/posts/filecoin-archiving-backup-fleek-sites-and-storage), [Fleek Storage V2](https://blog.fleek.co/posts/fleek-storage-is-out-of-beta-v2-release), **and now our first steps onto the Internet Computer**, and a future transition to a decentralized and user-controlled version of our platform that looks as bright as ever.

We told you **2021 in the Open Web was going to be AWESOME** 🔥

So stay posted, because we’re bringing more updates soon, and we are not thinking about slowing down our pace with these kinds of surprises!

- [Sign up](https://app.fleek.co/) to try Fleek
- Join our [Community Chat](https://slack.fleek.co/)
- Follow us on [Twitter](https://twitter.com/fleek)
- Subscribe to our [Youtube channel](https://www.youtube.com/channel/UCBzlwYM0JjZpjDZ52-SLUmw)
- Check out our [Tech Docs](https://docs.fleek.co/)
- Contact us at support@fleek.co
