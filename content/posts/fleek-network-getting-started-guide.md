---
template: post
draft: true
title: 'Fleek Network: Getting Started Guide'
slug: fleek-network-getting-started-guide
date: 2022-11-30T23:00:00Z
socialImage: ''
canonical: ''
description: ''
category: ''
tags: []

---
In this guide, we’ll have a simple look into how Fleek Network works in its current development phase and briefly share some of the core concepts like spinning up a node and putting + retrieving .car files from the network.

For those seeking advanced knowledge:

* Read our whitepaper.
* Checkout [our open source code](https://github.com/fleek-network/ursa).

### Table of Contents

* A Quick TL;DR on Fleek Network
* Why is Fleek Network Needed?
* How Does Fleek Network work?
* Running a Node

***

## Need a quick Fleek Network TL;DR?

Fleek Network is a decentralized content and application layer built on established decentralized storage protocols combined with high-speed caching and an effective delivery layer. An alternative to traditional content delivery networks without a central authority that is reliable and censorship-resistant. Fleek Network relies on blockchain technology at its core, allowing governance and token rewards as incentives for participation in serving the network.

***

## Why is Fleek Network Needed?

The demand for content delivery is skyrocketing, and due to the rise of video, gaming, and other media content popularity, demand will keep going up. Content delivery providers have a central infrastructure giving immense control to obscure authorities that can block access to content and even manipulate it.

On the other hand, content delivery services depend on costly infrastructure that requires a significant number of resources. Traditionally these are dispersed geographically but more commonly located in convenient regions for the business; that is, a resolver might only find a content delivery node close to you sometimes.

Most Web 3 services have their client-facing interfaces hosted and delivered through centralized host providers and traditional content delivery networks, breaking the trust upfront and causing immense disappointment to the end user.

Since decentralized storage is a reality, a decentralized content delivery network can help achieve the goal of providing a fully decentralized Web 3 application.

***

## How Does Fleek Network Work?

Fleek Network is built on FileCoin and IPFS for long-term and peer-to-peer storage (other decentralized storage protocols will be integrated, such as Arweave, Storj, Sia, etc). Contrary to traditional CDN networks, it grows only on demand, designed to be scalable, highly available, and fault-tolerant: meaning that it's intended to continue its normal operations despite system failures.

Content is replicated across nodes and delivered through peer-to-peer mechanisms while maintaining the user experience of traditional content delivery services we are accustomed to. Peer-to-peer technology is also helpful in providing content as quickly as possible. Fleek Network, at its basics, is a caching and delivery layer on top of FileCoin and IPFS, inheriting the benefits of years of research and the highest advancements in blockchain and internet data transmission technology.

Offers an alternative route to access content without censorship that is more performant and cheaper! Promotes a decentralized economy by caching and serving content while incentivizing participants. It features caching, load balancing, reduced round trips (RTT), and in-memory caching for more demanded content for quicker trip time for first-byte (TTFB). In counterpart, content is cleared based on access popularity.

Fleek Network relies on blockchain technology to handle governance and rewards. Adopting a shared economy model allows anyone to participate with bandwidth and computation in exchange for FLK, the native protocol token. All participants are bound to a consensus algorithm for transparency and verifiable metrics for a fairer and open community.

Clients operate with the Fleek Network independently but interact with the network via Gateway nodes. The Gateway Nodes connect users to the closest Cache Nodes that are responsible for caching, replicating, and delivery of content through client-facing HTTPS GET and PUT methods.

Fleek Network allows direct access to content instead of only being accessible via HTTP-HTTPS methods, as the content is universally addressable and linkable. Users can access Fleek Network via the Gateway or the RPC interfaces.

The Gateway Nodes act like a reverse proxy for the entire network, handling client HTTPS GET requests. There are Origin Servers that persist Client data and respond to trivial requests from Cache Nodes.

***

## Running a Node

A Fleek Network node can be built and run on your local machine. It’s an open-source project and is open for contributions.

The project is built with Rust, a general-purpose programming language, be sure to have it installed on your local machine in advance to be able to follow the guide.

We’ll clone the repository locally, build it and interact with the node through the binary or the HTTP JSON-RPC API with a client like cURL, but you can use a GUI (Postman, Insomnia, etc.) if your preference.

Start by cloning the repository located at [https://github.com/fleek-network/ursa](https://github.com/fleek-network/ursa "https://github.com/fleek-network/ursa")

    git clone git@github.com:fleek-network/ursa.git

You’ll notice that we try our best to document the project as we go, so it should be easy to follow if interested. Of course, don’t shy away from contributing with any amends or your wording poetry!

Once the git clone completes, you’ll have the latest HEAD version at the time of cloning. You should use git to fetch or pull the latest versions consequently.

Execute the install command to build and install the Fleek Network CLI.

    make install

The install command uses the Rust compiler to build; depending on how fast your machine is, it might take a while.

![](https://storageapi.fleek.co/fleek-team-bucket/Blogs/fleek-network-rust-compiler.png)

Once the Rust compiler completes generating the binary, it’ll include it in the cargo’s bin directory. On macOS and Linux this is located at `$HOME/.cargo/bin` and on Windows `%USERPROFILE%\\.cargo\\bin`. These should be in your `$PATH` environment variable. If you have customized these, check the [installation guide](https://rust-lang.github.io/rustup/installation/index.html) for any questions.

Run the CLI with the flag `version` to confirm it's available.

    ursa --version

The CLI has an optional “config.toml” for custom configuration settings. As it depends on the CLI version, you can find what’s available with the flag "help".

    ursa --help

The CLI can be called without flags or options to start a new node with default settings.

    ursa

Here’s the output of the listener's host and port numbers:

![](https://storageapi.fleek.co/fleek-team-bucket/Blogs/fleek-network-node-listeners.png)

### Put Data Via the CLI

We can interact with the network via the CLI, the HTTP endpoint "/", or the JSON-RPC API endpoint "/rcp/v0". Both HTTP and JSON-RPC are listening on port "4069”.

For today’s example, we're going to “put” a [file](https://ipfs.fleek.co/ipfs/bafybeidqdywrzg7c3b4dmm332m4b7uiakgitplz2pep2zntederxpj3odi) and then after retrieving it.

The CLI can be called without flags or options to start a new node with the default settings. It should output details about the listeners’ hosts and the port numbers.

At the current development stage, there’s only support for IPLD car file format (content addressable aRchive). If curious, learn more about “IPLD car” in the [official specs](https://ipld.io/specs/transport/car/).

As we’re keeping things simple, we’ll download an existing “car” demo file to our local machine to use later for our example.

    curl https://ipfs.fleek.co/ipfs/bafybeidqdywrzg7c3b4dmm332m4b7uiakgitplz2pep2zntederxpj3odi -o basic.car

If successful, we should have a `basic.car`.

We can check the available CLI commands to determine how to perform our desired goal and put the [car file](https://ipfs.fleek.co/ipfs/bafybeidqdywrzg7c3b4dmm332m4b7uiakgitplz2pep2zntederxpj3odi) into our network.

After we checked our base `help`, we'll find that RPC is available as a subcommand.

    ursa rpc --help

Very simple to find help by simply passing the help flat after the desired subcommand.

    ursa rpc put --help

Finally, we can put our `basic.car` file into our node.

On success, you’ll get a hash representing the data of its content; it uses a format called CID (**C**ontent **ID**entifier).

Put car file done: "bafybeifyjj2bjhtxmp235vlfeeiy7sz6rzyx3lervfk3ap2nyn4rggqgei"

### Retrieve Data Via the CLI

We can get a file as quickly as we put the file in the network.

The subcommand is `get` followed by a valid `CID` and the output `pathname` where the file will be saved.

Here’s the syntax:

    ursa rpc get <CID> <PATHNAME>

As previously explained, we can always use the flag `help` to find out more about any available subcommands.

Following up on the “put” example, we have a valid CID that was returned in response to our request in our network.

    ursa rpc get bafybeifyjj2bjhtxmp235vlfeeiy7sz6rzyx3lervfk3ap2nyn4rggqgei ./output

If successful, the output will be similar to the following:

![](https://storageapi.fleek.co/fleek-team-bucket/Blogs/fleek-network-ursa-rpc-get.png)

At this point, we are interested in the file in the “output” directory. The file is named after the CID (Content identifier) plus the file extension car (the CAR file type).

    bafybeifyjj2bjhtxmp235vlfeeiy7sz6rzyx3lervfk3ap2nyn4rggqgei.car

The content is a string binary that only an interpreter can understand. Still, you can assert the file size by executing a simple list command to check the files in the “output” directory, as follows:

    ls -hl ./output

The output in our machines shows the following:

\-rw-r--r-- 1 fleek staff 26K 29 Nov 17:23 bafybeifyjj2bjhtxmp235vlfeeiy7sz6rzyx3lervfk3ap2nyn4rggqgei.car

Notice that it's the same file size, as the original [basic.car](https://ipfs.fleek.co/ipfs/bafybeidqdywrzg7c3b4dmm332m4b7uiakgitplz2pep2zntederxpj3odi) we’ve put into the network. You can verify by using the \`cmp\` command, you'll get no output because there's no difference:

    cmp basic.car bafybeifyjj2bjhtxmp235vlfeeiy7sz6rzyx3lervfk3ap2nyn4rggqgei.car

We’ve now been successful in retrieving the original car file content we “put” into the network earlier!

***

## Final thoughts

Content delivery services have a significant position in our web experience on access to information; If not considered, it might limit access to or manipulate the information we consume.

We have learned a bit about the importance of decentralized content delivery networks to mitigate the conflicting interest we otherwise face when trusting traditional content delivery providers for a complete web three experience: reasoning and fundamentals.

Finally, we introduced an open-source solution named Fleek Network, appealed for collaboration, and gave a brief example of how simple it is to run a node on anyone’s computer!

Discover more about the project by [watching/contributing on Github](https://github.com/fleek-network/ursa), following us on [Twitter](https://twitter.com/fleek_net), and joining [our community Discord](https://discord.gg/fleekxyz) for all the best updates!