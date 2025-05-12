# Web Infrastructure Design Project

This project focuses on understanding and designing different web infrastructure setups, starting from a simple single-server architecture to more complex, distributed, secured, and scalable systems. The goal is to grasp the fundamental concepts behind each component and their roles in delivering a website to users.

## Learning Objectives

By the end of this project, you should be able to explain the following concepts without relying on external resources:

* Draw a diagram illustrating a web stack built with sysadmin/devops track projects.
* Explain the function of each component within a web infrastructure.
* Explain the concept of system redundancy.
* Understand and explain the following acronyms: LAMP, SPOF, QPS.

## Requirements

* A `README.md` file at the root of the project folder is mandatory.
* For each task, you need to whiteboard a design diagram. Take a picture or screenshot of your diagram.
* Upload the screenshot of your completed whiteboard to an image hosting service (e.g., Imgur).
* Insert the link to your screenshot in the corresponding answer file.
* After pushing your answer file to GitHub, insert the GitHub file link into the URL box.
* You will be required to whiteboard each task in front of a mentor, staff, or student without any computer or notes.
* Focus on the specific requirements mentioned in each task. Avoid unnecessary details unless asked during the whiteboarding session.

## Tasks

### 0. Simple web stack (mandatory)

Design a one-server web infrastructure that hosts the website reachable via `www.foobar.com`. Start your explanation from a user trying to access the website.

**Requirements:**

* Use **1 domain name**: `foobar.com` configured with a `www` record pointing to your server IP `8.8.8.8`.
* Use **1 server** containing:
    * 1 web server (Nginx)
    * 1 application server
    * 1 set of application files (your codebase)
    * 1 database (MySQL)
* Explain the following aspects of this infrastructure:
    * What is a server?
    * What is the role of the domain name?
    * What type of DNS record is `www` in `www.foobar.com`?
    * What is the role of the web server?
    * What is the role of the application server?
    * What is the role of the database?
    * What does the server use to communicate with the user's computer?
* Explain the issues with this infrastructure:
    * Single Point Of Failure (SPOF)
    * Downtime during maintenance (e.g., deploying new code requiring a web server restart)
    * Inability to scale with increased traffic.

**Repo:**

* GitHub repository: `holbertonschool-system_engineering-devops`
* Directory: `web_infrastructure_design`
* File: `0-simple_web_stack`

### 1. Distributed web infrastructure (mandatory)

Design a three-server web infrastructure that hosts the website `www.foobar.com`.

**Requirements:**

* Add:
    * 1 load-balancer (HAproxy)
    * 2 servers (each containing):
        * 1 web server (Nginx)
        * 1 application server
        * 1 set of application files (your codebase)
        * 1 database (MySQL)
* Explain the following aspects of this infrastructure:
    * For every additional element, explain why you are adding it.
    * What distribution algorithm is your load balancer configured with, and how does it work?
    * Does your load-balancer enable an Active-Active or Active-Passive setup? Explain the difference between both.
    * How does a database Primary-Replica (Master-Slave) cluster work?
    * What is the difference between the Primary node and the Replica node in regard to the application?
* Explain the issues with this infrastructure:
    * Where are the Single Points Of Failure (SPOF)?
    * Security issues (no firewall, no HTTPS).
    * No monitoring implemented.

**Repo:**

* GitHub repository: `holbertonschool-system_engineering-devops`
* Directory: `web_infrastructure_design`
* File: `1-distributed_web_infrastructure`

### 2. Secured and monitored web infrastructure (mandatory)

Design a three-server web infrastructure that hosts the website `www.foobar.com`, ensuring it is secured, serves encrypted traffic, and is monitored.

**Requirements:**

* Add:
    * 3 firewalls
    * 1 SSL certificate to serve `www.foobar.com` over HTTPS
    * 3 monitoring clients (data collectors for Sumologic or other monitoring services)
* Explain the following aspects of this infrastructure:
    * For every additional element, explain why you are adding it.
    * What are firewalls for?
    * Why is the traffic served over HTTPS?
    * What is monitoring used for?
    * How does the monitoring tool collect data?
    * Explain what to do if you want to monitor your web server Queries Per Second (QPS).
* Explain the issues with this infrastructure:
    * Why is terminating SSL at the load balancer level an issue?
    * Why is having only one MySQL server capable of accepting writes an issue?
    * Why might having servers with all the same components (database, web server, and application server) be a problem?

**Repo:**

* GitHub repository: `holbertonschool-system_engineering-devops`
* Directory: `web_infrastructure_design`
* File: `2-secured_and_monitored_web_infrastructure`

### 3. Scale up (mandatory)

**Readme:** Application server vs web server

**Requirements:**

* Add:
    * 1 server
    * 1 load-balancer (HAproxy) configured as a cluster with the other one.
    * Split components (web server, application server, database) onto their own dedicated servers.
* Explain the following aspects of this infrastructure:
    * For every additional element, explain why you are adding it.

**Repo:**

* GitHub repository: `holbertonschool-system_engineering-devops`
* Directory: `web_infrastructure_design`
* File: `3-scale_up`
