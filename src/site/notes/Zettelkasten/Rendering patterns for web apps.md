---
{"dg-publish":true,"permalink":"/zettelkasten/rendering-patterns-for-web-apps/","title":"Rendering patterns for web apps","tags":["core/tech/web-development","status/todo"],"created":"2023-01-09T21:31:50.000+00:00"}
---


# Rendering patterns for web apps

## What is rendering?
Is the process of taking data and code into **HTML** this can be done either in the **server** or the **browser**
- all at once
- partially 


### Static Web Site
All you web pages in advance and put together in a storage bucket link between them and assign a domain to it 

#### Drawback
- No for sites that data change a lot


### Multi page apps (MPA)
The server renders a **whole new page**,
#### Drawbacks
- Full page reload
- Not feel like an app - The invention of the iPhone


### Single page app (SPA)
All the UI render happens in the browser, you start with an almost blank html page and fetch data, multiple routes based on JS, feeling instantanious 

#### Drawbacks
- Large JS bundles - initial load high
- Bad for [[SEO\|SEO]]
- 

### Server side rendering - (SSR = MPA + SPA)
Start with server render and then frontend takes over

#### Drawback
- Need server = $

### Server side generated  (SSG)
All html generated in advance static host and the js client takes over after initial load - [[JAMSTACK\|JAMSTACK]] 
- Simple hosting
- App-like experience

#### Drawbacks
Redeploy whenever the data changes


### Incremental static generation
Deploy static site and rebuild on the fly 


### Partial Hydation
Wait until the user sees the component to load the data - code splitting 


### Islands architecture


### Streaming SSG

### Resumability 


## References
