# Pen Testing Live Targets

Time spent: **50** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:

* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each color is vulnerable to only 2 of the 6 possible exploits. First discover which color has the specific vulnerability, then write a short description of how to exploit it, and finally demonstrate it using screenshots compiled into a GIF.

## Blue

Vulnerability #1: SQL Injection

Description:
I found that when I intercepted one of the salesman request on burp suite I was able to use able to obtain the following command:%27%20OR%20SLEEP(5)=0--%27. Using this I was able to inject this on a different salesman request which causes the Database command to wait for 5 seconds while quering the data.

<img src="blueTargetSql_Injection.gif">


## Green

Vulnerability #1: Username enummeration

Description:
Given the username 'jmonroe99' was a valid user, I was able to try editing different usernames similar. I found that the developer created 2 similar 'unsuccessful' cases. When entering jmonroe99, the unsuccessful output is in bold while the jmonroe9 output is the same message except it is not bolded.Inspecting both html codes I noticed that the developer created a 'failure' and 'failed' case. 
<img src="green target Username enummeration.gif">


## Red

Vulnerability #1: IDOR

Description:
When clicking on each username I noticed each contained a unique 'id='. Using burpsuite intruder, running a number list payload attack I was able to see 2 restricted users by using both 'id=10' and 'id=11'
<img src="red target IDOR.gif">


## Notes

Describe any challenges encountered while doing the work
I was really comfratable using IDOR,SQL injection and username enummeration attacks because they were concepts I understood the best and had the best practice using them. 
