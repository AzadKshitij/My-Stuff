---
tags:
	- SDE
	- study
---

%%
1. Report in pdf/doc format [ [Team Member details, Introduction- 300 words, Summary of Work done - 300 words, Work done, Results, Conclusion - 300 words] ] 
2. Source code - zipped or link to online repository with readme file  
3. Link of demo if applicable  
4. 10 slides ppt focusing on work done and team member's contribution   
5. Video recording of demo - optional for regular students, compulsory for executive candidates
%%

## Team Member Details
- Sandeep Swami (B19ME072)
- Kshitij Sanodariya (B19ME075)

## Introduction

Our Project is a blogging solution for communities of different sizes or to manage personal stuff where you can read, create and search for different articles. Our solution is different from existing solutions as it is lightweight and easy to deploy on your own server as it is completely containerized. It doesn't depend on any proprietary software or library so you can customize it as per your need as it is open sourcesed on Github. 

**React JS** Library React is an efficient, flexible and open-source JavaScript Library for building simple and scalable front-ends Major benefits of using ReactJS are it is declarative which makes easier to create interactive UIs as it uses states which can be updated when the data changes in the UI part along with that it is component based which makes encapsulated components that manage their own state, then compose them to make complex UIs and **Tailwind CSS** , It has features of **Firebase Authentication** to allow users to sign in to a website using one or more sign-in methods, including email address and password sign-in, and federated identity providers such as Google Sign-in.. You can write posts with a rich text editor and also upload a Image which will be stores in Amazon S3(Simple Storage Service) bucket to be shown on the feed. Frontend talks to backend with a library **axios**(a Promise-based HTTP client). 

Backend is build using Flask(web application framework written in python) and uses **mongoDB** database (a NoSQL general purpose document database). As mentioned previously backend is completely containerized with Docker, flask server runs with waitress(a production-quality pure-Python Web Server Gateway Interface server) and Nginx(Nginx is a web server that can be used as a reverse proxy, load balancer etc.) for load balance and to serve static files. 

Server is built using **Publisher-Subscriber pattern** which enable an application to announce events to multiple interested consumers asynchronously, without coupling the senders to the receivers. Author will publish the article and all the use on the site will receive the article.

## Summary of Work done

Started with research and thinking about possible ways of solving the problem. As it was a group project we divided it into two major part Frontend and Backend.

Frontend consist of UI creation, User experience communication with backend and performance 

Backend consist of server, database management, load balancer etc. Server created with python and flask framework. We used MongoDB as a database as it is a general purpose database, does not have strict model rule, it can be scaled horizontally, its easy to use etc. 

We also used version control with git and Github.



## Work done

Work Done By Kshitij
- Design architecture of backend. Ended up choosing Pub-Sub architecture. 
![[Assets/Pasted image 20221113135056.png]]
<p align="center" >Figure 1: Flow of the app. Client using webapp requests server for content. </p>

![[Assets/Pasted image 20221114103141.png]]
<p align="center" >Figure 2: Flow of the app. From Author(user) to database -> all users of the app. </p>

![[Assets/Pasted image 20221113134559.png]]
<p align="center" >Figure 3: Showcase of how Publisher-Subscriber pattern works. Request from  publisher goes to through server and then to server. </p> 

- Designed Models to store in database.
![[Assets/Pasted image 20221115100436.png | center ]] 
<p align="center" >Figure 4: User and Post Model to store in database.</p>
- Containerized backend with docker.
- Deployed Nginx and MongoDB with Docker to work with Flask.
![[Assets/Pasted image 20221113135454.png]]
<p align="center" >Figure 5: Architecture of server</p>
- Implemented image storage with S3.
- In frontend, implemented communication with backend using **axios**.
- Designed Form to publish post.![[Assets/Pasted image 20221114154713.png]]

Work Done By Sandeep: 
- Created frontend with react and TailwindCSS.
**![](https://lh4.googleusercontent.com/Hr4Mi8fCgbeZ6ZI3Aly5JAqNQFfnk4pfHk3-gR59SRZxamxwPm-PJeVFbysVKy7dgP2lX2z-p0VdpsLi70JOOBDh_G4w-6YLupNv0HPxnwUpg_huXKK3CwYt327S7MtAuXTYM1dRkkBM1COLMK_LgSQkBdEqbwbaM6mUw0mH35zKlVbIVFCN27LahNzXzw)**





## Results





## Conclusion



## Reference
[^2]: https://learn.microsoft.com/en-us/azure/architecture/patterns/publisher-subscriber



[^1]: The Web Server Gateway Interface is a simple calling convention for web servers to forward requests to web applications or frameworks written in the Python programming language.


![[Assets/Pasted image 20221117010619.png]]