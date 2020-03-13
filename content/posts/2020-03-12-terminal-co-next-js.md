---
template: post
title: How to deploy a Next.js app onto IPFS using Terminal.co
slug: terminal-nextJS
draft: false
date: 2020-03-12T14:06:38.733Z
description: >-
  We’ll create a Next.js app and deploy it with Terminal.co. This whole process
  should take 10 minutes.
category: Tutorial
tags:
  - Tutorial
  - Guide
---
![](/media/nextjs/Next.JS+Terminal.png)

## Overview

We’ll create a Next.js app and deploy it with Terminal.co. This whole process should take 10 minutes.

Tools:

* Terminal.co account
* GitHub account
* node.js/npm

### Step 1: Set Up a Repo on Github

Create an empty repository and clone it.

![](/media/nextjs/CreateRepo.png)

Create a Next.js app using:

`$ mkdir nextjs && cd nextjs` `$ npm init --y'
'$ npm install next react react-dom`

![](/media/nextjs/CreateNextjsapp.png)

Open `package.json` and add in the following scripts

```
"scripts": {
    "dev": "next",
    "build": "next build",
    "start": "next start",
    "export": "next export"  
}
```

![](/media/nextjs/Openpackagejson.png)

Create a `next.config.js` file in the root directory

```
module.exports = {
  exportTrailingSlash: true,
  exportPathMap: function() {
    return {
      '/': { page: '/' }
    };
  }
};
```

![](/media/nextjs/createNextConfigJS.png)

Let’s create some pages: Create a folder called pages Inside pages, create `index.js`

```
// index.js
import Link from "next/link";

export default function Index() {
  return (
    <div>
      <h1> Index </h1>
      <Link href="/about">
        <a> About </a>
      </Link>
    </div>
  );
}
```

and `about.js`

```
// about.js
export default function About() {
  return (
    <div>
      <h1> About </h1>
    </div>
  );
}
```

It should look something like this

![](/media/nextjs/indexJSAboutJS.png)

To test, run `npm run dev` and visit localhost:3000

![](/media/nextjs/localhost3000.png)

git add, commit, push

![](/media/nextjs/gitcommit.png)

### Step 2: Set Up Terminal.co

Sign into: https://sites.terminal.co/

Sign in with Github

![](/media/nextjs/signin.png)

Add New Site

![](/media/nextjs/addsite.png)

Connect with Github.

![](/media/nextjs/connectGithub.png)

Pick your Next.js repository.

![](/media/nextjs/picknextjsrepo.png)

To create a new site:

Build command: `npm install && npm run build && npm run export`

Publish directory: `out`

Deploy Site

![](/media/nextjs/deploySite.png)

Once complete, view your website.

![](/media/nextjs/viewSite.png)

You can view the website using the provided domain name.

`https://<your-custom-domain>.tmnl.co`

Or verify with the CID.

`https://ipfs.io/ipfs/<CID>`

![](/media/nextjs/verifyCID.png)

### Step 3: Updates

Terminal will automatically redeploy your website whenever you make changes on GitHub. Make sure to provided domain name will remain the same and will point to the new CID. This enables you to build fast modern websites hosted on IPFS.

* [Sign up](https://terminalbeta.typeform.com/to/kionHH) for private beta early access
* [Join](https://join.slack.com/t/terminal-public/shared_invite/enQtOTM1MjQ3NTExMDU3LTNkYjU1ZGJhZGUyYjgwN2I3OThjY2U5OThlMGY2MGY0OGYxMDI1OWIwMTMwYzViZGY4ZGU0NDA0YmY4ZjVhOTg) our #community
* [Check out](Https://docs.terminal.co) our technical documentation
