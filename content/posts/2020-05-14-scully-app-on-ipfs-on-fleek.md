---
template: post
title: Scully app on IPFS on Fleek
slug: scully-on-ipfs-on-fleek
draft: false
date: 2020-05-14T04:02:37.816Z
description: >-
  Get started with deploying a Scully app on IPFS on Fleek
category: Tutorial
socialImage: ./media/scully/hero.png
tags:
  - general
  - ipfs
  - scully
---

![](images/scully/hero.png)

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

Scully ia a wicked fast and the best static site generator for Angular which is the best static site generator for Angular projects for building JAMStack.

# Install Angular CLI

Scully runs totally on Angular and to get scully running you need to have an angular application setup in your computer, the first step would be to get the Angular CLI installed via the command below

```
npm install -g @angular/cli
```

Once the Angular CLI is done installing, you would also have to create an angular project using the command below

```
ng new your-app-name
```

This command will bootstrap a complete AngularJS app for you, you would also be prompted if you would like to add Angular routing, that should be a yes and also the kind of css style you would like to use, for example, CSS, SCSS, LESS, and the likes. You can see a picture of my process below

![](images/scully/terminal.png)

Imediately that process is over, the next step is to enter into the directory of the project you are working on using the command below

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

In the same path to your application you would have to install scully the tooling package via npm in your app using the command below

```
ng add @scullyio/init
```

![](images/scully/terminal2.png)

The next step is to add support for a blog into your scully app using the command below, should take less that 5 seconds to install, This command adds the blog modules's routes to your Angular app. In addition, it creates a ./blog folder for the blog's markdown files.

```
ng generate @scullyio/init:blog
```

![](images/scully/terminal3.png)

Once you open your codebase you will find a folder called blog with a specific markdown file, that mean's the process is done, if you would like to generate a new blopost in scully, run the comand below

```
ng generate @scullyio/init:post --name="New Post"
```

Next we would open the `app-routing.module.ts` file under the directory app and copy the below routing in

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

Once that is done build your app in a `.dist` file because scully demands we have one, use the command below

```
ng build
```

Visit http://localhost:4200/ for a privew in your browser of your scully app

