# ADR 2: Centralized Logging and Monitoring

## Status
Approved

## Context
As the system grows, it is crucial to have a reliable way to monitor and log errors across various services. Given the large number of users and interactions, quick identification of issues is necessary to ensure smooth operation and minimize downtime. Currently, there is no centralized logging or error-handling solution in place.

## Decision
We will implement **AWS CloudWatch** for centralized logging and monitoring, and **AWS SNS** to notify the team when issues or errors occur.

1. **CloudWatch Logs**
   - Centralizes logs from all services, allowing for easier access and analysis.
   - Provides real-time monitoring for performance insights and troubleshooting.

2. **CloudWatch Alarms**
   - Automatically triggers notifications based on error conditions or performance metrics.

3. **AWS SNS (Simple Notification Service)**
   - Sends alerts to the team (via email, SMS, etc.) when critical issues are detected by CloudWatch alarms.

## Consequences

### Easier
- **Centralized Monitoring**: Logs from different services are accessible in one place, streamlining the process of identifying and resolving issues.
- **Real-Time Alerts**: Teams are immediately notified of critical events, enabling faster response times and minimizing system downtime.
- **Scalable Solution**: As the system grows, CloudWatch can easily handle increased log volumes.

### More Difficult
- **Cost**: The use of CloudWatch for storing and processing large amounts of log data can result in increased costs over time.
- **Vendor Lock-In**: Relying on AWS for logging and notifications introduces a dependency on a single cloud provider.
