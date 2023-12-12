# CRUD

Create, Read, Update, Delete

## Status Codes Based On REST Methods

**In your own words, describe what each group of status code represents:**

>*100’s = Informational... something wonky is going on, but server is still trying to satisfy the client's request.*
>*200’s =Success... (or at least eventual success in the case of 202)*
>*300’s =Redirection... the url you are pinging isn't it anymore... maybe this is temporary, but it may permanent... try this url instead.*
>*400’s =Client Error... client side goofed. Often a bad url or improper token provided so the request could not be processed.*
>*500’s =Sever Error... client request was valid, but the server is acting wonky.*

**What is a status code 202?**

>*Request valid, but it's gonna be awhile.*

**What is a status code 308?**

>*Redirect to a new URL (permanent)*

**What code would you use if an update didn’t return data to a client?**

>*204... often used to tell client that deletion is complete.*

**What code would you use if a resource used to exist but no longer does?**

>*410*

**What is the ‘Forbidden’ status code?**

>*403*

## Things I want to know more about

>*When would there be multiple choices (status code 300)?*
