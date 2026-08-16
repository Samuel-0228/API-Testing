# Lab 1: Exploiting an API Endpoint Using Documentation

**Category:** PortSwigger API Testing  

## Description
In this lab, I worked on finding hidden API documentation and using an exposed API endpoint to delete a user account.

## What I First Did and How I Solved It

1. I first opened the target website in my browser and started browsing around.
2. I looked for exposed API documentation by checking paths like `/api`.
3. I found the REST API documentation page. I saw a table that listed supported endpoints:
   * `GET /user/[username]`
   * `DELETE /user/[username]`
   * `PATCH /user/[username]`
4. I noticed that the `DELETE` method accepts a username parameter to delete a user.
5. I tried sending a delete request using the interactive API tool on the page. I set the username to `carlos` and sent the request: `DELETE /api/user/carlos`.

![Sending DELETE request](sreenshots/Screenshot%202026-08-16%20172547.png)

6. The server responded with HTTP 200 OK.
7. I checked the website header and saw that the lab was solved.

![Lab solved notification](sreenshots/Screenshot%202026-08-16%20172616.png)

---

[Next: Lab 2 Writeup](../lab2/README.md)