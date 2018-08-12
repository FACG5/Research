# Attacks


## What are the following types of attack and How can you defend against ?

### 1. Man In The Middle (MITM)

<p align="center">
<img src="http://1kam1.com/wp-content/uploads/2017/03/man-in-the-middle-mitm.jpg">
</p>

A **man-in-the-middle (MITM) attack** is a form of eavesdropping where communication between _two_ _users_ is monitored and modified by an unauthorized party. Generally, the attacker actively eavesdrops by intercepting a public key message exchange and retransmits the message while replacing the requested key with his own.

In the process, the two original parties appear to communicate normally. The message sender does not recognize that the receiver is an unknown attacker trying to access or modify the message before retransmitting to the receiver. Thus, the attacker controls the entire communication.

This term is also known as a **janus attack** or a **fire brigade attack**.

#### Example:
let say `http://www.ocbtc.com`  is a legitimate URL. But when website’s URL is hacked it becomes `http://www.theattacker.com/http://www.ocbtc.com`

If an intruder manages to get into a strategic position, they can steal information, take control of an ongoing session to gain access to private network resources, conduct DoS attacks, corrupt transmitted data, or introduce new information into network sessions.

<p align="center">
<img src="http://orbit-computer-solutions.com/wp-content/uploads/2015/10/Man-in-the-middle-attacks.jpg">
</p>

1. When a victim requests a webpage, the host of the victim makes the request to the host of the attacker’s.
2. The attacker’s host receives the request and fetches the real page from the legitimate website.
3. The attacker can alter the legitimate webpage and apply any transformations to the data they want to make.
4. The attacker forwards the requested page to the victim.


#### Ways to Defend Against a Man-in-the-Middle Attack :
1. VPN
2. Proxy Server with Data Encryption
3. Secure Shell Tunneling

