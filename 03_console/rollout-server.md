---
title: McNative Rollout Server
---

## Introduction

The McNative Rollout server is simple web service which caches resources and licenses from the McNative mirror server in the local environment. 
This technology is important for building a reliable and stable network. We recommend all professional networks to use at least one rollout server in your infrastructure.

## Advantages
* Independent infrastructure 
* Resource version controlling over the McNative Console
* Automatically plugin rollout to your servers
* Different profiles for production, stage and development environments 

## Architecture
As you can see in the picture, the rollout server installed on your server talks to our infrastructure to get the latest configured settings from the McNative Console. 
The rollout server will then download and cache the configured resources. 
Your game and proxy servers will contact your rollout server to get the configured resource version.

![McNative Architecture](https://raw.githubusercontent.com/McNative/McNative/master/images/rollout-server-architecture.png)

## Do I need a rollout server?
This question is very important and should be decided carefully. First we need to look at your server size and your goals with the server. 
If you are just running a simple server for you and your friends, a rollout server is not necessary. 
This technology was designed and developed for professional and medium-sized networks to build an independent infrastructure.

### Is mandatory required

For medium (100 players and more) size networks a rollout server is **always required** to create a redundant and independent infrastructure. 
We are currently not able to guarantee a 100% uptime.

### Technology based

**Cloud & dynamic server handling (recommended)**<br />
In networks with dynamic server load balancing, a rollout server should always be used. 
This can increase the server startup speed and minimize the traffic on your and our infrastructure.

**BungeeCord proxy network (optional)**<br />
This depends on you and your knowledge. If you only have a simple proxy with a view server, it is not necessary, but you are welcome to test it.

**Standalone Spigot Server (not recommended)**<br />
If you are using a simple one-instance spigot, bukkit or other server software, we do not recommend using a rollout server. 
In your case it is better to load the latest version directly from our mirror server.


## Installation & Setup

@Todo Write installation

### 1. - Download

Download the latest version from [McNative Downloads](https://downloads.mcnative.org/McNativeRolloutServer) and move it into a new folder

### 1. - Configure your rollout server the McNative console

### 1. - Configure your profiles

Open the [McNative Console](https://console.mcnative.org) and navigate to the "Rollout" section.

### 1. - Configure the rollout server

### 1. - Configure game & proxy server
