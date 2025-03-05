# Attack Scenarios and Threats

This document provides an overview of some attack scenarios and threats that LuckyNetwork may face. It is intended to help the security team understand each threat, assess the potential impact, and implement appropriate preventive and reactive measures. For more detailed information about threats that LuckyNetwork has faced in the past, refer to the Internal Security Training document.

## 1. Attack against the Infrastructure
### 1.1. DDoS Attack

DDoS attacks are a common threat to our infrastructure. They can be launched by malicious actors to disrupt the availability of our services. The impact of a DDoS attack can be severe, leading to a loss of revenue and reputation. They only need to take some of our resources to cause a noticeable impact. Since 2019, DDoS protection has been baked into our Infrastructure Standards, so the security team only faces a low risk of DDoS attacks. But when they happen, it is usually a high-impact one since it's very rare that an attack can bypass our DDoS protection.

- **Types of DDoS Attacks**:
  - Volumetric Attacks: Attacks that aim to consume all of our infrastructure resources like bandwidth, CPU, and memory by the sheer amount of traffic they generate.
  - Protocol Attacks: Attacks that exploit vulnerabilities in network protocols to consume resources. For example, SYN Flood attacks exploit the TCP handshake process.
  - Application Layer Attacks: Attacks that target the application layer of our services like our Minecraft servers. They are harder to detect and mitigate by the Infrastructure DDoS protection. However, this kind of attack is usually caught by our Ingress Proxy.

- **Mitigation**:
  - Mitigating a DDoS attack requires a combination of network and application layer protections. The security team should work closely with the Infrastructure Operations team to mitigate the attack.
  - In the event of a very large Application Layer (L7) attack, the security team should work with the Infrastructure Operations team to provision Ingress Proxy to absorb the attack. The Ingress Proxy is designed to handle and absorb large amounts of traffic and is part of our DDoS protection strategy. It can be globally distributed within minutes.
  - Monitoring and alerting are key to detecting and mitigating DDoS attacks. The security team should work with the Infrastructure Operations team to set up monitoring and alerting for DDoS attacks.

### 1.2 SSH Brute Force Attack

SSH brute force attacks are a common threat to internet-facing servers. They are usually launched by bots that scan the internet for servers with weak SSH credentials. The impact of an SSH brute force attack can be severe, leading to unauthorized access to our servers.

- **Mitigation**:
  - The security team should work with the Infrastructure Operations team to implement the following mitigation measures:
    - Implementing rate limiting on SSH connections to prevent brute force attacks.
    - Implementing multi-factor authentication (MFA) for SSH access.
    - Implementing IP whitelisting for SSH access.
    - Implementing intrusion detection and prevention systems (IDS/IPS) to detect and block SSH brute force attacks.
  - One of the current security standards is to use SSH keys instead of passwords for SSH access. This is a more secure way to authenticate to servers.
  - If the server has a reliable Out-of-Band (OOB) management system, the Infrastructure Operations team usually puts the SSH port behind a VPN.

### 1.3. Service Discovery Attack

Service discovery are attack that aims to discover the services running on our infrastructure. While this may not seem like a serious threat, it can be used by malicious actors to identify vulnerabilities in our services and could lead to information disclosure.

- **Mitigation**:
  - For internal services, the security team should work with the relevant teams to put the services behind a VPN or implement IP whitelisting.
  - For services that are meant to be public, the security team should proxy the services through the Ingress Proxy to hide the IP address of backend services. This will reduce our attack surface and make it harder for attackers to discover other services.
  - Ensure firewall policies are always up-to-date and restrict access to services to only authorized users.

### 2. Attacks against the Applications
### 2.1. Exploits in Minecraft Plugins

Minecraft plugins are a common attack vector for malicious actors. They can exploit vulnerabilities in plugins to gain unauthorized access to our servers or disrupt the gameplay experience of our players. The impact of an exploit in a Minecraft plugin can be severe, leading to a loss of revenue and reputation.

- **Mitigation**:
  - The security team should regularly audit the plugins used on our servers for vulnerabilities.
  - The security team should work with the Plugin Development team to implement secure coding practices and review processes.
  - The security team should work with the Setup team to notify if a plugin has a known vulnerability and should be updated or removed.

- **Types of Exploits**:
  - Remote Code Execution (RCE): Attackers can exploit vulnerabilities in plugins to execute arbitrary code on our servers. 
 - Denial of Service (DoS): Attackers can exploit vulnerabilities in plugins to crash our servers or disrupt the gameplay experience of our players.
 - Information Disclosure: Attackers can exploit vulnerabilities in plugins to gain access to sensitive information like player data or server configurations.
 - Elevation of Privilege: Attackers can exploit vulnerabilities in plugins to gain unauthorized access to our servers or escalate their privileges.
 - Data Exfiltration: Attackers can exploit vulnerabilities in plugins to steal sensitive data from our servers.
 - Malware Injection: Attackers can exploit vulnerabilities in plugins to inject malware into our servers.

### 2.2. Minecraft Bot Attacks

Bot attacks are a common threat to our Minecraft servers. They are usually launched by malicious actors to disrupt the gameplay experience of our players. The impact of a bot attack can be severe, leading to loss of revenue and reputation.

- **Mitigation**:
  - The security team should implement protection suites to detect and block bots from joining our servers.
  - The security team should work with the Infrastructure Operations team to implement rate limiting on connections to prevent bot attacks.
  - The security team should work with the Plugin Development team to implement anti-bot measures in our plugins for plugins that are likely to be targeted by bot attacks.

### 2.3. SQL Injection Attacks in Web Applications

