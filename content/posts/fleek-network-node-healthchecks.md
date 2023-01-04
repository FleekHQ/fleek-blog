---
template: post
draft: false
title: 'Fleek Network: Node health checks'
slug: fleek-network-node-health-checks
date: 2023-01-04T23:00:00Z
canonical: ''
socialImage: https://storageapi.fleek.one/fleek-team-bucket/fleek-network-node-health-checks.png?202301041235
description: Provides instructions to do node health checks
category: Tutorial
tags:
- DCDN
- Guide
- Getting Started
- Fleek Network
- health checks

---

![](https://storageapi.fleek.one/fleek-team-bucket/fleek-network-node-health-checks.png?202301041235)

## Introduction

In Software development, a health check means checking the health status of a resource to determine whether the resource is operating correctly. Here, we'll look into how to check the health of a Fleek Network node.

The purpose of the guide is to provide basic information about the node resource by exposing the host, port numbers, logs during runtime, etc.

You should have followed our [getting started guide](#fleek-network-getting-started-guide) and have the Ursa CLI installed in the machine terminal you're accessing to follow along.

We'll give you a basic introduction into the topic, but you should also appreciate the fact that development is ongoing and other factors, such as the introduction of features, may cause malfunction of a node beyond what a simple health check can hint about the network.

For any unexpected behavior, we appreciate the contribution of the community by any means which includes reporting to our [Discord](https://discord.gg/fleekxyz), opening a [PR](https://github.com/fleek-network), reporting issues in our [Github repository](https://github.com/fleek-network/ursa/issues), etc.

## Topics
  - [What's a node health check?](#whats-a-node-health-check)
  - [Available interface]()
  - [Conclusion](#conclusion)

## What's a node health check?

A Node health check is exactly what it sounds like, a way of checking the health status of a Fleek Network node!

A Node operator can do a health check (as it's common among system operators worth their title) to get feedback and see if the resource is working! It's a good practice for a Node operator to do it frequently, as otherwise there'd be no way of knowing whether or not the Node is running. For example, some advanced operators automate this process by using cronjobs and getting reports via email, etc.

Health checks are valuable and a must for all the Node operators, as they are incentivized to participate in the network by making their resources available which the reward mechanism evaluates.

Rewards are only a given for good behavior and thus an unhealthy Node, or bad management can cause disappointment. A decentralized and permissionless network, which is beyond anyone's control (us included) requires some education by the users.

A system can be highly customizable and understanding some basics can help you achieve success as a node operator, resource health checking is important! There are many reasons why'd want to learn how to operate, such as the "how to do node health checks" we instruct here.

Fleek Network depends on the Node operator's success, thus we try to keep things simple and try to motivate you to learn for the network's overal health! That's what a Node health check is about, your contribution!

## Conclusion

We've walked through the most basics of where the configuration file is located, the configuration settings we use to setup and run the node, the different configuration sections we have, but most importantly the identity section.

Additionally, a brief guide on the [identity](#identity), more specifically an introduction to the [type of keys](#type-of-keys) and [key privacy](#key-privacy), which we find important to understand for anyone seriously interested in running a node by hinting into some system administration and security principals.

In the future, we'll introduce more advanced topics that will help you improve into the knowledge you get from this, but we are glad that you followed this guide and got some comprehension to help you manage the key store.

While we do our best to provide the most clear instructions, there's always space for improvement, therefore feel free to make any contributions by messaging us on our [Discord](https://discord.gg/fleekxyz) or by opening a [PR](https://github.com/fleek-network) in any of our repositories 🙏.

Discover more about the project by [watching/contributing on Github](https://github.com/fleek-network/ursa), following us on [Twitter](https://twitter.com/fleek_net), and joining [our community Discord](https://discord.gg/fleekxyz) for all the best updates!