---
template: post
draft: false
title: 'Fleek Network: How to deal with files using Content Addressable aRchives'
slug: fleek-network-packaging-content-addressed-data
date: 2022-12-13T13:00:00.000+00:00
socialImage: https://storageapi.fleek.co/fleek-team-bucket/fleek-network-how-fleek-network-deals-with-files.png?202212131140
canonical: ''
description: How to deal with files using Content Addressable aRchives
category: Tutorial
tags:
- CDN
- Guide
- Getting Started
- Fleek Network
- GIT
- CAR
- Content Addressable aRchive

---

![](https://storageapi.fleek.co/fleek-team-bucket/fleek-network-how-fleek-network-deals-with-files.png?202212131140)


## Introduction

Fleek Network uses the IPLD CAR ([Content Adressable aRchive](https://ipld.io/specs/transport/)) as the data structure and packing of data in the network. IPLD provides the primatives to share valuable information in a flexible and extensible manner across the network for the semantic web or Linked Data vision of the next web. 

In this guide, we'll look into what we have in the web today for accessing files, the web of tomorrow, the importance of immutable data, hash functions, content addressability, metadata and a practical hands down approach on handling of files in Fleek Network.

## Prerequesites

To follow this guide, you will need:

- Some experience with command-line interfaces

For other topics, check our [getting started guide](https://blog.fleek.co/posts/fleek-network-getting-started-guide).

### Table of Contents

- [How Fleek Network deals with files](#how-fleek-network-deals-with-files)
  - [Immutability](#immutability)
  - [Content Addressing](#content-addressing)
  - [Hash functions](#hash-functions)
  - [Interplanetary linked data (IPLD)](#interplanetary-linked-data-ipld)
  - [Content Addressable aRchive (CAR)](#content-addressable-archive-car)

***

## How Fleek Network deals with files?

The way content is handled, stored and distributed defines how trustworthy is a protocol. Some of the primitives to achieve it, has roots in immutability, verificartion, the [Semantic Web](https://www.w3.org/standards/semanticweb/) and [Linked Data](https://www.w3.org/standards/semanticweb/data). 

When you use Fleek Network, you either provide your data packed into a format called a Content Archive ([CAR](https://ipld.io/specs/transport/car)) or an existing [CID](https://docs.ipfs.tech/concepts/content-addressing/#what-is-a-cid) of a CAR file, which hash addresses are unique and universally addressable.

### Immutability

Some of the principles that help us provide guarantees to end-users,
require a high-ability for content verification, as a consequence, immutability of files are critical to the system. To emphasize, immutability means the state of not changing, or being unable to change!

The web is nothing more and nothing less than a mirror of what it has become from within and among its main actors, the service providers, the central authorities and the powers they have when managing user files.

Fleek Network deals with files in a manner where the content determines the address in which the user of the system can locate and verify it unquestionably. This is possible due to cryptography, of which the same data always produce the same hash deterministically.

A file which content determines the hash, but also impossible to invert it. We shouldn't be able to reconstruct the data from a hash. It's unique, not two files produce the same file or content. Thus, a small change in the content should always generate a completely different hash.

In retrospect, what we have in the web today are files acessible via a URL address and the problem with this approach is that the content is not intrinsically tight to the address e.g. the content can change and the URL remaining the same. That is the problematic way we access files in the web today, that we call "Location addressing", and the way we solve it for the web of tomorrow, is called "Content addressing".

> When content is immutable, we can verify its integrity and thus provide the ability get the content from anyone and everywhere. The ability to get it from anywhere, lead us to the decentralised and distributed nature of content storage and delivery in the Fleek Network.

### Content Addressing

Content addressing is where we use a hash to access the content, and which allow us to verify that the content we received is the content we asked for! For this we use a special hash called CID ([Content Identifier](https://docs.ipfs.tech/concepts/content-addressing/#what-is-a-cid)), a cryptography hash function that maps input of arbitrary size to output of a fixed size - the content identifiers are short, regardless of the size of the content, and the address does not actually tell us where the content is stored. It's also interesting to observe, that the CID is a sort of string like binary that is human-friendlier in comparison to the underlying binary, that is way longer.

> Caching and deduplication are possible due to immutability of content e.g. if content changes, let's say that an image has some new detail, the files share many of the same bytes. The amount of data we have to transfer to fetch is minimum, we'd only pull the difference. In today's web, we'd have to transfer both files in full, which is a worse path on resource allocation and performance.

### Hash functions

The hash function for creating [CID's](https://docs.ipfs.tech/concepts/content-addressing/#what-is-a-cid) use `sha-256`, but there is support for other hashing algorithms, such as sha1 (used by Git), sha2-256, sha3-255, blake2b-160, etc. Some older algorithms are proven to not be collision free, so if algorithms can break, we have to swith the hash algorithm we use in the future! The problem with this switching of algorithms is the need of finding a future proof way of identifying the hash functions used to generate the hash, as well as the hash name.

[Multihash](https://multiformats.io/multihash/) is a protocol and comes in to play to provide us the metadata useful for future proofing. To explain it in simple terms we'll provide an example, it is the composition where a bash is placed at the end, a prefix as a number to identify the algorithm used and a number to idenfify the hash name. Thereafter, we'd start raising some questions. With the simple example provided here, how would we get the data back without the ability to identity how it was encoded? Some users could use [cbor](https://en.wikipedia.org/wiki/CBOR), [protocol buffers](https://en.wikipedia.org/wiki/Protocol_Buffers), [json](https://en.wikipedia.org/wiki/JSON), etc; and there might be plenty of good reasons why of those choices. Maybe it's a compact binary encoding that is very efficient for storage, or easy to work with, etc.

What's important is that it is the users choice and why [IPLD](https://ipld.io) becomes useful for Fleek Network's use-cases. A system for understanding and working with data, made up of a [Data Model](https://ipld.io/docs/intro/hello-world/#data-model-and-codecs) and [Codecs](https://ipld.io/docs/intro/hello-world/#data-model-and-codecs), some tools for [Linking](https://ipld.io/docs/intro/hello-world/#linking), and then a handful of other [Powerful Features](https://ipld.io/docs/intro/hello-world/#powerful-features) that help ups develop a decentralized application.

### Interplanetary linked data (IPLD)

[Interplanetary linked data (IPLD)](https://ipld.io/) provide us all the metadata prefixes to soothe the system needs, provide us the data model of the content-addressable web, as discussed earlier. IPLD is a set of conventions for creating decentralised data-structures that are universally addressable and linkable.

> These addressable and linkable data structures will allow us to do for data what URLs and links did for HTML web pages (Quote from [IPLD](https://ipld.io/docs/)).

### Content Addressable aRchive (CAR)

For all the reasons demonstrated here, Fleek Network uses the IPLD CAR [Content Adressable aRchive](https://ipld.io/specs/transport/) to transport IPLD data. IPFS IPLD defines transport as of both file and stream format, meaning packing IPLD data together and interactivity that involves requests and responses.

As discussed above in [Hash functions -> multihash](#hash-functions), the CAR files contain data encoded in a particular codec, in the Fleek Network, the IPLD codec supported is called [dag-pb](https://ipld.io/docs/codecs/known/dag-pb/).

Fleek Network only works with car files ([CARv1](https://ipld.io/specs/transport/car/carv1/)) and ([CARv2](https://ipld.io/specs/transport/car/carv2/)) soon, this means that it only computes car files, as input and output! Therefore, the decoding of the files is handled by the clients. We're still on early development days, where a client library is in early development, which the should abstract some the possible hurdles, but at the end it will be simple to use.

## Final Thoughts

Discover more about the project by [watching/contributing on Github](https://github.com/fleek-network/ursa), following us on [Twitter](https://twitter.com/fleek_net), and joining [our community Discord](https://discord.gg/fleekxyz) for all the best updates!