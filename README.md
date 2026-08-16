# PortSwigger API Testing Writeups

## Overview
In this project, I worked on studying and completing the API testing labs from PortSwigger Web Security Academy ([PortSwigger API Testing](https://portswigger.net/web-security/api-testing)).

API testing involves analyzing how application programming interfaces send, receive, and process data between clients and servers. In web security, testing APIs helps identify vulnerabilities such as exposed API documentation, unhandled HTTP request methods, broken authorization, and mass assignment flaws.

I completed three practical labs to practice finding and exploiting these API security issues:

1. **Lab 1: Exploiting an API Endpoint Using Documentation**  
   I searched for exposed API documentation, found hidden endpoints, and used an undocumented API call to delete a target user account.  
   For step by step details and screenshots, see the [Lab 1 Writeup](lab1/README.md).

2. **Lab 2: Finding and Exploiting an Unused API Endpoint**  
   I inspected HTTP requests in Burp Suite, discovered an unadvertised `PATCH` method on a price endpoint, modified the product price to zero, and purchased the item for free.  
   For step by step details and screenshots, see the [Lab 2 Writeup](lab2/README.md).

3. **Lab 3: Exploiting a Mass Assignment Vulnerability**  
   I analyzed the JSON payload used during checkout, added an unauthorized parameter to inject a 100 percent discount, and placed an order for free.  
   For step by step details and screenshots, see the [Lab 3 Writeup](lab3/README.md).

---

## Individual Lab Reports
* [Lab 1 Report and Screenshots](lab1/README.md)
* [Lab 2 Report and Screenshots](lab2/README.md)
* [Lab 3 Report and Screenshots](lab3/README.md)
