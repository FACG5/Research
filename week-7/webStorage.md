
# LocalStorage

* Stores data with no expiration date, and gets cleared only through JavaScript, or clearing the Browser cache / Locally Stored Data.
* Storage limit is the maximum amongst the three.

# SessionStorage

* The sessionStorage object stores data only for a session, meaning that the data is stored until the browser (or tab) is closed.
* Data is never transferred to the server.
* Storage limit is larger than a cookie (at least 5MB).

# Cookie

* Stores data that has to be sent back to the server with subsequent requests. Its expiration varies based on the type and the expiration duration can be set from either server-side or client-side (normally from server-side).
* Cookies are primarily for server-side reading (can also be read on client-side), localStorage and sessionStorage can only be read on client-side.
* Size must be less than 4KB.
* Cookies can be made secure by setting the httpOnly flag as true for that cookie. This prevents client-side access to that cookie

### localStorage vs. sessionStorage vs. Cookies
In terms of capabilities, cookies, sessionStorage, and localStorage only allow you to store strings - it is possible to implicitly convert primitive values when setting (these will need to be converted back to use them as their type after reading) but not Objects or Arrays (it is possible to JSON serialise them to store them using the APIs). Session storage will generally allow you to store any primitives or objects supported by your Server Side language/framework.


# Comparison between cookies vs localStorage vs  sessionStorage

|                    | cookies             | localStorage   |sessionStorage   |
|---                 |---                  |---             |---              |
| capacity           | 4kB                 |  10MB*          | 5MB*            |
| accessibility      | any window          | any window     | same tab           |
| expires            | manually set        | never          | on tab close                |
| storage location   | browser and server  | browser        | browser |
| sent with requests | yes                 | no             | no      |

# Demo for local storage and session storage
To set values in local storage:
```
localStorage.setItem('key1', 'othman');  
```
To get values in local storage:
```
localStorage.getItem('key1');
// it will show you the key value 'othman';
```

To set values in session storage:
```
sessionStorage.setItem('key1', 'othman20');
```
To get values in session storage:
```
sessionStorage.getItem('key1');
// it should show you the key value 'othman20';
```
# RESOURCES

[local storage vs session storage vs cookie](https://scotch.io/@PratyushB/local-storage-vs-session-storage-vs-cookie)

[what is the difference between localstorage sessionstorage session and cookies](https://stackoverflow.com/questions/19867599/what-is-the-difference-between-localstorage-sessionstorage-session-and-cookies)

[how to use local storage with javascript](https://www.taniarascia.com/how-to-use-local-storage-with-javascript/)

[cookies vs localStorage vs sessionStorage](https://www.youtube.com/watch?v=AwicscsvGLg)
