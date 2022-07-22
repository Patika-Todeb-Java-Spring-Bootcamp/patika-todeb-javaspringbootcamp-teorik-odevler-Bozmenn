# HW3
## 1 – SOAP vs Restful ?
REST and SOAP are 2 different approaches to online data transmission. Specifically, both define how to build application programming interfaces (APIs), which allow data to be communicated between web applications. Representational state transfer (REST) is a set of architectural principles. Simple object access protocol (SOAP) is an official protocol maintained by the World Wide Web Consortium (W3C). The main difference is that SOAP is a protocol while REST is not. Typically, an API will adhere to either REST or SOAP, depending on the use case and preferences of the developer.
### REST: representational state transfer
REST is a set of architectural principles attuned to the needs of lightweight web services and mobile applications. Because it's a set of guidelines, it leaves the implementation of these recommendations to developers.

When a request for data is sent to a REST API, it’s usually done through hypertext transfer protocol (commonly referred to as HTTP). Once a request is received, APIs designed for REST (called RESTful APIs or RESTful web services) can return messages in a variety of formats: HTML, XML, plain text, and JSON. JSON (JavaScript object notation) is favored as a message format because it can be read by any programming language (despite the name), is human- and machine-readable, and is lightweight. In this way, RESTful APIs are more flexible and can be easier to set up.

An application is said to be RESTful if it follows 6 architectural guidelines. A RESTful application must have:

- A client-server architecture composed of clients, servers, and resources.
- Stateless client-server communication, meaning no client content is stored on the server between requests. Information about the session’s state is instead held with the client.
- Cacheable data to eliminate the need for some client-server interactions.
- A uniform interface between components so that information is transferred in a standardized form instead of specific to an application’s needs. This is described by Roy Fielding, the originator of REST, as “the central feature that distinguishes the REST architectural style from other network-based styles.”
- A layered system constraint, where client-server interactions can be mediated by hierarchical layers.
- Code on demand, allowing servers to extend the functionality of a client by transferring executable code (though also reducing visibility, making this an optional guideline).
### SOAP: simple object access protocol
SOAP is a standard protocol that was first designed so that applications built with different languages and on different platforms could communicate. Because it is a protocol, it imposes built-in rules that increase its complexity and overhead, which can lead to longer page load times. However, these standards also offer built-in compliances that can make it preferable for enterprise scenarios. The built-in compliance standards include security, atomicity, consistency, isolation, and durability (ACID), which is a set of properties for ensuring reliable database transactions.

Common web service specifications include:

- Web services security (WS-security): Standardizes how messages are secured and transferred through unique identifiers called tokens.
- WS-ReliableMessaging: Standardizes error handling between messages transferred across unreliable IT infrastructure.
- Web services addressing (WS-addressing): Packages routing information as metadata within SOAP headers, instead of maintaining such information deeper within the network.
- Web services description language (WSDL): Describes what a web service does, and where that service begins and ends.
- When a request for data is sent to a SOAP API, it can be handled through any of the application layer protocols: HTTP (for web browsers), SMTP (for email), TCP, and others. However, once a request is received, return SOAP messages must be returned as XML documents—a markup language that is both human- and machine-readable. A completed request to a SOAP API is not cacheable by a browser, so it cannot be accessed later without resending to the API.

### SOAP vs. REST
Many legacy systems may still adhere to SOAP, while REST came later and is often viewed as a faster alternative in web-based scenarios. REST is a set of guidelines that offers flexible implementation, whereas SOAP is a protocol with specific requirements like XML messaging.

REST APIs are lightweight, making them ideal for newer contexts like the Internet of Things (IoT), mobile application development, and serverless computing. SOAP web services offer built-in security and transaction compliance that align with many enterprise needs, but that also makes them heavier. Additionally, many public APIs, like the Google Maps API, follow the REST guidelines.
## 2 - Difference between acceptance test and functional test ?
The functional test confirms the software performs a function within the boundaries of how you've solved the problem. This is an integral part of developing software, comparable to the testing that is done on mass produced product before it leaves the factory. A functional test verifies that the product actually works as you (the developer) think it does.

Acceptance tests verify the product actually solves the problem it was made to solve. This can best be done by the user (customer), for instance performing his/her tasks that the software assists with. If the software passes this real world test, it's accepted to replace the previous solution. This acceptance test can sometimes only be done properly in production, especially if you have anonymous customers (e.g. a website). Thus a new feature will only be accepted after days or weeks of use.
- Functional testing 

