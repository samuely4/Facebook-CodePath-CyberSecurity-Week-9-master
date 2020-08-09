# Week-9
> Time taken to complete the lab and the assignment: 3 hrs.

> The objective of this assignment is to identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.
>> NOTE: Each version of the site has two of the six following vulnerabilities:
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
 ## Assignment Report:
 
 ### GREEN
 > Vulnerability 1: Cross-Site Scripting (XSS)
- [x] GIF Walkthrough
  ![picture alt](https://github.com/Samuel665/Week-9/blob/master/green_XSS.gif "green_xss")
       
       
- [x] Brief Overview to recreate the exploit
* By submitting malicious javascript code into the feedback section of the Contact Us form, an administrator views the feedbacks and the stored XSS script will get executed.
* ```<script>alert('hacked, haha....');</script```

> Vulnerability 2: Username Enumeration
- [x] GIF Walkthrough
  ![picture alt](https://github.com/Samuel665/Week-9/blob/master/green_userEnum.gif "green_UserEnum")
       
       
- [x] Brief Overview to recreate the exploit
* If a username does exist and entered but with the wrong password, the following sentence is bolded: **Log in was unsuccessful**
* If the user name does not exist, the error message will not be bolded: Log in was unsuccessful
       

 ### BLUE
 > Vulnerability 1: SQL Injection (SQLi)
- [x] GIF Walkthrough
  ![picture alt](https://github.com/Samuel665/Week-9/blob/master/blue_sqlHack.gif "blue_sqli")
       
- [x] Brief Overview to recreate the exploit
 * By injecting SQL code into the id paremeter, we find that the site is vulnerable to SQL Injection.
    * ```' OR SLEEP(5)=0--'``` causes the webpage to sleep for 5 seconds and then display the user with id 1 by default.
    * ```11' AND SLEEP(5)=0--'``` causes the webpage to sleep for 5 seconds and then fetch the information of the user with id 11.
    
 > Vulnerability 2: Session Hijacking
 - [x] GIF Walkthrough
  ![picture alt](https://github.com/Samuel665/Week-9/blob/master/blue_sessionHack.gif "blue_sessionHack")
       
- [x] Brief Overview to recreate the exploit
 * By accessing ```hacktools/change_session_id.php``` form while logged in, we can have the current session ID. Now, we can put the session ID we obtained into a non-loggd-in session casuing that session to gain unauthenticated access to the account which was logged in and from which the session ID got hacked.

### RED

> Vulnerability 1: Cross-Site Request Forgery (CSRF)
 
- [x] GIF Walkthrough
  ![picture alt](https://github.com/Samuel665/Week-9/blob/master/red_CRSF.gif "red_CSRF")
       
       
- [x] Brief Overview to recreate the exploit
 * By creating an HTML form, You can edit salesperson's personal data such as their first and last name.
 * NOTE: [link to html form](https://github.com/Samuel665/Week-9/blob/master/red_CSRF.html "link to html form")
       
       
 > Vulnerability 2: Insecure Direct Object Reference (IDOR)
       
- [x] GIF Walkthrough
  ![picture alt](https://github.com/Samuel665/Week-9/blob/master/red_IDOR.gif "red_IDOR")
       
- [x] Brief Overview to recreate the exploit
 * Having logged in as an administrator, you can see salespersons who are not visible to the public. However, by changing the id parameter, you can gain access to this information without being logged in.
 # Note
 * Materials used to do this assignment are to be found in the repository