SQL injection are attacks that exploit vulnerabilities in web applications that allow attackers to craft malicious SQL queries to execute arbitrary code on our databases. The impact of an SQL injection attack can be severe, leading to unauthorized access to our databases and loss of sensitive information.

- **Mitigation**:
  - The security team should work with the Web Development team to implement secure coding practices to prevent SQL injection attacks.
  - The security team should configure a third-party of first-party Web Application Firewall (WAF) to detect and block SQL injection attacks. 
  - The security team should regularly audit our web applications for vulnerabilities and conduct penetration testing to identify and remediate SQL injection vulnerabilities.

### 2.4. Cross-Site Scripting (XSS) Attacks

Cross-site scripting (XSS) attacks are a common threat to web applications. They can be launched by malicious actors to inject malicious scripts into web pages viewed by our players. The impact of an XSS attack can be severe, leading to unauthorized access to our players' accounts or loss of sensitive information.

- **Mitigation**:
  - The security team should work with the Web Development team to implement secure coding practices to prevent XSS attacks.
  - The security team should configure a third-party or first-party Web Application Firewall (WAF) to detect and block XSS attacks.
  - The security team should regularly audit our web applications for vulnerabilities and conduct penetration testing to identify and remediate XSS vulnerabilities

### 2.5 Service DoS Attacks

A common attack vector is to flood our services with requests to disrupt the availability of our services. Taking down some of our services can have a significant impact on our players.

- **Mitigation**:
  - The security team should work with the Infrastructure Operations team to implement rate limiting on connections to prevent DoS attacks.
  - The security team should work with the Infrastructure Operations team to implement monitoring and alerting to detect and respond to DoS attacks.
  - The security team should work with the application development team to implement rate limiting on the application layer to prevent DoS attacks.


### 3. Attacks against the Humans
### 3.1. Phishing Attacks

Phishing attacks can be launched by malicious actors to trick our Staff members into revealing sensitive information like credentials or personal information. The impact of a phishing attack can be severe, leading to unauthorized access to our systems or loss of sensitive information.

- **Mitigation**:
  - The security team should regularly conduct phishing awareness training for our Staff members.
  - The security team should implement email filtering and scanning to detect and block phishing emails.
  - The security team should work with the Infrastructure Operations team to implement multi-factor authentication (MFA) for sensitive systems.

### 3.2. Social Engineering Attacks

Social engineering attacks aim to manipulate our Staff members into revealing sensitive information or performing actions that could compromise our security. The impact of a social engineering attack can be severe, leading to unauthorized access to our systems or loss of sensitive information.

- **Mitigation**:
  - The security team should regularly conduct social engineering awareness training for our Staff members.
  - The security team should implement policies and procedures to verify the identity of individuals requesting sensitive information or access to our systems.
  - The security team should work with the Infrastructure Operations team to implement multi-factor authentication (MFA) for sensitive systems.

### 3.3. Insider Threats

Insider threats can pose a significant risk to our security. They can be launched by Staff members who have access to our systems and data. The impact of an insider threat can be severe, leading to unauthorized access to our systems or loss of sensitive information.

- **Mitigation**:
  - The security team should implement least privilege access controls to limit the access of Staff members to sensitive systems and data.
  - The security team should implement monitoring and alerting to detect and respond to suspicious activities by Staff members.
  - The security team should regularly conduct security awareness training for our Staff members to educate them about the risks of insider threats.

## 4. Advanced Persistent Threats (APTs)

Advanced Persistent Threats (APTs) are sophisticated attacks that are launched by well-funded and organized groups. They can be difficult to detect and mitigate, and they can have a significant impact on our security. The security team should be aware of the following APT scenarios:

- **Scenario 1: Data Exfiltration**:
  - APTs can exfiltrate sensitive data from our systems and use it for malicious purposes. The impact of data exfiltration can be severe, leading to loss of sensitive information and reputation.
  - Mitigation: The security team should implement data loss prevention (DLP) measures to detect and block data exfiltration attempts. The security team should work with the Infrastructure Operations team to implement encryption and access controls to protect sensitive data.

- **Scenario 2: Credential Theft**:
  - APTs can steal credentials from our systems and use them to gain unauthorized access to our systems. The impact of credential theft can be severe, leading to unauthorized access to our systems and data.
  - Mitigation: The security team should implement multi-factor authentication (MFA) to protect against credential theft. The security team should regularly audit and rotate credentials to prevent unauthorized access. The security team should enforce strong password policies and VPN requirements for internal systems.

- **Scenario 3: Staff Device Compromise**:
  - APTs can compromise the devices of our Staff members and use them to gain unauthorized access to our systems. The impact of device compromise can be severe, leading to unauthorized access to our systems and data.
  - Mitigation: The security team should develop and enforce least privilege access controls to limit the access of Staff members to sensitive systems and data and make use of our zero-trust model. The security team should also train Staff members on how to secure their devices and detect signs of compromise.


## 4. SIEM & SOAR

Monitoring is a critical component of our security strategy. It allows us to detect and respond to security incidents promptly. The security team should work closely with the Infrastructure Operations team to implement monitoring and alerting for the following scenarios:

The security team should use SIEM tools, NeoLogger, IDS/IPS, and other monitoring and attack detection tools to detect and respond to security incidents. The security team should also use SOAR tools to automate incident response and remediation.

## 5. Conclusion

This document has provided an overview of the various attack scenarios and threats that LuckyNetwork may face. The security team needs to understand each threat, assess the potential impact, and implement appropriate preventive and reactive measures. By working closely with the relevant teams and implementing best practices, the security team can effectively protect our infrastructure and data from malicious actors. For more detailed information about threats that LuckyNetwork has faced, refer to the Security Training document.