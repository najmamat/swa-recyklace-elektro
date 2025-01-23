# Electronics Recycling System

## Architectures Evaluation
After evaluating both architectures, the decision was made to implement the event-based architecture. The primary reason for this is the ability to process a large volume of asynchronous requests

#### Scalability and asynchronous processing
Both event-based architecture and SOA offer good scalability. However, event-based architecture has the advantage of asynchronous request processing. This eliminates the need for immediate responses, reducing bottlenecks and making it more suitable for handling traffic spikes or processes that do not require instant user feedback.
#### Real-time processing
Event-based architecture is particularly well-suited for handling a large number of real-time requests. It also effectively manages sudden surges in demand.
#### Data consistency
With an event-based approach, special attention must be given to maintaining data consistency, as well as the increased demands on the messaging system.
#### Complexity
Implementing an event-based architecture introduces greater complexity in terms of orchestration, monitoring, and logging. In the short term, SOA may seem like a simpler option, but its limitations could become evident as the application scales over time.


# Course Assignment
This repository contains the solution for the course assignment from `4IT575 Software Architectures`.

## Team Members
- [Najman Matouš](https://github.com/najmamat) [najmamat] - najm06
- [Veis Michael](https://github.com/misak94) [misak94] - veim01
- [Fiedler Josef](https://github.com/fiedler256) [fiedler256] - fiej00
- [Beran Štěpán](https://github.com/sberan1) [sberan1] - bers06

## Assignment
A large electronics retailer wants to start a business in electronics recycling and needs a new system. Customers can send their small personal electronic devices or use local kiosks in shopping centers and potentially receive money for their used device if it is in working condition.

### Users
Hundreds, potentially thousands to millions...

### Requirements
- Customers can receive offers for used personal electronic equipment (phones, cameras, etc.) either through the website or a kiosk in a shopping center.
- Customers receive a box by mail, send their electronic device, and if it's in good condition, they get paid.
- Upon receiving the device, it is assessed/checked whether it can be recycled/safely disposed of or sold (eBay, etc.).
- The company expects to add 5-10 new types of electronics each month that they will accept.

### Additional Context
- This is a highly competitive activity and a new business area for us.
- If we haven't received a certain type of electronic device even once in the past year, we remove it from our system.
- We need to maintain a list of electronic devices we are willing to accept, as it changes frequently.
- Each device has its own assessment/checking rules.
- We have the right to change the original price offer to the customer if the product is not in the condition declared by the customer.

# User Roles and Use Cases

![Use Case Diagram](diagrams/use-case/uc-diagram-eng.png)
*Informal UC diagram primarily serving for understanding the assignment*

#### Unregistered Customer
- Can browse the catalog of accepted devices
- Can get a preliminary price offer for their device
- Can register
- Can use a kiosk in a shopping center to get an offer

#### Registered Customer
- Can manage their personal information
- Can request shipping box delivery
- Can track their shipment status through integration with Zásilkovna and PPL
- Can accept or reject adjusted price offers
- Can manage their payment details
- Can rate the service and recycling process
- Can communicate with customer support

#### System Administrator
- Can manage the catalog of accepted devices
- Can add/modify device assessment rules
- Can manage user accounts and roles
- Can generate reports and statistics
- Can set pricing policies
- Can manage integrations with carriers

#### Device Inspector
- Can assess received devices according to established rules
- Can adjust price offers based on actual device condition
- Can mark devices as suitable for recycling/sale
- Can initiate customer payment process
- Can document received device condition (photos, notes)

#### Sales Manager
- Can manage listings on sales platforms (eBay, Aukro)
- Can set device selling prices
- Can track sales success across platforms
- Can manage communication with buyers on sales platforms
- Can generate sales reports

#### Customer Support
- Can respond to customer inquiries
- Can handle complaints and claims
- Can modify basic customer information
- Can track shipment status and inform customers

## Architecture Evaluation

After thorough analysis of both Event-Driven and Service-Oriented architectures against the system requirements, we recommend implementing the **Event-Driven Architecture**. Here's our detailed justification:

### Key Decision Factors

1. **Scalability & Performance**
   - Event-Driven Architecture better handles the requirement for "thousands to millions" of users through asynchronous processing and event streaming
   - Kafka's partitioning enables horizontal scaling of event processing
   - Better handling of traffic spikes in kiosks and web applications

2. **Business Requirements Alignment**
   - Natural fit for the dynamic nature of device catalog management (5-10 new devices monthly)
   - Supports complex workflows: device assessment → price adjustment → customer notification → payment processing
   - Enables real-time tracking of shipments and instant price updates
   - Facilitates automated cleanup of unused device types (yearly requirement)

3. **Integration Capabilities**
   - Superior handling of external system integrations (Zásilkovna, PPL, eBay, Aukro)
   - Built-in resilience through event replay and Circuit Breaker pattern
   - Easier integration of future sales channels or shipping providers

4. **Data Consistency & Management**
   - Event sourcing provides complete audit trail of all transactions
   - Better handling of distributed data and eventual consistency
   - Enables replay of events for data recovery or analysis

### Trade-offs Considered

1. **Complexity vs Flexibility**
   - While Event-Driven Architecture introduces higher initial complexity, it provides better long-term flexibility
   - The complexity is justified by the system's scale and integration requirements

2. **Cost vs Scalability**
   - Higher infrastructure costs (Kafka cluster) are offset by better scaling capabilities
   - Reduced development costs for future integrations and features

3. **Learning Curve vs Long-term Benefits**
   - Initial team learning curve is outweighed by maintainability and extensibility benefits
   - Better support for future business requirements and system evolution

### Conclusion
The Event-Driven Architecture provides the best foundation for building a scalable, resilient, and maintainable electronics recycling system that can grow with the business needs while maintaining high performance and reliability.


## TODO
- [x] Assignment, application description, requirements, additional context
- [x] UseCase diagram
- [x] User roles
- [x] UseCase diagram to english

### Event-oriented Architecture
- [x] Architecture design
- [x] Architecture documentation (Component diagram, Deployment diagram)
- [x] Review of ADRs - should probably include some rejected, 002 might be a great example
- [x] ADR (at least 3)
- [x] Advantages and disadvantages

### Service-oriented Architecture (SOA)
- [x] Architecture design
- [x] Architecture documentation (Component diagram, Deployment diagram)
- [x] ADR (at least 3)
- [x] Advantages and disadvantages

### Evaluation
- [x] Architecture comparison
- [x] Selection of more suitable architecture
- [x] Justification of selection
- [ ] Polish
