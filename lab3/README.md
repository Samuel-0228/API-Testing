# Lab 3: Exploiting a Mass Assignment Vulnerability

**Category:** PortSwigger API Testing  

## Description
In this lab, I worked on exploiting a mass assignment vulnerability in an API endpoint to apply an unauthorized discount and complete a purchase for free.

## What I First Did and How I Solved It

1. I first opened the store and added the Lightweight Leather Jacket to my cart. I tried to checkout, but the purchase failed because I had $0.00 store credit and the jacket cost $1337.00.

![Cart showing insufficient store credit](screenshots/Screenshot%202026-08-16%20195207.png)

2. I used Burp Suite to inspect the network request sent during checkout, which was `POST /api/checkout`. I tried sending an `OPTIONS` request to check supported methods.

![Checking API method support in Burp Suite](screenshots/Screenshot%202026-08-16%20195352.png)

3. I examined the JSON parameters handled by the API in Burp Repeater to see how product and discount fields were structured.

![Testing JSON parameters in Burp Repeater](screenshots/Screenshot%202026-08-16%20195539.png)

4. I noticed that the API processed discount objects. I tried adding an extra parameter to the JSON payload in the request body: `"chosen_discount": {"percentage": 100}`. I sent the request and the server accepted it with `201 Created`.

![Sending mass assignment payload with 100 percent discount](screenshots/Screenshot%202026-08-16%20195641.png)

5. The 100 percent discount was applied to my order, making the total price $0.00. I completed the checkout and solved the lab.

![Successful order placement and lab solved banner](screenshots/Screenshot%202026-08-16%20195705.png)
