# Hackernews_Security

1. _Definition of our **assets** and **threat model** of our project:_
    
    **1.2 Data asset:**
The valuable assets that needs to be protected, could be our Database since we have confidental data and records of client information such as username and password. Here a back-up of your data could be a very good idea. 
    
    **1.3 Software asset:** 
Another asset could be if someone gets access to your code, they could get an idea of how code works and do some malicius stuff and find some vulnerabilities. Generely if an hacker has access to your application valnerabilities can be found easily. 

**Risk Matrices**

| Negligible | Marginal |Critical |Catastrophic|
| --- | --- | --- | --- |
| Certain | Malware |  |  |  |
| Likely | DOS | phishing attack |  |  |
| Possible |  |  | db hack |  |
| Unlikely |  | Theft of hardware |  |  |
| Rare |  |  | Lightning strikes OR Fire |  |

According to our **Risk Matrix** the worst thing that could happen to us is that if our DB is hacked, that could lead to that we would loose data. Using our **Risk Matrix** we can also have an idea about what kind of threats, we could face in the future. 

