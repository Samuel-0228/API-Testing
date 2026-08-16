# Lab 2: Finding and Exploiting an Unused API Endpoint

**Category:** PortSwigger API Testing  

## Description
In this lab, I worked on discovering an hidden API method on an endpoint, changing the product price, and buying an item for free.

## What I First Did and How I Solved It

1. I first logged into the shop and looked at the items for sale.

![Looking at product page](screenshots/Screenshot%202026-08-16%20180604.png)

2. I tried to buy the Lightweight Leather Jacket, but it cost $1337.00 and I only had $0.00 store credit.

![Trying to buy item with insufficient funds](screenshots/Screenshot%202026-08-16%20180627.png)

3. I used Burp Suite to capture my HTTP requests while using the shop.

![HTTP history in Burp Suite](screenshots/Screenshot%202026-08-16%20190932.png)

4. I found an API request that gets the product price: `GET /api/products/1/price`.
5. I sent an `OPTIONS` request to `/api/products/1/price` in Burp Suite to test what HTTP methods were supported. The server returned `Allow: GET, PATCH`. This showed me that an unused `PATCH` method existed.

![Testing OPTIONS request in Burp Suite](screenshots/Screenshot%202026-08-16%20191059.png)

6. I sent the request to Burp Repeater so I could modify it.

![Sending request to Burp Repeater](screenshots/Screenshot%202026-08-16%20191344.png)

7. I tried sending a `PATCH` request to `/api/products/1/price` in Burp Repeater with JSON payload `{"price": 0}`. The server responded with 200 OK.

![Sending PATCH request to set price to 0](screenshots/Screenshot%202026-08-16%20192028.png)

8. I refreshed the shop page and saw that the item price was updated to $0.00.

![Item price updated to zero on web page](screenshots/Screenshot%202026-08-16%20192045.png)

9. I added the jacket to my cart for $0.00 and clicked checkout. The order went through successfully and I solved the lab.

![Checkout completed and lab solved](screenshots/Screenshot%202026-08-16%20192111.png)