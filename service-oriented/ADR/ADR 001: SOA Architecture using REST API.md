ADR 001: SOA Architecture using REST API
Status
Accepted
Context
Our electronics recycling system needs to handle complex business processes with multiple steps, integrate with various external systems, and scale to support thousands to millions of users. The system needs to be resilient, maintainable, and able to evolve over time.
Decision
We will implement an SOA architecture using REST API, with the following key components:
1.	Enterprise Service Bus
o	Central message broker 
o	Messages persistence for replay and audit
o	Topic-based message routing
2.	Core Services
o	Device Catalog Management
o	Assessment Processing
o	Offer Management
3.	Integration Services 
o	Shipping Integration (PPL, Zásilkovna)
o	Sales Integration (eBay, Aukro)
o	Payment Integration (Stripe)
4.	Support Services
o	Analytics
o	Customer Support
5.	Frontends
o	Web Application
o	Kiosk Application
o	Admin Application
Consequences
Advantages
o	Organized Code
o	Reusability
o	Scalability
o	Flexibility
o	Interoperability
Disadvantages
o	Increased Complexity
o	Performance Overhead
o	Testing Challenges
o	Security Risks

Mitigation Strategies
o	Simplify Service Management
o	Improve Performance
o	Enhance Testing Processes
o	Strengthen Security

Infrastructure
•	NGINX Load Balancer
•	Redis for caching
•	PostgreSQL for persistent storage
•	Elastic search for search capabilities
Review Trigger
This decision should be reviewed if:
•	System scale exceeds Kafka's capabilities
•	New requirements demand synchronous processing
•	Event complexity becomes unmanageable
•	Performance metrics indicate issues

