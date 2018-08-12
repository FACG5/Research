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
