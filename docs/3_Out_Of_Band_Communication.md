# Out-of-band Communication

During a security incident, it is essential to establish secure and reliable communication channels to coordinate the incident response effort. This document outlines the current out-of-band communication methods, and the standard if we want to introduce new out-of-band communication methods.

## 1. Introduction

Out-of-band communication is a communication channel that is separate from the primary channels used for operations. During a catastrophic event, the primary communication channels may be compromised or unavailable. In-band communication channels are those that are used for day-to-day operations, such as email, In-game chat, and Discord.

## 1.1 Current In-band Communication Methods

The following in-band communication methods are used by LuckyNetwork for day-to-day operations:

### 1.1.1 Email

LuckyNetwork Email system is used for official asynchronous communication. It is also used to send reports, notifications, and other important information. While our email system has its own infrastructure, it is not considered secure for sensitive information, as it is not end-to-end encrypted. During a security incident, email should not be used for communication. During a security incident, email could be compromised, and an attacker could intercept the communication by using stolen credentials.

### 1.1.2 In-game Chat

In-game chat using /staffchat is used for real-time communication between staff members. It is more secure due to the server not storing the chat logs. However, it is not encrypted, and the server could be compromised during a security incident. During a security incident, In-game chat might be down if the infrastructure is compromised, or an attacker might be monitoring the chat with stolen Staff accounts.

### 1.1.3 Discord

Discord is the primary communication channel for LuckyNetwork staff members. It is used for real-time communication, announcements, and general discussions. During a security incident, our Discord server could be compromised, and an attacker could monitor the communication by using stolen credentials.

## 2. Out-of-band Communication Methods

LuckyNetwork has established the following out-of-band communication methods for security incidents:

### 2.1 WhatsApp

Each Staff member of LuckyNetwork is required to have a WhatsApp account for out-of-band communication. WhatsApp is used for urgent communication during security incidents, as it provides end-to-end encryption and is widely available on mobile devices. WhatsApp is significantly harder to compromise compared to email, In-game chat, and Discord. 

### 2.2 Drive Talk

LuckyNetwork Drive system has a built-in chat system called Drive Talk. Drive Talk is a secure chat system self-hosted by LuckyNetwork. Access to Drive Talk requires an account, mandatory 2FA, and is only accessible from the LuckyNetwork network where explicit approval for each device is required. Drive Talk is used for secure communication during security incidents, as it provides end-to-end encryption and is only accessible from the LuckyNetwork network. The Drive is end-to-end encrypted, but may not be available if the infrastructure is compromised.

### 2.3 Connectivity & Service Reliability Team's Communication Channel

The Connectivity & Service Reliability Team has maintained a separate communication channel for out-of-band communication. This communication channel is primarily used to ensure reliable communication between all staff members and executives during an outage that takes down the primary communication channels.

## 3. Standard for Introducing New Out-of-band Communication Methods

When introducing new out-of-band communication methods, it is important to consider the following standards to ensure that the communication channel is secure and reliable. The new out-of-band communication method must meet the following criteria:

### 3.1 Security

The new out-of-band communication method must provide several layers of security:

- **End-to-end encryption**: The communication must be encrypted from end-to-end to prevent eavesdropping.
- **Authentication**: The communication must require strong authentication to ensure that only authorized users can access it.
- **Access Control**: The communication must have access controls to restrict access to authorized users only.
- **MFA (Multi-Factor Authentication)**: The communication channel can enforce MFA to ensure that only authorized users can access it.
- **Logging and Auditing**: The communication must log all communication activities for auditing purposes.

### 3.2 Reliability

The new out-of-band communication method must be reliable and available during a security incident. It should not rely on the same infrastructure as the primary communication channels to ensure that it is not affected by the incident.

- **High Availability**: The communication channel must have high availability to ensure that it is accessible when needed. High availability can be achieved through redundancy and failover mechanisms. Mechanisms such as clustering, or load balancing can be used to ensure high availability.

- **Redundancy**: The communication channel must have redundancy to ensure that it is not a single point of failure. Redundancy can be achieved through multiple servers, data centers, or cloud providers.

- **Host Resilience**: The communication channel must be hosted in a resilient environment to ensure that it is not affected by our primary infrastructure's failure. The communication channel can be hosted in a separate data center or cloud provider to ensure host resilience.

### 3.3 Interoperability

The new out-of-band communication method must have strong interoperability. 

- **Cross-Platform Compatibility**: The communication channel must be compatible with multiple platforms, such as mobile devices, desktops, and web browsers. LuckyNetwork staff members use a variety of devices, and the communication channels must be accessible from all of them.

### 3.4 Performance

The new out-of-band communication method must have strong performance.

- **Low Latency**: The communication channel must have low latency to ensure that messages are delivered in real time. Low latency is essential for real-time communication during a security incident.

- **Scalability**: The communication channel must be scalable to handle a large number of users and messages. Scalability is essential to ensure that the communication channel can handle the load during a security incident.

## 4. Conclusion

Out-of-band communication is essential for coordinating the incident response effort during a security incident. LuckyNetwork has established several out-of-band communication methods to ensure secure and reliable communication during a security incident. When introducing new out-of-band communication methods, it is important to follow the standards outlined in this document to ensure that the communication channel is secure, reliable, and interoperable. Having a robust out-of-band communication system in place will prevent an attacker from disrupting the incident response effort and help the security team respond effectively to security incidents.