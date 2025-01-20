# ADR 001: Event-Driven Architecture Using Apache Kafka

## Status
Accepted

## Context
Our electronics recycling system needs to handle complex business processes with multiple steps, integrate with various external systems, and scale to support thousands to millions of users. The system needs to be resilient, maintainable, and able to evolve over time.

## Decision
We will implement an SOA architecture using REST API, with the following key components:

1. **1.	Enterprise Service Bus**
   - Central message broker 
   - Messages persistence for replay and audit
   - Topic-based message routing

2. **Core Services**
   - Device Catalog Management
   - Assessment Processing
   - Offer Management

3. **Integration Services**
   - Shipping Integration (PPL, Zásilkovna)
   - Sales Integration (eBay, Aukro)
   - Payment Integration (Stripe)

4. **Support Services**
   - Analytics
   - Customer Support

5. **Frontend Services**
   - Web Application
   - Kiosk Application
   - Admin Application

## Consequences

### Positive
- Organized Code
- Easy to add new services without affecting existing ones
- Better scalability and resilience
- Asynchronous processing capabilities
- Clear separation of concerns

### Negative
- Increased complexity 
- Performanc overhead
- Testing Challenges
- Security risks

## Mitigation Strategies
- Simplify Service Management 
- Improve Performance
- Enhance Testing Processes
- Strengthen Security

## Infrastructure
- NGINX Load Balancer
- Redis for caching
- PostgreSQL for persistent storage
- Elasticsearch for search capabilities

## Review Trigger
This decision should be reviewed if:
- System scale exceeds Kafka's capabilities
- New requirements demand synchronous processing
- Event complexity becomes unmanageable
- Performance metrics indicate issues 
