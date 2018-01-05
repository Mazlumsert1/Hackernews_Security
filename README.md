# Hackernews_Security

1. _Definition of our **assets** and **threat model** of our project:_

The definition of an **asset** is what we want to project, if an vulnerabillity is exploited then it could damage our assets. 
    
    **1.2 Data asset:**
The valuable assets that needs to be protected, could be our Database since we have confidental data and records of client information such as username and password. Here a back-up of your data could be a very good idea. 
    
    **1.3 Software asset:** 
Another asset could be if someone gets access to your code, they could get an idea of how code works and do some malicius stuff and find some vulnerabilities. Generely if an hacker has access to your application vulnerabilities can be found easily. 

**Threats**
Using our **Risk Matrix** we can also have an idea about what kind of **threats**, we could face in the near future. 


**Risk Matrices**

| Negligible | Marginal |Critical |Catastrophic|
| --- | --- | --- | --- |
| Certain | Malware |  |  |  |
| Likely | DOS | phishing attack |  |  |
| Possible | XSS |  | db hack |  |
| Unlikely |  | Theft of hardware |  |  |
| Rare |  |  | Lightning strikes OR Fire |  |

According to our **Risk Matrix** the worst thing that could happen to us is that if our DB is hacked, that could lead to that we would loose data. 


## OWASP ZAP Sikkerhedstest

En sikkerhedstest analysere din hjemmesides kode og hvordan den interagere med andre objekter for at identificere svagheder eller fejl, så vi kan forhindre at ondsindede hackere ikke får uautoriseret adgang til webserver eller andre netværk tilknyttet vores webserver. Vi har gjort brug af OWASP Zed Attack Proxy (ZAP) sikkerhedsværktøj til finde sikkerhedsfejl i vores Hackernews applikation. Nedenstående er en demonstration af OWASP ZAP Scan af vores system - `165.227.136.184`

![Text](https://github.com/HakimiX/UFO/blob/master/Models/OWASP2.jpg)

I OWASP’s brugergrænsefladen kan vi se at vores applikation er udsat for ”Clickjacking” angreb. Clickjacking angreb er når en hacker benytter gennemsigtige eller uigennemsigtige lag til at narre brugere til at klikke på et link eller en knap på en anden side, selvom brugerens hensigt var at klikke på øverste lag. 

> ”X-Frame-Options header is not included in the HTTP response to protect against Clickjacking attacks” - OWASP ZAP

![Text](https://github.com/HakimiX/UFO/blob/master/Models/OWASP1.jpg)

OWASP gør os opmærksom på at vores web browser XSS beskyttelse ikke er aktiveret. HTTP XXS beskyttelses response header er en funktion af Chrome og Safari, der har til formål at stoppe sider der indlæses med reflekterende XXS angreb (Cross-site scripting). Cross-site scripting er når en hacker påfører din hjemmeside ondsindede scripts. Via din hjemmeside kan en hacker påfører ondsindede scripts til dine kunders browser.  

> ”Web Browser XSS Protection is not enabled, or is disabled by the configuration of the X-XSS-Protection http response header on the web server” - OWASP ZAP

