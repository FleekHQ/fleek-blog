---
template: post
draft: false
title: 'Fleek Network: Node health checks'
slug: fleek-network-node-health-checks
date: 2023-01-04T23:00:00Z
canonical: ''
socialImage: https://storageapi.fleek.one/fleek-team-bucket/fleek-network-managing-the-keystore.png?202301021625
description: Provides instructions to do node health checks
category: Tutorial
tags:
- DCDN
- Guide
- Getting Started
- Fleek Network
- health checks

---

![](https://storageapi.fleek.one/fleek-team-bucket/fleek-network-managing-the-keystore.png?202301021625)

## Introduction

In Software development, a health check means checking the health status of a resource to determine whether the resource is operating correctly. Here, we'll look into how to check the health of a Fleek Network node.

The purpose of the guide is to provide basic information about the node resource by exposing the host, port numbers, logs during runtime, etc.

You should have followed our [getting started guide](#)

## Topics
  - [Configuration file](#configuration-file)
    - [Locating the file](#locating-the-file)
    - [Configuration sections](#configuration-sections)
    - [Identity selection](#identity-selection)
  - [Identity](#identity)
    - [Type of keys](#type-of-keys)
    - [Key privacy](#key-privacy)
  - [Conclusion](#conclusion)

## Conclusion

We've walked through the most basics of where the configuration file is located, the configuration settings we use to setup and run the node, the different configuration sections we have, but most importantly the identity section.

Additionally, a brief guide on the [identity](#identity), more specifically an introduction to the [type of keys](#type-of-keys) and [key privacy](#key-privacy), which we find important to understand for anyone seriously interested in running a node by hinting into some system administration and security principals.

In the future, we'll introduce more advanced topics that will help you improve into the knowledge you get from this, but we are glad that you followed this guide and got some comprehension to help you manage the key store.

While we do our best to provide the most clear instructions, there's always space for improvement, therefore feel free to make any contributions by messaging us on our [Discord](https://discord.gg/fleekxyz) or by opening a [PR](https://github.com/fleek-network) in any of our repositories 🙏.

Discover more about the project by [watching/contributing on Github](https://github.com/fleek-network/ursa), following us on [Twitter](https://twitter.com/fleek_net), and joining [our community Discord](https://discord.gg/fleekxyz) for all the best updates!