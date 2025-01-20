# ADR 001: Event-Driven Architecture Using Apache Kafka

## Status
Accepted

## Context
Our electronics recycling system needs to handle complex business processes with multiple steps, integrate with various external systems, and scale to support thousands to millions of users. The system needs to be resilient, maintainable, and able to evolve over time.

## Decision
We will implement an event-driven architecture using Apache Kafka as our central event bus, with the following key components:

1. **Event Bus (Apache Kafka)**
   - Central message broker for all system events
   - Event persistence for replay and audit
   - Topic-based message routing
   - Event sourcing capabilities

2. **Core Processors**
   - Device Catalog Management
   - Assessment Processing
   - Offer Management

3. **Integration Processors with Circuit Breakers**
   - Shipping Integration (PPL, Zásilkovna)
   - Sales Integration (eBay, Aukro)
   - Payment Integration (Stripe)

4. **Support Processors**
   - Analytics
   - Customer Support

5. **Frontend Applications**
   - Web Application
   - Kiosk Application
   - Admin Application

## Consequences

### Positive
- Loose coupling between components
- Easy to add new subscribers without affecting existing ones
- Built-in event history and audit trail
- Better scalability and resilience
- Asynchronous processing capabilities
- Clear separation of concerns

### Negative
- Increased complexity in event management
- Need for event versioning
- Eventually consistent data
- Learning curve for development team

## Technical Details
- Event metadata structure:
  ```json
  {
    "eventId": "UUID",
    "timestamp": "ISO-8601",
    "version": "1.0",
    "correlationId": "UUID",
    "causationId": "UUID",
    "type": "EventType",
    "data": {}
  }
  ```

- Key event flows:
  1. Device Assessment Flow
  2. Offer Creation Flow
  3. Payment Flow
  4. Shipping Flow
  5. Sales Flow

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