Test the product, verifying that it has the qualities you've designed or build (functions, speed, errors, consistency, etc.)

- Acceptance testing 

Test the product in its context, this requires (simulation of) human interaction, test it has the desired effect on the original problem(s).
## 3 - What is Mocking ?
Mock is an Object that clone the behavior of a real object. It is basically used in Unit Testing by testing the isolated unit even when Backend is not available.
### Why we use MOCK object?
The unit testing purpose is to approve each unit of software designed and verify that the generated code is working perfectly, interdependent on external dependencies. Most of the cases, Code under test has some external dependencies like APIs and It would be better to create a mock object instead of generating test cases on the real object of the dependencies.
## 4 - What is a reasonable code coverage % for unit tests (and why) ?
The simplest measure of unit testing is statement coverage. Teams can calculate statement coverage by dividing the number of code lines the unit tests execute by the number of executable lines of code. Most tools can provide this percentage, but teams can also use the following function to find their statement coverage percentage.

While there is no standard for unit testing, one number often cited in the testing world is 80%. "Eighty percent is what I usually see as the gating standard for code coverage in corporate shops," said Tim Ottinger, a senior consultant at Industrial Logic. "Any higher or lower than that is unusual."

Matt Baldwin, manager for development enablement at Affirm, also suggested 80%. "The interesting thing is not the 80%, but the 20% that is not covered," Baldwin said. "To find the part of uncovered code that matters, examine the incident reports for the problematic teams. Look for mistakes in thinking that are repeated -- from analysis to code to tests -- and take corrective action."

For example, let's say there's a team with a high number of incidents that require rework, or the incidents have a high amount of customer impact. If the coverage number is below 80%, and unit tests could reasonably resolve the incidents, it may be time to get those numbers up. Likewise, if the number is below 80%, but the team doesn't have problems that lead to rework or customer outage, there may be other priorities to work on right now besides focusing on unit tests.

Another way to look at coverage is to compare new development and legacy software. If all new development meets that 80% code coverage standard and the legacy software code improves with every change, it might not be worth it to fix the problem. A mixed measure of say, 30% coverage, might fail to recognize the breakdown is closer to 10% (old) and 90% (new development).
## 5 – HTTP/POST vs HTTP/PUT ?
PUT puts a file or resource at a specific URI, and exactly at that URI. If there's already a file or resource at that URI, PUT replaces that file or resource. If there is no file or resource there, PUT creates one.

POST sends data to a specific URI and expects the resource at that URI to handle the request. The web server at this point can determine what to do with the data in the context of the specified resource.

- PUT method is called when you have to modify a single resource while POST method is called when you have to add a child resource.
- PUT method response can be cached but you cannot cache POST method responses.
- You can use UPDATE query in PUT whereas you can use create query in POST.
- In PUT method, the client decides which URI resource should have, and in POST method, the server decides which URI resource should have.
- PUT works as specific while POST work as abstract.
- If you send the same PUT request multiple times, the result will remain the same but if you send the same POST request multiple times, you will receive different results.
- PUT method is idempotent whereas POST method is not idempotent.
## 6 - What are the Safe and Unsafe methods of HTTP ?
Idempotency and safety are properties of HTTP methods. The HTTP RFC defines these properties and tells us which HTTP methods are safe and idempotent. Server application should make sure to implement the safe and idempotent semantic correctly as clients might expect it.
### Safe HTTP methods
HTTP methods are considered safe if they do not alter the server state. So safe methods can only be used for read-only operations. The HTTP RFC defines the following methods to be safe: GET, HEAD, OPTIONS and TRACE.
### Idempotent HTTP methods
Idempotency means that multiple identical requests will have the same outcome. So it does not matter if a request is sent once or multiple times. The following HTTP methods are idempotent: GET, HEAD, OPTIONS, TRACE, PUT and DELETE. All safe HTTP methods are idempotent but PUT and DELETE are idempotent but not safe.
Note that idempotency does not mean that the server has to respond in the same way on each request.

## 7 - How does HTTP Basic Authentication work ?
## 8 - Define RestTemplate in Spring ?
## 9 – What is the difference between @Controller and @RestController ?
## 10 – What is DNS Spoofing ? How to prevent ?
## 11 – What is content negotiation ?
## 12 – What is statelessness in RESTful Web Services ?
## 13 - What is CSRF attack? How to prevent ?
## 14 - What are the core components of the HTTP request and HTTP response ?

