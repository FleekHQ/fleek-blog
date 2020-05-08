---
template: post
title: Scully app on IPFS on Fleek
slug: scully-on-ipfs-on-fleek
draft: true
date: 2020-05-14T04:02:37.816Z
description: >-
  Get started with deploying a Scully app on IPFS on Fleek
category: Tutorial
socialImage: ./media/scully/bg.png
tags:
  - general
  - ipfs
  - Scully
---

![](images/scully/bg.png)

Get Started with deploying your Scully app, In this tutorial, we will learn how to create a Scully app and deploy it on Fleek so it can be shared through IPFS.

```
# Table of Contents
- What is Scully?
- Install Angular CLI
- Starting an Angular Project
- Installing Scully
- Push to GitHub and Linking Fleek
- Congratulations
```

# Getting Started with Scully

Scully is a wicked fast and the best static site generator for Angular which is the best static site generator for Angular projects for building JAMStack.

# Install Angular CLI

Scully runs totally on Angular and to get Scully running you need to have an angular application set up in your computer, the first step would be to get the Angular CLI installed via the command below

```
npm install -g @angular/cli
```

Once the Angular CLI is done installing, you would also have to create an angular project using the command below

```
ng new your-app-name
```

This command will bootstrap a complete AngularJS app for you, you would also be prompted if you would like to add Angular routing, that should be a yes and also the kind of css style you would like to use, for example, CSS, SCSS, LESS, and the likes. You can see a picture of my process below

![](images/scully/terminal.png)

Immediately that process is over, the next step is to enter into the directory of the project you are working on using the command below

```
cd your-app-name
```

Start your angular project in your terminal using the command below

```
ng serve --open
```

This command will start the Angular project and open up right away in your browser once the preview is ready on `http://localhost:4200/`

![](images/scully/terminal.png)

# Installing Scully

In the same path to your application, you would have to install Scully the tooling package via npm in your app using the command below

```
ng add @scullyio/init
```

![](images/scully/terminal2.png)

The next step is to add support for a blog into your Scully app using the command below, should take less than 5 seconds to install, This command adds the blog modules' routes to your Angular app. Also, it creates a ./blog folder for the blog's markdown files.

```
ng generate @scullyio/init:blog
```

![](images/scully/terminal3.png)

Once you open your codebase you will find a folder called blog with a specific markdown file, that means the process is done if you would like to generate a new blogpost in Scully, run the command below

```
ng generate @scullyio/init:post --name="New Post"
```

Next, we would open the `app-routing.module.ts` file under the directory app and copy the below routing in

```typescript
import { NgModule } from '@angular/core';
import { Routes, RouterModule } from '@angular/router';


const routes: Routes = [{ path: 'blog', loadChildren: () => import('./home/home.module').then(m => m.HomeModule) }, { path: 'home', loadChildren: () => import('./home/home.module').then(m => m.HomeModule) }];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule { }
```

under the `home.component.ts` you would have to inject the routing service that would automatically route your application to `home.component.html` copy and paste the below in your `home.component.ts` file

```typescript
import { Component, OnInit } from '@angular/core';
import {ScullyRoutesService} from '@scullyio/ng-lib';
import {Observable} from 'rxjs';

@Component({
  selector: 'app-home',
  templateUrl: './home.component.html',
  styleUrls: ['./home.component.css']
})
export class HomeComponent implements OnInit {
  links$: Observable<any> = this.scully.available$;

  constructor(private scully: ScullyRoutesService) {}

  ngOnInit() {
    this.links$.subscribe(links => {
      console.log(links);
    });
  }
}
```
Once that is all done visit `home.component.html` and paste the below inside

```html
<router-outlet></router-outlet>

<h5>Now, Let's deploy to IPFS on Fleek!</h5>
<p>Visit <a href="https://fleek.co" target="_blank">Fleek.co</a></p>
```

Once that is done build your app in a `.dist` file because Scully demands we have one, use the command below

```
ng build
```

Visit http://localhost:4200/ for a preview in the browser of your Scully app

# Push to GitHub and Linking Fleek

The first step is to push your Scully app to Github. That will allow Fleek to gain access to your project for the deployment.

In our case, I've pushed my project to this repo: git@github.com:Developerayo/scully-app-on-ipfs-on-fleek.git

Now, we must log to fleek and create a new site and click/find the repo you created

![](images/scully/fleek1.png)

Luckily for us, Fleek has automatically detected our Scully App and filled the build settings with the right information, but the one thing you have to specify is the publish directory, which should be set to `dist/your-app-name.com`. Immediately that is set click on `Deploy Site`. 

![](images/scully/fleek2.png)

Let's wait a bit for the site to deploy. This should take no longer than a few minutes.

Upon deployment, Fleek will automatically assign a default URL to the site. 
Here is mine: https://holy-glade-7553.on.fleek.co/

![](images/scully/fleek3.png)

## Congratulations!

Congrats! You've just joined the family by deploying your Scully app to IPFS with Fleek.

We love to see what our users come up with. Do not hesitate to share your work with us by tweeting your deployed site!

* [Sign up](https://app.fleek.co) to try for yourself
* [Join](https://join.slack.com/t/fleek-public/shared_invite/zt-bxna7y1d-PbVdut4rgHt5jM6Zjg9g9A) our Community Chat
* [Follow](https://twitter.com/FleekHQ) us on Twitter
* [Read](https://docs.fleek.co/) out our Tech Docs
* Contact us at support@fleek.co 