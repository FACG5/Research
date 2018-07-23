# Client Side vs. Server Side

## Website scripts run in one of two places:

 1. client side (front-end): The client of a website refers to the web browser that is viewing it.

 2. server side (back-end): The server of a website is, of course, the server that hosts it.

 Most web coding languages are designed to run on either the server side or the client side. This largely defines how they   work. Here are some examples.

 In General: 

 1. Front-end scripting is good for anything that requires user interaction, such as a simple game.

 2.  Back-end scripting is good for anything that requires dynamic data to be loaded, such as a notice  that tells the user they’re logged in.

 ### hint: To write your own front-end and back-end scripts, you should learn web development.

## Front-end/ client-side

The front-end, or the client-side, is everything involved with the browser and relates to what the user sees. It only uses HTML, CSS and JS.

UX/ UI
Input fields
Imagery
Buttons
Animations/ transitions

## Back-end/ server-side

The backend is mostly worried about things like security, structure and content management.

Some uses of the back-end include:

Database creation, integration, and management
Content management system (CMS) development
API integration
Security settings and hack prevents
Collecting analytics and statistics e.g. system reports of server load, number of visitors, geography of visitors, etc.
Backup and restore technologies for website’s files and DB.

How the back-end and front-end works together
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
