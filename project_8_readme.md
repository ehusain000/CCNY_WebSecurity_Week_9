# Project 8 - Pentesting Live Targets

Time spent: 10 hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue

Vulnerability #1: SQLI Injection

![Week9_1](https://user-images.githubusercontent.com/32075350/56174054-a816c400-5fbe-11e9-8820-0a9d347a5b29.gif)

It can be seen in the gif above, when the apostrophe (') is written in the end of the URL for the green and redwe are simply redirected to the same page. In the blue; however, it results in a database query failiure which shows that the blue site had SQL Injection vulnerability.


Vulnerability #2: Session Hijacking/Fixation

![Week9_2 9 06 01 PM](https://user-images.githubusercontent.com/32075350/56174822-69830880-5fc2-11e9-92f4-49bf0f08fe66.gif)

In a session that was logged in alreadu, we similpy copy the session id using the link given int the codepath website. Next we go to a different session where we are logged out and change it session to that of the logged in one. This would give the attacker logged in priveleges.



## Green

Vulnerability #1: Cross-Site Scripting

![Week9_4](https://user-images.githubusercontent.com/32075350/56175516-83721a80-5fc5-11e9-8d91-a5250b4057a9.gif)

To figure out this vulnerability, first go to the contact us tab. In here type <script>alert('FOUND IT!')</script> for you name and comment and then type in a random email for the email secion. To see this vulnerability in action, log in and go to feedback as shown in the GIF.


Vulnerability #2: User Enumeration 
![Week9_3](https://user-images.githubusercontent.com/32075350/56175198-0abe8e80-5fc4-11e9-8e03-43bccd712614.gif)

It can be seen in the GIF whenever a nonexistent username such as 'admin' is entered, the message is shown in non-bold letters. Moreover, insepecting it shows that the class for the wrong username is failed. On the other hand, the correct username displays the message in bold letters and the class for the correct username is failure.




## Red

Vulnerability #1: Insecure Direct Object Reference

![Week9_5](https://user-images.githubusercontent.com/32075350/56176370-da2d2380-5fc8-11e9-890d-18a79388fab8.gif)

To see that the red has a Insecure Direct Object Reference I tried to change salesperson id for the blue and green initially; however, I was redirected to the page. In the red, however, when we change the salesperson id to 11 we get a salesperson who was fired:
Lazy Lazyman (FIRED FOR STEALING)


Vulnerability #2: Cross-Site Request Forgery

![Week9_6](https://user-images.githubusercontent.com/32075350/56177824-04351480-5fce-11e9-81bb-2a9256352c78.gif)

As shown in the GIF, what I basically did was that in my users page I updated/changed the csrf token in the html code and changed the user name. Doing so in the Green and Blue gave me a "Invalid Request"; however the red allowed me to make the changes.

## Notes

The challenges were pretty straight forward.

