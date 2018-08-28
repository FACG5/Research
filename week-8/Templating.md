# Templating And  Server Side Rendering


## Server-side Rendering
* This approach allows the user to receive everything at once and also caters to browsers that don't have good JavaScript support, but it also means everything takes a bit longer before the browser gets the first ``` <htmt>```    tag.

## Client-side Rendering
* This approach allows you to render your structure quickly on the server-side, then let the user's JavaScript pick up the actual content.

### Server-side pros:
* Search engines can crawl the site for better SEO.
* The initial page load is faster.
* Great for static sites.
### Server-side cons:
* Frequent server requests.
* An overall slow page rendering.
* Full page reloads.
* Non-rich site interactions.
### Client-side pros:
* Rich site interactions
* Fast website rendering after the initial load.
* Great for web applications.
* Robust selection of JavaScript libraries.
### Client-side cons:
* Low SEO if not implemented correctly.
* Initial load might require more time.
* In most cases, requires an external library.


## What problems do templating languages solve ?
* Your application has much interactivity and it is very responsive . 
* You are developing a singlepage web application with multiple views . 
* Make it easy to manage the website .
* You  use new syntax that may be more easier. 
* You have alot of tools is already made and you should not make it again.


## some examples of functionality that templating languages provide : 
```
{{parmeter}}
{{object.parmeter}}
{{function parmeter}}
{{function paramOne='value' paramTwo='value'}}
```