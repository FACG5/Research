# Architecture

Website scripts run in one of two places:

 1. client side (front-end): The client of a website refers to the web browser that is viewing it.

 2. server side (back-end): The server of a website is, of course, the server that hosts it.

 Most web coding languages are designed to run on either the server side or the client side. This largely defines how they work. 

### In General: 

 1. Front-end scripting is good for anything that requires user interaction, such as a simple game.

 2.  Back-end scripting is good for anything that requires dynamic data to be loaded, such as a notice  that tells the user they’re logged in.

 ### hint: To write your own front-end and back-end scripts, you should learn web development.

### Front-end/ client-side

The front-end, or the client-side, is everything involved with the browser and relates to what the user sees. It only uses HTML, CSS and JS.

* UX/ UI
* Input fields
* Imagery
* Buttons
* Animations/ transitions

### Back-end/ server-side

The backend is mostly worried about things like security, structure and content management.

### Some uses of the back-end include:

* Database creation, integration, and management
* Content management system (CMS) development
* API integration
* Security settings and hack prevents
* Collecting analytics and statistics e.g. system reports of server load, number of visitors, geography of visitors, etc.
* Backup and restore technologies for website’s files and DB.

## How the back-end and front-end works together?
The web application creates, deletes, changes, renames, etc items in the database. For example, when a customer purchases a ticket, that creates an item in the database, but when they have a change in their order or they wish to cancel, the item in the database is changed.

A server, in the simplest form, is a computer accessed remotely that runs software to fulfill requests from clients. In our example, the server the customer’s browser is communicating with is where the database is stored and modified.

## Client side vs server side

#### Server-Side Code
> Server-side handles logging in, personal information and preferences and provides the specific data which the user wants (and allows new data to be stored).

* Run with any language the server can run.
* Doesn't rely on the users hardware / software.
* Cannot be seen by the user (unless something is terribly wrong).
* Stores persistent data (user profiles, instatweets, mybook pages, etc.).
* Creates the page that the user finally sees (this is generally only true in web applications that choose to render most of their layouts on the server).

#### Client-Side Code
> Client-side makes the page interactive, sorting data in different ways if the user asks for that by clicking on elements with event triggers.

* Languages used include: HTML, CSS, and Javascript. Nothing else.
* Parsed by the user’s browser.
* Can be seen and edited by the user in full.
* Cannot store anything that lasts beyond a page refresh.
* Cannot read files off of a server directly, must communicate via HTTP requests.
* Creates the page that the user finally sees (this is generally only true in single page applications).

#### Validation
**Server Side Validation**

In Server Side Validation, the input submitted by the user is sent to the server and validated there. After the server validation, the feedback is sent back to the client by a new dynamically generated web page.

It is often better to validate user input on the Server Side because it is easier to protect against malicious users, who can bypass your Client Side scripting language and submit dangerous input to the server.

---

**Client Side Validation**

In the Client Side Validation you can provide a better user experience by responding quickly at the browser level. When you perform a Client Side Validation, all the user inputs are validated in the user's browser itself. Client Side validation does not require a round trip to the server. This type of validation is done on the browser side using script languages such as JavaScript or HTML5 attributes.

For example, if the user enters an invalid email format, you can show an error message immediately before the user moves to the next field.

Mostly the Client Side Validation depends on the JavaScript Language, so if users turn JavaScript off, it can easily bypass and submit dangerous input to the server. So the Client Side Validation can not protect your application from malicious attacks on your server resources and databases.

------------------------------------
top 5 server side languages are:

php 81.7%

asp 16.0%

java 3%

static files 1.6%

ColdFusion 0.7%

## Pros of Using Node.js:

* It's easy to learn:
 According to Node.js’s 2016 User Survey Javascript is one of the most popular programming languages for front-end development. Nearly every front-end developer is familiar with this universal language. Therefore, it is much easier for them to switch to using Node.js at the back-end. It requires less effort and less time to learn and work with, even for a junior Javascript programmer.

* Freedom in Building Apps.
While Ruby on Rails is a framework that imposes rules and guidelines of developing software in a particular way, Node.js gives you much more space and freedom in doing it your own way. Node.js is completely unopinionated, meaning you start building everything from scratch. It can execute basic tasks, but gives you only the bare minimum from a fresh install, making it less restricted.

* Fullstack JS.
Before Node.js, Javascript was only used for client-side development. It was necessary to use a different server-side programming language. In practice, you had to hire separate devs for backend and for frontend. With a growing popularity of Node.js fullstack JavaScript became a reality. Nowadays it is possible to write both front-end and back-end of web applications in Javascript, making app deployment much easier and more efficient.

* Active Community.
The Node.js developers community is a very active and vibrant group of developers who contribute to constant improvement of Node.js. Thanks to the cooperation of JavaScript programmers and their input to the community you get access to a ton of ready solutions, codes in Github and many more possibilities. Even though, it is still at a relatively early stage of development, the community is dynamically evolving and its members go the extra mile to provide others with best and reliable solutions.

* Simultaneous Request Handling.
Node.js provides the non-blocking IO system that lets you process numerous requests concurrently. The system makes simultaneous request handling much better than in other languages like Ruby or Python. Incoming requests are queued up and executed sequentially in a fast manner. In effect your app will take up much less system RAM, achieve high scalability levels and in a result will perform faster.

##Cons of Using Node.js for Your Back-end:
*Unstable API
One of the biggest disadvantages of Node.js is that it lacks consistency. Node.js’ API changes frequently, and the changes are often backward-incompatible. When this happens, programmers are forced to make changes to the existing code base to make it compatible with the latest version of the Node.js API.

* More Development Time
The fact that Node.js is unopinionated can also be seen as a drawback by some developers. Ruby on Rails provides you with a lot of directions from a fresh install and guides you into their way of doing things, but with Node.js you basically need to write everything from scratch. It might result in a decrease in productivity, slowing your work down. However, if you cooperate with an experienced team of programmers who have internally developed a good processes for developing and maintaining code, you do not have to worry about efficiency.

* Not Suitable for Heavy-Computing Apps
Node.js doesn’t support multi-threaded programming yet. It is able to serve way more complicated applications than Ruby, but it’s not suitable for performing long-running calculations. Heavy computations block the incoming requests, which can lead to decrease of performance . While Node.js is perfect for complex apps, in the case of software which requires some heavy-computing it might perform less effectively.

* Immaturity of Tools
Even though, the core Node.js is stable, many packages in the npm registry (pre-installed node package manager that organises the installation and management of third-party Node.js programs) are still of poor quality or have not been properly documented. As it is mostly an open source ecosystem, numerous tools have not been supervise

# Resources  
1. https://www.codeconquest.com/website/client-side-vs-server-side/
2. https://www.quora.com/How-do-front-end-and-back-end-technologies-work-together
