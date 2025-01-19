# Event-Based Architecture - Component Diagram

## Overview
The system is designed as an event-driven architecture using an event bus for communication between services. This solution enables independent scaling of individual components and ensures high service availability.

## Main Components

### Frontend Services
1. **Web Application (FE)**
   - Web interface for customers
   - Enables price offers, shipment tracking, and account management
   - Implements local caching for optimal performance
   - Communicates via Event Bus using events

2. **Kiosk Application (FE)**
   - Application for shopping center kiosks
   - Offline-first approach for stable operation
   - Local cache for device catalog
   - Synchronization via Event Bus

### Core Services
1. **Device Catalog Service**
   - Management of accepted devices
   - Automatic removal of inactive items (12 months without receipt)
   - Management of device assessment rules
   - Uses MongoDB for flexible device schema

2. **Assessment Service**
   - Processing of received device assessments
   - Implementation of specific rules for each device type
   - Ability to adjust price offers based on actual condition
   - Results storage in MongoDB

3. **Payment Service**
   - Automatic customer payment processing
   - Integration with payment systems
   - Transactional processing in PostgreSQL
   - Payment initiation after technician approval

4. **Offer Management Service**
   - Generation of price offers
   - Management of pricing policies
   - Cache utilization for frequently requested offers
   - Integration with Device Catalog Service

### Integration Services
1. **Shipping Integration Service**
   - Integration with Zásilkovna and PPL
   - Real-time shipment tracking
   - Management of empty box shipping
   - Receipt of devices for recycling

2. **Sales Integration Service**
   - Integration with eBay and Aukro
   - Automatic product listing
   - Sales management and buyer communication
   - Status synchronization across platforms

### Support Services
1. **Analytics Service**
   - System usage monitoring
   - Report generation
   - Recycling/sales success analysis
   - Elasticsearch utilization for analytical queries

2. **Customer Support Service**
   - Customer request management
   - Communication history
   - Access to shipment and offer data
   - Integration with communication channels

## Infrastructure Components

### Event Bus (Apache Kafka)
- Central communication hub
- Guaranteed message delivery
- Event persistence in Cassandra
- Scalable event processing

### Databases
1. **Device Catalog DB (MongoDB)**
   - Flexible schema for various device types
   - Fast catalog querying
   - Scalable solution

2. **Assessment DB (MongoDB)**
   - Assessment results storage
   - Offer change history
   - Flexible data structure

3. **Customer DB (PostgreSQL)**
   - Transactional data
   - User accounts
   - Financial operations
   - Replication for high availability

### Cache (Redis)
- Local caching strategy (without CDN)
- Caching of frequent queries
- Session management
- Performance optimization

### Load Balancer
- Load distribution
- Health checking
- Request routing
- Service scaling

## Communication Patterns
- Event-driven communication via Kafka
- REST API for synchronous operations
- WebSockets for real-time updates
- Optimized queries through cache 