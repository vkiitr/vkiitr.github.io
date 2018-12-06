---
layout: post
title:  "Java Cheat Sheet!"
date:   2018-11-25 13:46:52
comments: true
image: /images/java.jpg
categories: 
---


Hashmap => Hashtable or ConcurrentHashMap.

----

Immutable objects are those, whose state can not be changed once created e.g. java.lang.String, once created can not be modified e.g. trim, uppercase, lowercase. All modification in String result in new object.

----

Collections such as `HashMap` and `HashSet` use a hashcode value of an object to determine how it should be stored inside a collection, and the hashcode is used again in order to locate the object in its collection. 
Hashing retrieval is a two-step process:
+ Find the right bucket (using `hashCode()`)
+ Search the bucket for the right element (using `equals()` )

----

Basically REST is stateless means every HTTP request happens in complete isolation. When the client makes an HTTP request, it includes all information necessary for the server to fulfill that request. The server never relies on information from previous requests. If that information was important, the client would have sent it again in this request. 
Statelessness is easier to distribute across load-balanced servers. Since no two requests depend on each other, they can be handled by two different servers that never coordinate.

A practical example.

Suppose we have a cluster of 12 identical J2EE webapp servers. Each one has the same application installed on it. We expect thousands of hits per hour. 
If the webapp was stateful, once a client had logged into one of those servers, the session state (HttpSession) would (usually) reside in RAM within that server. If a later request came in and that server was loaded down but other servers were idle, they could not be employed to handle the request. Or at a minimum, could not be employed unless the cluster was set up to serialize sessions and ship them between servers, which is extra overhead. There would be an asymmetry between the server currently holding the user's state and the other webapp servers.

A stateless webapp, on the other hand, wouldn't establish an HttpSession. Any ongoing state would be an artefact of (presumably distributed) backend processes. So you could send out requests to any server in the cluster that happened to be free at the moment. They would all be symmetrical in their response.

-----

Bean
@Autowired
IOC - it is not going to instantiate the object utill it required 

@cbcertservice interface what kind of service would be injected in this is decided run time ..and that implementation would be annoted as @Service



