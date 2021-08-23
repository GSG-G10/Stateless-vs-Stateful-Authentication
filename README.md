# Stateless vs Stateful Authentication

###### Understanding the concept of  Stateful and Stateless Applications is the foundation upon which most architectures and designs are based upon — concepts like RESTful design are built on these foundations, so having a solid logical framework is critical.


### **Stateless application**  
###### A stateless application or process is something that does not save or reference information about previous operations. Every time it carries each operation from the scratch just like the first time and provides functionality to use the Web Servers in order to process every short-term request. For example, someone is searching a question in the search engine and pressed the Enter button. In case if the searching operation gets interrupted or closed due to some reason, you have to start a new one as there is no saved data for your previous request.

### **Stateful application**
######  A Stateful application remembers specific details of a user like profile, preferences, and user actions. This information is considered as the ‘Status’ of a system. For example, your shopping cart while using any website in Cloud. Each time you select an item and add it in your cart, you add it with the items added previously and eventually, you navigate to the checkout page.  

### **Stateless Authentication (token-based authentication)**

###### Token-based authentication enables users to obtain a token that allows them to access a service and/or fetch a specific resource without using their username and password to authenticate every request. Because the token can be a self-contained entity that conveys all the required information for authenticating the request, it is often referred to as stateless authentication. In this case, the server side does not need to maintain the state of a user.

###### The authentication token is created by the authenticating service and contains information to identify a particular user and the token validity. The token itself is cryptographically signed to prevent tampering.

###### After the token is validated by the service, it is used to establish security context for the client, so the service can make authorization decisions or audit activity for successive user requests.

###### Common standards for token-based authentication include JSON Web Tokens (JWT) and Security Assertion Markup Language (SAML).

<br>
<br>






![](https://i.imgur.com/xlZ9oaL.png)

<br>
<br>

### **Stateful Authentication (Cookie/Session Based Authentication)**

###### Stateful authentication is commonly used in many applications, especially for applications that do not require scalability too much.

###### Stateful session is created on the backend side, and the corespondent session reference Id is sent to the client. Each time the client makes a request to the server, the server locates the session memory using the reference Id from the client and finds the authentication information.

![](https://i.imgur.com/AGMunL6.png)

### Main differences between Stateful and Stateless applications:
![](https://i.imgur.com/4oJOObX.png)

The eight main differences between Stateful and Stateless applications are:
1. **State of working:** Applications in Stateful react by the current state, while Stateless applications act independently with taking into consideration previous/next request.
2. **Stored Data:** If the webserver stores data in a backend manner and uses it to identify the user as an always-connected client, the service is Stateful. While in Stateless, the server does store data, but in a database to verify user/client whenever it needs to connect.
3. **Reaction toward Clients:** In Stateful, the server thinks a client is just a dumb machine, while in Stateless, server things the client is an intelligent machine that doesn't need to depend on any state on the server-side.
4. **Requests:** In Stateless, requests are self-contained, i.e. everything contained within the request, and handled in two distinct phases, a “request” and “response.” While in Stateful, requests always dependant on the server-side state.
5. **Generated State:** While browsing the internet, the state generated and stored somewhere. Although the state generated in both types when the state stored on the server, it generates a session. This is called a Stateful application.
6. **State Stored:** When the state stored by the client, it generates some data used for further requests while technically “Stateful” as it references a state, but the state stored by the client, so call it Stateless.
7. **Cookie Stores:** On the client-side, cookie stores authentication data. On the server-side, create temporary client data or store on a database(this is the typical case). While returning to the dashboard to make another payment, it's a cookie stored in the browser that establishes the state with the server.
8. **User Base:** Stateful is past when there were Monoliths and no dynamic user base. Stateless is future, having Microservices floating around and mostly communicate through REST interfaces and scale-like anything since there is no state stored.

## Advantages and Disadvantages
### stateless advantages:
 1. Lower server overhead
 2. Easy to scale
 ### stateless disadvantages:
 1. Cannot revoke the session anytime
 2. Session data cannot be changed until its expiration time

### stateful advantages:
1.  Revoke the session anytime
1. Easy to implement and manage for one-session-server scenario
1. Session data can be changed later

### stateful disadvantages:
1. Increasing server overhead
1. Fail to scale

