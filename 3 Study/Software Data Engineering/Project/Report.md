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

Our Project is a blogging solution for communities of different sizes or to manage personal stuff where you can read, create and search for different articles. Our solution is different from existing solutions as it is lightweight and easy to deploy on your own server as it is completely containerized. It doesn't depend on any proprietary software or library so you can customize it as per your need as it is open sources on Github. Frontend is build using **React** and **Tailwind CSS**, It has features of Google Login as well as Login with Email and Password. You can write posts with a rich text editor and also upload a Image which will be stores in Amazon S3(Simple Storage Service) bucket to be shown on the feed. Frontend talks to backend with a library **axios**(a Promise-based HTTP client). 

![[Assets/Pasted image 20221113135056.png]]
<p align="center" >Figure 1: Flow of the app. Client using webapp requests server for content. </p>
Backend is build using Flask(web application framework written in python) and uses **mongoDB** database (a NoSQL general purpose document database). As mentioned previously backend is completely containerized with Docker, flask server runs with waitress(a production-quality pure-Python Web Server Gateway Interface[^1] server) and Nginx(Nginx is a web server that can be used as a reverse proxy, load balancer etc.) for load balance and to serve static files. 

![[Assets/Pasted image 20221113135454.png]]
<p align="center" >Figure 2: Architecture of server</p>
Server is built using **Publisher-Subscriber pattern** which enable an application to announce events to multiple interested consumers asynchronously, without coupling the senders to the receivers[^2]. Author will publish the article and all the use on the site will receive the article.

![[Assets/Pasted image 20221113134559.png]]
<p align="center" >Figure 1: Showcase of how Publisher-Subscriber pattern works. Request from  publisher goes to through server and then to server. </p> 












## Summary of Work done





## Work done





## Results





## Conclusion

[^1]: The Web Server Gateway Interface is a simple calling convention for web servers to forward requests to web applications or frameworks written in the Python programming language.

## Reference
[^2]: https://learn.microsoft.com/en-us/azure/architecture/patterns/publisher-subscriber