> Resource: 
> * [www.techopedia.com](http://www.techopedia.com)
> * [www.orbit-computer-solutions.com](http://www.orbit-computer-solutions.com)

---

### 2. Cross Site Scripting (XSS)
**XSS attacks** occur when an attacker uses a web application to send malicious code, generally in the form of a browser side script, to a different end user.

#### Cross-Site Scripting (XSS) attacks occur when:

Data enters a Web application through an untrusted source, most frequently a web request.
The data is included in dynamic content that is sent to a web user without being validated for malicious content.

#### XSS attacks can generally be categorized into two categories:
1. **Stored XSS Attacks**
Stored attacks are those where the injected script is permanently stored on the target servers, such as in a database

2. Reflected XSS Attacks
Reflected attacks are those where the injected script is reflected off the web server, such as in an error message, search result, or any other response that includes some or all of the input sent to the server as part of the request. Reflected attacks are delivered to victims via another route, such as in an e-mail message, or on some other website. When a user is tricked into clicking on a malicious link, submitting a specially crafted form, or even just browsing to a malicious site, the injected code travels to the vulnerable web site, which reflects the attack back to the user’s browser.

#### Example 1
The following JSP code segment reads an employee ID, eid, from an HTTP request and displays it to the user.

```
<% String eid = request.getParameter("eid"); %> 
...
Employee ID: <%= eid %>
```

The code in this example operates correctly if eid contains only standard alphanumeric text. If eid has a value that includes meta-characters or source code, then the code will be executed by the web browser as it displays the HTTP response.

Initially, this might not appear to be much of a vulnerability. After all, why would someone enter a URL that causes malicious code to run on their own computer? The real danger is that an attacker will create the malicious URL, then use e-mail or social engineering tricks to lure victims into visiting a link to the URL. When victims click the link, they unwittingly reflect the malicious content through the vulnerable web application back to their own computers. This mechanism of exploiting vulnerable web applications is known as Reflected XSS.

#### Example 2
The following JSP code segment queries a database for an employee with a given ID and prints the corresponding employee's name.

```
<%... 
 Statement stmt = conn.createStatement();
 ResultSet rs = stmt.executeQuery("select * from emp where id="+eid);
 if (rs != null) {
  rs.next(); 
  String name = rs.getString("name");
%>

Employee Name: <%= name %>
```

As in Example 1, this code functions correctly when the values of name are well-behaved, but it does nothing to prevent exploits if they are not. Again, this code can appear less dangerous because the value of name is read from a database, whose contents are apparently managed by the application. However, if the value of name originates from user-supplied data, then the database can be a conduit for malicious content. Without proper input validation on all data stored in the database, an attacker can execute malicious commands in the user's web browser. This type of exploit, known as Stored XSS, is particularly insidious because the indirection caused by the data store makes it more difficult to identify the threat and increases the possibility that the attack will affect multiple users. XSS got its start in this form with websites that offered a "guestbook" to visitors. Attackers would include JavaScript in their guestbook entries, and all subsequent visitors to the guestbook page would execute the malicious code.

As the examples demonstrate, XSS vulnerabilities are caused by code that includes unvalidated data in an HTTP response. There are three vectors by which an XSS attack can reach a victim:

As in Example 1, data is read directly from the HTTP request and reflected back in the HTTP response. Reflected XSS exploits occur when an attacker causes a user to supply dangerous content to a vulnerable web application, which is then reflected back to the user and executed by the web browser. The most common mechanism for delivering malicious content is to include it as a parameter in a URL that is posted publicly or e-mailed directly to victims. URLs constructed in this manner constitute the core of many phishing schemes, whereby an attacker convinces victims to visit a URL that refers to a vulnerable site. After the site reflects the attacker's content back to the user, the content is executed and proceeds to transfer private information, such as cookies that may include session information, from the user's machine to the attacker or perform other nefarious activities.
As in Example 2, the application stores dangerous data in a database or other trusted data store. The dangerous data is subsequently read back into the application and included in dynamic content. Stored XSS exploits occur when an attacker injects dangerous content into a data store that is later read and included in dynamic content. From an attacker's perspective, the optimal place to inject malicious content is in an area that is displayed to either many users or particularly interesting users. Interesting users typically have elevated privileges in the application or interact with sensitive data that is valuable t

_
 
Click here to type a chat message. Supports GitHub flavoured markdown.


---

### 3. Cross Site Request Forgery (CSRF)

* Cross-Site Request Forgery (CSRF) is an attack that forces an end user to execute unwanted actions on a web application in which they're currently authenticated. CSRF attacks specifically target state-changing requests, not theft of data, since the attacker has no way to see the response to the forged request. With a little help of social engineering (such as sending a link via email or chat), an attacker may trick the users of a web application into executing actions of the attacker's choosing. If the victim is a normal user, a successful CSRF attack can force the user to perform state changing requests like transferring funds, changing their email address, and so forth. If the victim is an administrative account, CSRF can compromise the entire web application.

#### EXAMPLE OF A CROSS-SITE REQUEST FORGERY ATTACK:
```html
<div style="display:none;">
    <iframe id="frame" name="frame"></iframe>

    <form target="frame" id="formid" action="http://www.mybank.com/transfer" method="post">
      <input type="hidden"
          name="toAccount"
          value="55555555555555555555"/>
      <input type="hidden"
          name="amount"
          value="666"/>
       <input type="hidden"
          name="fee"
          value="5.0"/>
      <input type="hidden"
          name="description"
          value="EVIL ACCOUNT"/>
      <input type="submit"
          value="View"/>
    </form>

    <script>
    document.getElementById("formid").submit();
    </script>
    </div>
```
#### Synchronizer token pattern:

* A token must be added to the request for it to complete successfully. This token is generated when the user first creates their session and is stored as session data on the server (not as a cookie).

**EX:**
```html
<input type="hidden" name="csrfmiddlewaretoken" value="KbyUmhTLMpYj7CD2di7JKP1P3qmLlkPt" />
```
> Resource: [hdivsecurity.com](hdivsecurity.com)

---



### By :
> * Asmaa 
> * Ahmad L 
> * Ahmad A
