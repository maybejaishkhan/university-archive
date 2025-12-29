Systems and Network Administration - Mids Notes
# Introduction
> **System Administration** -> The management and maintenance of computer systems.
> **Network Administration** -> The management and upkeep of computer networks.

*   Installing, configuring, and maintaining servers and networks.
*   Ensuring system security and data integrity.
*   Monitoring and optimizing performance.
*   Troubleshooting issues and implementing solutions.

## Roles and Responsibilities
*   **System Administrator:**
    *   User account management
    *   System updates and patches
    *   Backup and disaster recovery planning
*   **Network Administrator:**
    *   Network configuration -> IP addressing, routing
    *   Managing network services -> DNS, DHCP
    *   Monitoring and optimizing network performance and security
*   **Shared Responsibilities:**
    *   Security management -> Firewalls, VPNs
    *   Documentation and policy implementation
    *   Ensuring system and network availability

**Components of a Computer System:**
*   *Hardware* -> Physical components (CPU, memory, storage)
*   *Software* -> Operating systems, applications, drivers
*   *Firmware* -> Embedded software controlling hardware
*   *Networking* Components -> Network Interface Cards (NICs), routers, switches

<div style="page-break-after:always;"></div>

## Networking
A collection of computers and devices connected to share resources and information.

**Network Types:**
* *LAN* (Local Area Network): Small geographical area
* *WAN* (Wide Area Network): Larger geographical area
* *MAN* (Metropolitan Area Network): Covers a city or campus

**Network Topologies:**
* *Bus*
* *Star*
* *Ring*
* *Mesh*
### Networking Protocols
1. **TCP** (Transmission Control Protocol)
2. **UDP** (User Datagram Protocol)
3. **IP** (Internet Protocol)
4. **DNS** (Domain Name System) -> Resolves human-readable domain names to IP addresses.
5. **DHCP** (Dynamic Host Configuration Protocol) -> Automatically assigns IP addresses to devices on a network.

<div style="page-break-after:always;"></div>

## Policies
Policies are rules or guidelines to allow/deny access. Policies can be implemented on a Systems Level or on a Network Level (both kinds of policies having separate catalogues).
- *Inbound Policies* -> Controls traffic coming into the network.
- *Outbound Policies* -> Controls traffic leaving the network.
## Documentation
It is the act of writing down information in a formal format. Documentation is essential for maintaining continuity, aiding in troubleshooting, and providing records for compliance and auditing. It should include information on network layouts and configurations, system settings, user accounts, security policies, and backup schedules.
## Planning
Planning is the foundation for successful system and network administration. It involves several steps:
1. *Assessment*: It's important to understand the current state of your systems and networks before making any changes.
2. *Goal Setting*: Define clear objectives for what you want to achieve, such as improved security, enhanced performance, or increased scalability.
3. *Budgeting*: Allocate resources effectively to support the plan.
4. *Timeline*: Create a realistic schedule with milestones and deadlines.

But it has issues like how do we balance security with usability? or how do we provide high availability with disaster recovery? and how do we keep up with technology updates.

---

# Operating System
> A program that controls the execution of application programs. It is an interface between applications and hardware and makes a computer more convenient, more efficient and able to evolve.

An OS provides many many services like
*   Program development (Editors and debuggers) and Program execution.
*   Access to I/O devices, System and Files.
*   Error detection and response for internal and external hardware and software errors.

**Accounting** -> Collect usage statistics, monitor performance, used to anticipate future enhancements and for billing purposes.

A computer system has
- **4** Layers -> Applications, Utilities, Operating System, Hardware.
- **5** Resources -> Processor, Memory, Storage Disk, Network, I/O Devices.
## Kernel
It is the portion of the operating system that is in the main memory and contains the most frequently used functions. It is the first program that is loaded in the memory, in **kernel mode**. It has 4 main functions of "managing" *processes*, *memory*, *devices* and *files*.

> OS Kernel also enforces security policies and protects the system from unauthorized access.
## Processes
It is an instance of a program running on a computer. It is the the entity that can be assigned to and executed on a "processor". Also called, a unit of activity characterized by a single sequential thread of execution, a current state, and an associated set of system resources.

**Components of a Process** -> An executable program, Data needed by the program and Execution context of the program.
### Design Considerations
* **Improper synchronization:** Ensure a process waiting for an I/O device receives the signal
* **Nondeterminate program operation:** Program should only depend on input to it, not on the activities of other programs
* **Deadlocks**

## Memory Management

*   **Features:**
    *   Process isolation
    *   Automatic allocation and management
    *   Support of modular programming
    *   Protection and access control
    *   Long-term storage
*   **Issues:**
    *   Not enough Memory
    *   Memory Fragmentation
    *   Security Crash

### Virtual Memory
Allows programmers to address memory from a logical point of view.
*   **Benefits:** Eliminates the hiatus between the execution of successive processes while one process was written out to secondary store and the successor process was read in
*   **Relationship to File System:**
    *   Implements long-term store
    *   Information stored in named objects called files

**Paging** -> Paging is a memory management technique used by OS to store and retrieve data between main memory (RAM) and secondary storage (disk). Memory is divided into fixed-size blocks called pages and those pages are mapped to parts of the physical memory, creating an illusion of more memory than there is.

A **MMU** (Memory Management Unit) handles the translation of virtual addresses (used by applications) into physical addresses (used by the hardware to access actual memory).

More Complex Fragmentation => More Complex Mapping
## Information Protection and Security

*   **Availability:** Concerned with protecting the system against interruption
*   **Confidentiality:** Assuring that users cannot read data for which access is unauthorized
*   **Data integrity:** Protection of data from unauthorized modification
*   **Authenticity:** Concerned with the proper verification of the identity of users and the validity of messages or data

### Scheduling and Resource Management Goals
*   **Fairness:** Give equal and fair access to resources
*   **Differential responsiveness:** Discriminate among different classes of jobs
*   **Efficiency:** Maximize throughput, minimize response time, and accommodate as many uses as possible

## System Structure
*   View the system as a series of levels
*   Each level performs a related subset of functions
*   Each level relies on the next lower level to perform more primitive functions
*   This decomposes a problem into several more manageable

Process Hardware Levels
*   **Level 1** -> *Electronic Circuits*
*   **Level 2** -> *Processor's Instruction Set*
*   **Level 3** -> *Procedure*s
*   **Level 4** -> *Interrupts*

Concepts with Multiprogramming
*   **Level 5** -> *Processes*
*   **Level 6** -> *Secondary Storage Devices*
*   **Level 7** -> *Logical Address Space*

Deal with External Objects
*   **Level 8** -> *Interprocess Communication*
*   **Level 9** -> *File System*
*   **Level 10** -> *External Device Interfaces*
*   **Level 11** -> *External-Internal Identifier Mapping*
*   **Level 12** -> *Process Support Facilities*
*   **Level 13** -> *User Interface*: For the operating system.

**UNIX** is a powerful, multiuser, multitasking operating system. It uses a Layered Architecture where the layers are "Hardware", "Kernel", "System Call Interface", "Commands and Libraries". Each layer surrounds the one before it.

It comes with a number of user services and interfaces: Shell, Components of the C compiler etc.
### Multithreading
Process is divided into threads that can run concurrently.
*   **Thread:** Dispatchable unit of work - executes sequentially and is interruptable

**Symmetric Multiprocessing (SMP):** There are multiple processors which share the same main memory and I/O facilities, and can perform the same functions.

### Kernel-Mode Components
1. **Executive** -> Contains base operating system services: Memory management, Process and Thread management, Security, I/O and Interprocess communication.
2. **Kernel** -> Consists of the most used
3. **HAL** (Hardware abstraction layer) -> Isolates the operating system from platform-specific hardware differences.
4. **Device drivers** -> Translate user I/O function calls into specific hardware device I/O requests
5. **Windowing and graphics systems** -> Implements the graphical user

### User-Mode Processes
*   Special system support processes - Ex: logon process and the session manager
*   Service processes
*   Environment subsystems
*   User applications

**Client/Server Model** -> Provides a uniform means for applications to communicate via LPC (Local Procedure Calls).

## File Systems
A file system is a method to manage and organize data in the form of files and directories (folders). These are the most common ones:
* Windows - **NTFS** (New Technology File System) -> *Default file system on Windows*. It supports large files and partitions, file compression, encryption, disk quotas, and advanced permissions.
* Windows - **FAT32** (File Allocation Table 32) -> It is widely compatible across many devices and operating systems, making it a common choice for external drives and USB sticks. However, it has significant limitations, such as a maximum file size of *4GB* and a partition limit of *8TB*, making it unsuitable for modern large storage needs.
* Linux - **ext4** (Fourth Extended File System) -> *Default file system for many Linux*. It is an improvement over its predecessor, ext3, offering better performance, larger volume support, and enhanced journaling features.
* macOS - **APFS** (Apple File System) -> *Default file system for macOS, iOS, and other Apple devices*. APFS is optimized for flash and SSD storage, offering fast file access, cloning, snapshots, and strong encryption.

**Partitioning** -> Process of dividing a physical storage device, such as a hard drive or SSD, into separate sections called *partitions*.
- *Primary Partition* -> A bootable partition where an operating system can be installed. Limit=4.
- *Extended Partition* -> Since, only 4 primary are allowed on a drive, an extended partition acts as a container to hold additional partitions. Limit=1.
- *Logical Partition* -> Resides inside the extended partition and can be used to store data, files, or additional operating systems. No Limit.

🛠️Tools -> Disk Management (Windows), GParted (Linux), Disk Utility (macOS)

> [!Question] What is Distributed Computing?
> It refers to a model where tasks are divided across multiple computers that work together to solve a problem or complete a process. These computers are connected over a network and they divide the workload and processing tasks in parallel, resulting in faster execution and scalability.

> [!Question] Why is FAT32 still used?
> Because of its wide compatibility and simplicity.

> [!Question] Why is UNIX so powerful?
> Because of its simple, modular, flexible, and robust design.


---

# System Maintenance
System maintenance involves a set of activities aimed at ensuring the smooth and efficient operation of computer systems, networks, and applications. These activities are carried out to prevent system failures, enhance performance, and prolong the lifespan of hardware and software.

It is important because of *Performance Optimization*, *Security*, *Cost-Effectiveness* and *Compliance*.

**Key Tools and Techniques in System Maintenance:**
*   *Monitoring Tools*: Used to continuously monitor system performance and detect anomalies. Examples: Nagios, Zabbix, or SolarWinds.
*   *Backup and Recovery*: Regular backups and disaster recovery plans ensure that data can be restored in case of system failure or data loss.
*   *Documentation*: Keeping accurate records of maintenance schedules, system configurations, and any changes made to the system helps in troubleshooting and future upgrades.
## Types of System Maintenance

1.   **Preventive Maintenance** -> Prevent problems before they occur.
2.   **Corrective Maintenance** -> Fix issues when they arise.
3.   **Adaptive Maintenance** -> Modify systems to cope with changing environments or requirements.
4.   **Perfective Maintenance** -> Improve performance or functionality.
5.   **Emergency Maintenance** -> Address unforeseen critical issues.
## Routine System Maintenance Tasks
### 1. Updates and Patch Management

1. **Updates** -> Larger software packages that introduce new features, enhancements, or significant changes to existing functionality.
2. **Patches** -> Smaller software packages designed to address specific vulnerabilities, bugs, or security flaws in existing software.

🛠️Tools -> Windows Update (Windows), Synaptic/apt-get (Linux), Software Update (macOS)
### 2. Disk Cleanup and Defragmentation

1. **Disk Cleanup** -> Removing unnecessary files to free up space.
2. **Defragmentation** -> Re-organizing data to improve read/write speeds.

🛠️Tools -> Disk Cleanup (Windows), fsck and defrag utilities (Linux), Disk Utility (macOS)
### 3. Backup and Restore Verification
Protects against data loss and Enables disaster recovery.
* *Types of backups:* Full, incremental, differential
* *Verification process:* Test restores to ensure backup integrity, Automated verification tools.
### 4. User Account Review and Management
Regularly review user accounts -> Disable inactive accounts and Update permissions as needed.

## Monitoring System Performance
Helps identify bottlenecks and performance issues
**Key metrics:** CPU usage, memory usage, disk I/O, network throughput

🛠️Tools -> Task Manager (Windows), top/htop (Linux), Activity Monitor (macOS), Zabbix
## System Logs
System logs record events that occur within a system. These include Application logs, Security logs and System logs.

🛠️Tools -> Splunk, , Graylog and the ELK Stack (Elasticsearch, Logstash, Kibana).

---

# User and Group Management

## Users
Every person or entity that interacts with a system is identified as a "user." Users have unique IDs and roles, determining what resources they can access.

Types of Users
1.   **Root/Administrator:** Has unrestricted access to the entire system.
2.   **Standard Users:** Limited access based on assigned permissions.
3.   **Service/System Users:** Accounts used by services, applications, and domains for background tasks.

User Account Types
1. **Local Accounts** -> Stored on the local system and used for local access only.
2. **Domain Accounts** -> Managed by a central server and used across multiple systems in a network.
3. **Service Accounts** -> Non-human accounts, Used to run services or applications.
## Groups
Groups are collections of users who share similar access permissions or roles. The purpose of groups is to simplify the administration of permissions and policies.

Types of Groups
1.   **Local Groups**
2.   **Domain Groups**
## Permissions
Permissions determine what actions a user or group can perform. Assign permissions to groups to manage access efficiently.

### Understanding Permissions and Access Control

**Permissions in Linux** -> Files have three main permissions: Read (r), Write (w), Execute (x). Permissions apply to three categories: Owner, Group, Others.

**Permissions in Windows** -> Files and folders have NTFS permissions which control access (Full Control, Modify, Read & Execute). Managed through Security Tab in file/folder properties.

It is best to assign permissions to groups rather than individual users and Use the *principle of least privilege*: grant only necessary permissions.

<small> A "Group Policy Misconfiguration" is a much bigger mistake when compared to a "User Account Compromise", as administrators are often suspended and in some cases terminated from the service for this mistake.</small>
## Best Practices
1.   Regularly audit user and group access rights.
2.   Use strong password policies and enforce multi-factor authentication.
3.   Monitor and review group memberships, especially for privileged groups.
4.   Regularly remove or disable inactive user accounts.

---

# Security and Policy Administration

**Authentication** -> The process of verifying a user's identity. There are 3 main methods of doing this: *Passwords*, *Biometrics*, *2FA* (Two-Factor Authentication)
### 1. Passwords
Enforce strong password policies to enhance security: Minimum length, complexity requirements; Regular password expiration; Avoid common passwords; Implement external key methods for higher management.
### 2. Two-Factor Authentication (2FA)
Adds an extra layer of security by requiring two forms of authentication. Methods include SMS codes, authentication apps, and hardware tokens. Example: Google Authenticator.
### 3. Biometrics
Unique physical characteristics to verify identity like Fingerprints, facial recognition, retina scans. Benefits include higher security and ease of use. Most notably used by higher management and administrators.

## Managing User Sessions
Monitor and manage active user sessions for security. Methods include session timeouts, activity monitoring, and manual session termination.

🛠️Tools -> Task Manager (Windows), top (Linux), Activity Monitor (macOS).
### Security Best Practices
*   Implement the principle of least privilege.
*   Regularly update and patch systems.
*   Educate users about phishing and social engineering.
*   Backup data regularly and verify backups.
## 8. Cloud Computing
> The delivery of computing services over the internet (the "cloud"). These services include storage, databases, servers, networking, software etc.

### 8.1. Key Characteristics
1. **On-demand Self-service** --> Users can provision resources as needed without human intervention from the service provider.
2. **Broad Network Access** --> Services are accessible over the network and support a variety of devices (e.g., mobile phones, laptops).
3. **Resource Pooling** --> Cloud providers pool resources to serve multiple consumers using a multi-tenant model.
4. **Rapid Elasticity** --> Resources can scale up or down as needed.
5. **Measured Service** --> Resource usage can be monitored, controlled, and reported, offering transparency for both provider and consumer.

> [!INFO] Easier Explanation
> Think of cloud computing like renting a house. You only pay for what you use (on-demand), you can access it from anywhere (broad access), many people can rent from the same company (resource pooling), you can easily upgrade to a bigger house or downgrade to a smaller one (elasticity), and you get a bill showing exactly what you used (measured service).

### 8.2. Types of Cloud Computing Services

| Service Type                               | Description                                                                                                                                                  | Examples                                              |
| ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------- |
| **IaaS** <br>(Infrastructure as a Service) | Virtualized computing resources over the internet. Users rent infrastructure like servers, virtual machines (VMs), storage, networks, and operating systems. | • AWS EC2<br>• Google Compute<br>• Azure VMs          |
| **PaaS**<br>(Platform as a Service)        | Provides a platform allowing users to develop, run, and manage applications without dealing with infrastructure management.                                  | • App Engine<br>• Elastic Beanstalk<br>• Azure Apps   |
| **SaaS**<br>(Software as a Service)        | Delivers software applications over the internet eliminating the need for installing and running applications on individual computers.<br>                   | • Salesforce<br>• Microsoft 365<br>• Google Workspace |
> [!INFO] Easier Explanation
> Cloud services come in three main types:
> - IaaS (is like renting an empty apartment) - you get the basics and set up everything else yourself
> - PaaS (is like renting a furnished apartment) - the basics are already set up for you
> - SaaS  (is like staying at a hotel) - everything is managed for you

**Other Service Models**

| Model                               | Description                                                                                                           | Examples                                                  |
| ----------------------------------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| **FaaS**<br>(Function as a Service) | Allows users to execute code in response to events without the complexity of building and maintaining infrastructure. | - AWS Lambda, <br>- Azure Functions                       |
| **DaaS**<br>(Database as a Service) | Databases provided as managed services in the cloud.                                                                  | - Amazon RDS, <br>- Azure SQL,<br>- Google Cloud BigTable |

### 8.4. Cloud Deployment Models

| Model | Characteristics | Benefits | Best For |
|-------|----------------|----------|-----------|
| Public | Third-party owned, shared resources | • Cost-effective<br>• Scalable<br>• Low maintenance | General computing, Web apps |
| Private | Single organization, dedicated resources | • Maximum control<br>• Better security<br>• Customization | Sensitive data, Compliance |
| Hybrid | Combined public/private | • Flexibility<br>• Cost optimization<br>• Risk management | Mixed workloads |
| Community | Shared by similar organizations | • Cost sharing<br>• Common compliance<br>• Collaborative | Healthcare, Government |
> [!INFO] Easier Explanation
> Think of cloud deployments like different types of gyms:
> - Public cloud is like a public gym - anyone can join, pay as you go
> - Private cloud is like a personal home gym - only you can use it
> - Hybrid cloud is like having both gym memberships - use what works best
> - Community cloud is like a gym for a specific group (e.g., employees only)

### 8.5. Cloud Services and Providers

**Major Providers** --> Amazon Web Services (AWS), Microsoft Azure, Google Cloud Platform (GCP), Others (IBM Cloud, Oracle Cloud, Alibaba Cloud etc...)

**Cloud Service Categories**
- Computing --> Virtual machines, serverless functions, containers.
- Storage --> Block storage, object storage, file storage.
- Databases --> SQL, NoSQL, in-memory databases.
- Networking --> Virtual networks, load balancers, CDNs.
- AI/ML --> Machine learning models, natural language processing, computer vision.
- Security --> Identity management, encryption, firewall solutions.
- DevOps Tools --> CI/CD tools, code repositories, testing environments.

**Tools**
1. Docker Desktop (containerization)
2. Docker Compose/Kubernetes (container management)
3. Ansible/Chef/Puppet (configuration management)
4. Terraform (infrastructure management)
5. CloudSim (cloud simulation)
6. Vagrant (VM provisioning)

---

## 9. Backup and Recovery Strategies

### 9.1. Types of Backups
1. **Full Backup** --> *Complete data copy* (only data).
2. **Incremental Backup** --> *Changes since last backup*.
3. **Differential Backup** --> *Changes since last full backup*.
4. **Mirror Backup** --> *Exact source replica* (includes every single thing).
5. **Snapshot** --> *System state capture*.

> [!INFO] Easier Explanation
> Backups are like taking photos of your important documents:
> - Full backup is like taking a photo of everything
> - Incremental backup is like only photographing new or changed documents
> - Differential backup is like photographing everything that changed since your last complete photo set
> - Snapshot is like taking a quick picture of how everything looks right now

### 9.2. Backup Strategies
> **3-2-1 Rule** --> Maintain 3 copies of data, on 2 different media, with 1 copy off-site.

**Backup Types by Priority**
- *Cold backups* (offline | for low-priority data)
- *Warm backups* (accessible | for medium-priority data)
- *Hot backups* (real-time | for high-priority data)

Backup Frequency --> After how long are backups done۔
Backup Retention --> How long a backup is stored۔
### 9.3. Implementation Methods
1. **Local Backups** --> Done on *Physical* (directly attached) storage like external hard drives.
	- Pros: Fast backup and recovery, No need for internet, Complete data control.
	- Cons: Physical maintenance required, Vulnerable to local disasters, Hard to scale.
2. **Remote Backups** --> Done on *Off-site* storage in some other location like data centers.
	- Pros: Protection against local disasters.
	- Cons: Slower recovery times, logistical challenges.
3. **Cloud Backups** --> Done on *Cloud* storage like AWS S3, GCloud Storage, Azure Blob.
	- Pros: Easy to scale, Automatic and Accessible from everywhere.
	- Cons: Needs internet, Has monthly subscription cost.
### 9.4. Disaster Recovery Planning and Testing
**Importance**: Ensures business continuity during unexpected events. Minimizes downtime and data loss.

**Steps in Disaster Recovery Planning**
1. *Risk Assessment*: Identify potential risks and vulnerabilities.
2. *Define Recovery Objectives*:
	1. Recovery Point Objective (RPO) --> Maximum acceptable data loss.
	2. Recovery Time Objective (RTO) --> Maximum acceptable downtime.
3. *Make a Disaster Recovery Plan* (DRP): Identify critical systems and data. Specify backup and restoration procedures. Assign roles and responsibilities.

**Testing DRP** --> Simulated discussion of the DRP (*Tabletop Exercise*), Step-by-step review of recovery procedures (*Walkthrough Test*), Actual recovery simulation (*Live Drill*).

---

## 10. Network Troubleshooting and Performance Tuning

### 10.1. Common Network Issues
1. Connectivity Problems --> Faulty Cables
2. Bandwidth Issues --> Low Bandwidth, Network Loss
3. Software Configuration Errors --> Outdated Drivers, Main Terminal Failed
4. Hardware Failures --> Cache Overload
5. Security Threats

**Root-Cause Analysis** --> Use the OSI Layers to identify and compare causes with symptoms.

> If there's an attack; To check the level/scope/size of attack --> Count the number and Check the physical/geographical range of affected devices. The solution to these attacks is to check the equipment closest to you (proximity) to get an idea about the attack. Also, immediately disconnect affected devices with the rest of the network to avoid other devices getting affected.

> [!INFO] Easier Explanation
> Network troubleshooting is like being a detective:
> - You use different tools (like Ping, Traceroute) to find clues
> - Each tool tells you something different about the network's health
> - Performance metrics are like vital signs (heartbeat, temperature) but for your network

### 10.2. Diagnostic and Troubleshooting Tools and Techniques

#### 10.2.1. Troubleshooting Tools
There are two types of troubleshooting tools:

- **Physical Tools** --> Equipment like *LAN Tester*, *Voltage Equipment*, *Splicing Tools*, *Clamps* etc... 
- **Software Tools** --> Tools like ping, traceroute, snmp, nmap, netstat, tcpdump, nslookup, dig etc.

| Tool       | Primary Use          | Best For            |
| ---------- | -------------------- | ------------------- |
| Ping       | Connectivity testing | Basic connectivity  |
| Traceroute | Path analysis        | Network mapping     |
| SNMP       | Device monitoring    | Network management  |
| Nmap       | Network scanning     | Security assessment |
> There are also "Third-party applictions" like **Wireshark** are also used for deep packet inspection and traffic analysis.

#### 10.2.2. Troubleshooting Techniques
1. *Baseline Analysis* --> Compare current system or network performance to historical data (the baseline).
2. *Port and Protocol Analysis* --> Check network traffic based on ports and protocols used by different applications and services.
3. *Simulation* --> Simulate network conditions in a controlled environment.
4. *Event Correlation* --> Analyzing logs and events from multiple sources.

### 10.3. Network Performance Tuning

#### 10.3.1. Performance Metrics

| Metric | Definition | Impact Factors | Optimization Methods |
|--------|------------|----------------|---------------------|
| Latency | Data travel time | • Network distance<br>• Processing delays | • CDN usage<br>• Edge computing |
| Bandwidth | Data capacity | • Network infrastructure<br>• Congestion | • Traffic shaping<br>• Load balancing |
| Jitter | Delay variation | • Network congestion<br>• Route changes | • QoS policies<br>• Buffer management |
| Packet Loss | Failed transmission | • Network errors<br>• Congestion | • Error correction<br>• Path optimization |

> [!INFO] Easier Explanation
> Network performance is like traffic on a road:
> - Latency is like the time it takes to drive from A to B
> - Bandwidth is like how many lanes the road has
> - Jitter is like inconsistent traffic speeds
> - Packet loss is like cars not reaching their destination

#### 10.3.2. Performance Tuning

1. **System-Level Tuning**
	- *Optimize Hardware* --> Upgrade hardware components into better ones.
	- *Update Firmware/Software* --> Keep system firmware and software up to date.
	- *Load Balancing* --> Distribute network traffic across multiple servers to prevent any single server from becoming overloaded.
	- *Quality of Service* --> Prioritize specific types of network traffic (e.g., voice, video, or business-critical applications) over others.
2. **Network-Level Tuning**
	- *Traffic Shaping* --> Controls the flow of network traffic to manage bandwidth usage and prevent congestion.
	- *Segmentation* --> Dividing a network into smaller, isolated segments.
	- *Caching* --> Storing frequently accessed data in a cache (a temporary storage location) closer to users.
	- *DNS Optimization* --> Configuring efficient DNS settings to reduce the time it takes to resolve domain names to IP addresses.

---

## 11. Security Policies and Compliance

### 11.1. Security Standards and Frameworks
- **ISO/IEC 27001**: A global standard for managing information security risks via an ISMS.  
- **ISO/IEC 27002**: A guide to best practices and controls for information security.**
- **NIST CSF**: A flexible framework to identify, protect, detect, respond to, and recover from cybersecurity risks.  
- **NIST SP 800-53**: A detailed catalog of security and privacy controls for managing federal information systems.
- **GDPR**: A European regulation enforcing data privacy and protection rights for individuals, with heavy penalties for non-compliance.
### 11.2. Implementing and Enforcing Security Policies

When developing Security Policies: Define scope, involve stakeholders, and customize policies.
- *Enforcement Mechanisms* --> Access controls (RBAC, MFA), Monitoring tools (IDS, IPS, SIEM), and Employee training.
- *Incident Response Plans* --> Establish procedures for security incidents.
### 11.3. Compliance Auditing and Reporting
> **Compliance Auditing** is the process of verifying whether an organization adheres to regulatory, industry, or internal standards. **Reporting** ensures findings are communicated effectively to stakeholders.

- Prepare for Audits --> Maintain documentation, conduct internal reviews, and ensure audit readiness.
- Conduct Compliance Audits --> External and internal audits, automated compliance tools, and penetration testing.
- Report Findings --> Create audit reports, develop action plans, and communicate with stakeholders.

---

## 12. Advanced System Administration
System Administation is differently done in Linux vs Windows:
1. **Linux Administration**
	- Command-line tools --> *grep*, *sed*, *awk*, and *find*.
	- System monitoring --> *top*, *htop*, and *vmstat*.
	- Security enhancements --> *SELinux*, *firewalls*, and *SSH* practices.
	- Configuration management --> *Ansible* or *Puppet*.
2. **Windows Administration**
	- Scripting/Automation --> *Powershell*.
	- Managing "Active Directory" and "Group Policies".
	- Performance monitoring --> *Event Viewer* and *Resource Monitor*.
	- Security --> *BitLocker*, *Windows Defender*, and *Firewall* settings.
### 12.1 High Availability Systems
> Ensuring minimal downtime and redundancy and Monitoring and failover mechanisms.

1. **Linux High-Availability Solutions** --> Clustering tools (Pacemaker, Corosync), Shared storage (NFS, iSCSI), Load balancing (HAProxy and Keepalived).
2. **Windows High-Availability Solutions** --> WSFC (Failover clustering), SQL Server "Always On" for database redundancy, NIC teaming and network load balancing.
### 12.2. Load Balancing and Failover Strategies
> **Load Balancing** --> Distributes network traffic across multiple servers for reliability and performance.

- *Load Balancing Tools* --> Software-based (HAProxy, Nginx), Hardware-based (F5 BIG-IP, Citrix ADC), Cloud-based (AWS Elastic Load Balancer, Azure Load Balancer).
- *Failover Strategies* --> **Active-Passive** (One server is active while another waits in standby), **Active-Active** (All servers handle traffic simultaneously), **DNS-Level** and **Database Failover** (Reroute traffic or database connections when primary services fail).

## Labs

Systems and Network Administration Labs - Mids Notes
## 1. Network Administration
Network administration involves **configuring, managing, and maintaining networks.**
**Key Responsibilities**
*   Configuring network devices
*   Monitoring network traffic
*   Managing user access
*   Troubleshooting network issues
*   Implementing security policies

**Types of Networks** -> Local Area Network (LAN), Wide Area Network (WAN), Metropolitan Area Network (MAN), Personal Area Network (PAN).
### 1.1 Networking Models
*   OSI Model (7 Layers)
*   TCP/IP Model (4 Layers)

**Networking Devices**
1.   **Router** -> Directs data between networks.
2.   **Switch** -> Operates within LAN, directing data between devices.
3.   **Firewall** -> Protects network by controlling traffic.
4.   **Access Point** -> Connects wireless devices to a wired network.

**Network Protocols** -> Set of rules that *allow communication between devices on a network.* Protocols define format, timing, sequencing, and error checking for data transmission. [[SNA Labs (Mids) - Jaish Khan#Networking Protocols]]

---

## 2. Network Monitoring
[[SNA Labs (Mids) - Jaish Khan#Network Monitoring Tools]]

> [!Question] Why monitor networks?
> *   **Performance Monitoring**: Ensures that the network is operating efficiently, detecting bottlenecks or failures.
> *   **Security**: Identifies suspicious or unauthorized activity on the network.
> *   **Troubleshooting**: Helps to pinpoint and resolve network issues quickly.
> *   **Capacity Planning**: Helps in forecasting network needs and preventing overload.

### 2.1 VLAN (Virtual Local Area Network)
> A technology that allows network administrators to create logically separate networks on the same physical switch.

We can define the "type" of the port of the switch to be either `access port` or `trunk port`.
1. **Access Port** -> Used for intra-vlan communication. (with devices on the same VLAN)
2. **Trunk Port** -> User for inter-vlan communication. (with devices on other VLANs)

[[SNA Labs (Mids) - Jaish Khan#VLAN(Extra Information)]]

### 2.2 Basic Router/Switch Configuration

**Basic Router Configuration**: Assign IP addresses, Static/Dynamic Routing Configuration and SSH Configuration for remote access.
**Basic Switch Configuration**: Configuring VLANs, Disable unused ports for security

---
## 3. Network Security
> It refers to practices and policies for preventing and monitoring unauthorized access, misuse, modification, or denial of a computer network and its resources.

The 3 Objectives of Security (CIA):
1.   **Confidentiality:** Ensuring only authorized users can access data.
2.   **Integrity:** Data should not be altered or tampered with.
3.   **Availability:** Network services and resources must be available to authorized users.
### 3.1 Types of Network Threats

| Passive Threats                                                    | Active Threats                                                        |
| ------------------------------------------------------------------ | --------------------------------------------------------------------- |
| Eavesdropping on network communications without altering the data. | Intentional actions that alter or disrupt data.                       |
| *Examples:* Packet sniffing, traffic analysis.                     | *Examples:* Man-in-the-Middle attacks, Denial-of-Service and Malware. |
#### 3.1.1 Types of Active Threats
1. **MitM** (Man-in-the-Middle) -> An attacker secretly intercepts and potentially alters communication between two parties who believe they are directly communicating.
	1. *Eavesdropping* -> Intercepting and reading unencrypted data.
	2. *Session Hijacking* -> Stealing a user's session token to impersonate them.
	3. *SSL Stripping* -> Downgrading an HTTPS connection to HTTP, allowing data to be read in plaintext.
	4. *DNS Spoofing* -> Altering DNS responses to redirect users to malicious sites.
2. **DoS** (Denial of Service) & **DDoS** (Distributed Denial of Service) -> Attacks that aim to make a network service unavailable by overwhelming it with illegitimate requests.
	6. *Volume-Based Attacks* -> Techniques like ICMP floods and UDP floods that overwhelm bandwidth.
	7. *Protocol Attacks* -> Exploits weaknesses in the network protocol stack, such as SYN floods and Ping of Death.
	8. *Application Layer Attacks* -> Targets specific web applications (e.g., HTTP flood) to exhaust server resources.
3. **Phishing** -> Attackers pose as a trustworthy entity to trick individuals into revealing sensitive information. Broad attempts using emails, fake websites, or messages.
	1. *Spear Phishing* -> Targeted phishing, often directed at specific individuals or organizations using personal information.
	2. *Whaling* -> Spear phishing targeting high-profile individuals (e.g., CEOs, CFOs).
4. **Malware Attacks** -> Software designed to disrupt, damage, or gain unauthorized access.
	1. *Viruses* -> Malicious code that attaches to files and programs, spreading to others.
	2. *Worms* -> Standalone malware that replicates itself to spread across networks.
	3. *Trojan Horses* -> Malicious software disguised as legitimate software; may create a backdoor.
	4. *Ransomware* -> Encrypts data and demands a ransom for decryption.
	5. *Spyware* -> Secretly monitors user activity to steal sensitive information.
	6. *Adware* -> Displays or downloads unwanted advertising material.
5. **Brute Force Attacks** -> Trying multiple combinations of usernames and passwords until the correct one is found.
	1. *Dictionary Attack* -> Uses a list of common passwords or words.
	2. *Credential Stuffing* -> Uses leaked credentials from one service to gain access to another.
6. **Spoofing Attack** -> An attacker masquerades as a legitimate entity by falsifying data to gain unauthorized access or steal information. Things like IP Spoofing, Email Spoofing, DNS Spoofing or MAC Spoofing.
7. **XSS** (Cross-Site Scripting) -> Attackers inject malicious scripts into websites viewed by other users. Things like Stored XSS, Reflected XSS or DOM-Based XSS.
8. **Insider Threats** -> Threats that come from within the organization. The insider can malicious, negligent or compromised.
9. **APT** (Advanced Persistent Threats) -> Prolonged and targeted cyberattacks in which an intruder remains undetected for an extended period.


### 3.2 Components of Network Security
* **Authentication** -> Verifying the identity of a user or device.
* **Authorization** -> Ensuring authenticated entities have permission to access specific resources.
* **Access Control** -> Policies that restrict access to the network.
* **Security Protocols** -> SSL/TLS, IPsec, HTTPS.
* **Network Policies**
### 3.3 Firewall
A security system that monitors and controls incoming and outgoing network traffic based on predetermined security rules. Used to establish a barrier between a trusted internal network and untrusted external networks (like the internet).

<div style="text-align: center;">Non-Intrusive Firewalls</div>
1. **Packet Filtering Firewall** -> Operates at Layer 3 (Network) and Layer 4 (Transport). Filters packets based on source/destination IP address, port number, and protocol. *Pros*: Low overhead, high speed. *Cons*: Limited security features and does not inspect payload.
2. **Stateful Inspection Firewall** -> Tracks the state of active connections. Monitors packets at Layer 3, 4, and can inspect parts of Layer 7 (Application). *Pros*: Provides enhanced security compared to packet filtering.

<div style="text-align: center;">Intrusive Firewalls</div>
3. **Proxy Firewall (Application Gateway)** -> Acts as an intermediary between end-users and servers. Can perform content filtering, cache data, and inspect traffic at Layer 7. *Pros*: Deep inspection of traffic and content filtering. *Cons*: Slower than packet filtering firewalls.
4. **Next-Generation Firewall (NGFW)** -> Integrates traditional firewall functionalities with additional features like deep packet inspection, intrusion prevention, and application awareness. *Pros*: Comprehensive security for modern threats.

#### 3.3.1 Firewall Configurations
*   **Perimeter Firewall** -> Placed at the network's boundary to filter external traffic.
*   **Internal Firewall** -> Deployed within the network to provide internal segmentation and protection.
*   **DMZ (Demilitarized Zone)** -> A network segment for exposing external services while isolating them from the internal network. Commonly used for public-facing servers (web, email).

### 3.4 VPN (Virtual Private Network)
A technology that creates a secure, encrypted connection ("tunnel") over a less secure network, such as the internet.It provides secure access to private network resources and maintains confidentiality and integrity of transmitted data.

| Remote Access VPN                                                                                                                      | Site-to-Site VPN                                                                                                        |
| -------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Connects individual users to a remote network. Commonly used for telecommuting or accessing company resources from outside the office. | Connects entire networks to each other (like a branch office to headquarters). Can be Intranet-based or Extranet-based. |
#### 3.4.1 VPN Protocols
1.   **IPsec** (Internet Protocol Security) -> Operates at Layer 3 and provides confidentiality, integrity, and authentication. Protocols Used: AH (Authentication Header), ESP (Encapsulating Security Payload).
2.   **SSL/TLS VPN** -> Uses the SSL/TLS protocol to secure VPN traffic, operating at Layer 4 (Transport). Ideal for remote access as it can be used via a web browser.
3.   **PPTP** (Point-to-Point Tunneling Protocol) -> Older protocol, fast but with security limitations. Rarely used due to vulnerabilities.
4.   **L2TP** (Layer 2 Tunneling Protocol) with IPsec -> Combines L2TP for tunneling and IPsec for encryption. Offers a secure and reliable connection.

**VPN Configuration**
*   *Authentication*: Users are authenticated using credentials (username/password, certificates, or multi-factor authentication).
*   *Encryption*: Select strong encryption algorithms (e.g., AES-256).
*   *Network Configuration*: Ensure that the VPN gateway is properly configured to route traffic securely through the tunnel.

### 3.5 Network Intrusion Detection and Prevention

> **IDS** (Intrusion Detection System) -> Monitors network traffic for suspicious activity and alerts administrators.

> **IPS** (Intrusion Prevention System) -> Similar to IDS but also takes proactive measures to block or prevent detected threats.

**Types of IDS/IPS**
1.   **Network-Based IDS/IPS** -> Monitors and protects the entire network by analyzing network traffic. Deployed at strategic points in the network (like behind a firewall).
2.   **Host-Based IDS/IPS** -> Monitors and protects individual hosts (like servers, workstations). Inspects system files, logs, and running processes.
#### 3.5.1 Detection Methods
*   **Signature-Based Detection** -> Uses predefined attack patterns (signatures) to detect known threats.
	*   *Pros*: Effective against known threats.
	*   *Cons*: Unable to detect new (zero-day) attacks.
*   **Anomaly-Based Detection** -> Establishes a baseline for normal network behavior and detects deviations from this baseline.
	*   *Pros*: Can detect unknown threats.
	*   *Cons*: May generate false positives if the baseline is not well-defined.
*   **Hybrid Detection** -> Combines both signature-based and anomaly-based techniques for comprehensive detection.
#### 3.5.2 Configuration and Placement
Place NIDS outside the firewall to monitor all incoming traffic, and consider placing another NIDS inside the network for internal monitoring. Set up alerts and logging to notify administrators in real-time. Regularly update signatures, adjust anomaly detection baselines, and fine-tune alerts to reduce false positives.

## 4. Network Optimization & Diagnosis

### 4.1 Network Diagnosis Tools
1.   **Ping** -> Tests connectivity between two devices. It sends ICMP echo requests and listens for responses. 
	*Usage*: Checking network availability, measuring latency, diagnosing packet loss. 
	*Example*: `ping google.com`
2.   **Traceroute** -> Traces the path packets take from source to destination. It sends packets with increasing TTL values and records the route. 
	*Usage*: Identifying slow network segments, diagnosing routing issues or loops. 
	*Example*: `traceroute google.com`
3.   **Netstat** -> Displays network connections, routing tables, interface statistics, and more. Shows current active connections and network statistics. 
	*Usage*: Identifying active TCP/UDP connections, monitoring network traffic, detecting unusual connections or port activity. 
	*Example*: `netstat -an`
4.   **Nslookup/dig** -> Queries DNS to resolve domain names to IP addresses. 
	*Usage*: Troubleshooting DNS issues, checking if a DNS server is working correctly.
	*Example*: `nslookup google.com` / `dig google.com`

**Third-Party Apps:** Wireshark, speedtest.net, Nmap, Crystal eye

### 4.2 Network Performance Metrics

| Network Performance Metric | Description                                                             | Measurement                                                  | Optimization                                                                    |
| -------------------------- | ----------------------------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------------------------- |
| **Latency**                    | *Time it takes for data to travel from source to destination and back.* | Using Ping or Wireshark to measure round-trip time (RTT).    | Reduce network hops. Improve hardware (routers, switches).                      |
| **Bandwidth**                  | *Maximum data transfer rate of a network connection.*                   | Tools like speedtest.net or network monitoring software.     | Prioritize traffic using QoS. Upgrade internet service or networking equipment. |
| **Throughput**                 | *Actual amount of data transferred successfully over the network.*      | Using network monitoring tools like Wireshark or SolarWinds. | Avoid congestion by load balancing. Upgrade network hardware.                   |
| **Packet Loss**                | *Percentage of data packets lost during transmission.*                  | Ping or network monitoring tools.                            | Improve connection reliability. Use redundancy.                                 |

### 4.3 Common Network Issues

| 1. Connectivity Issue                                                                                          | 2. Slow Network Speed                                                                                                      | 3. High Latency                                                                                                                               | 4. IP Address Conflict                                                                                                                        |
| -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| *Symptoms*: No network access, unable to connect to the internet.                                              | *Symptoms*: Slow downloads/uploads, buffering during streaming.                                                            | *Symptoms*: Delays in response times during communications.                                                                                   | *Symptoms*: Devices unable to connect to the network, "IP address conflict" error.                                                            |
| *Causes*: Faulty cables, misconfigured devices, DNS issues, or firewall blocking traffic.                      | *Causes*: Bandwidth bottlenecks, congestion, high latency, or packet loss.                                                 | *Causes*: Long routes, overloaded devices, or inefficient routing.                                                                            | *Causes*: Two devices on the network using the same IP.                                                                                       |
| *Solutions* <br>1. Check cables and ports.<br>2. Restart modems and routers.<br>3. Verify IP and DNS settings. | *Solutions* <br>1. Optimize bandwidth usage.<br>2. Identify high traffic devices or applications.<br>3. Upgrade equipment. | *Solutions* <br>1. `traceroute` to identify latency sources.<br>2. Reroute traffic through better paths.<br>3. Reduce the no of network hops. | *Solutions* <br>1. Ensure DHCP is configured correctly.<br>2. Assign static IP addresses to critical devices.<br>3. Expand the DHCP IP range. |

### 4.4 Optimizing Network Performance
*   **Load Balancing** -> Distribute traffic evenly across multiple servers or paths.
	*   Tools: Load balancers (e.g., HAProxy, NGINX) to ensure high availability and avoid bottlenecks.
*   **QoS** -> Prioritize critical traffic over less important data.
	*   Implementation: Set QoS rules on routers to allocate more bandwidth to high-priority applications.
*   **Network Segmentation** -> Reduce network congestion by segmenting traffic (e.g., VLANs).
	*   Benefits: Limits broadcast domains, improving performance and security.
*   **Monitoring and Proactive Measures** -> Continuously monitor network performance.
	*   Tools: SNMP-based network monitoring (e.g., SolarWinds, Zabbix).
*   **Regular Firmware and Software Updates** -> Ensure all network devices have the latest updates for performance improvements and security fixes.

---

# Less Important

## 1. Networking Protocols

| Protocol                                       | Description                                                                                      | Features                                                                                | Notes                                                                    |
| ---------------------------------------------- | ------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| **TCP** (Transmission Control Protocol)        | **Connection-oriented protocol** ensuring reliable, ordered, and error-checked delivery of data. | Connection establishment (3-way handshake), sequencing, error detection and correction. | *Uses*<br>Web browsing (HTTP/HTTPS), email (SMTP), file transfers (FTP). |
| **UDP** (User Datagram Protocol)               | **Connectionless protocol** used when fast transmission is more important than error correction. | No handshake or connection establishment, faster but less reliable.                     | *Uses*<br>Video streaming, online gaming, VoIP.                          |
| **IP** (Internet Protocol)                     | Delivers packets from source to destination based on IP addresses.                               | Defines IP addressing and routing, fragmentation, reassembly of packets.                | *Versions* <br>IPv4 (32-bit)<br>IPv6 (128-bit)                           |
| **ARP** (Address Resolution Protocol)          | Resolves IP addresses to MAC addresses in a local network.                                       | ARP requests are broadcast to discover MAC addresses.                                   |                                                                          |
| **ICMP** (Internet Control Message Protocol)   | Used by network devices to send error messages and operational information.                      |                                                                                         | *Uses*<br>Ping, Traceroute, error reporting.                             |
| **DHCP** (Dynamic Host Configuration Protocol) | Automatically assigns IP addresses and other network configuration parameters.                   | Simplifies IP address management, reduces manual configuration errors.                  |                                                                          |
| **DNS** (Domain Name System)                   | Translates human-readable domain names into IP addresses.                                        | User enters domain name; DNS resolver queries servers.                                  | *Command*<br>nslookup                                                    |
### 1.1 IP Addressing

- **IPv4 Addressing** -> *32-bit addresses* divided into four octets (192.168.1.1).
	- Address Classes: A, B, C, D, E for different network sizes.
- **IPv6 Addressing** -> *128-bit addresses* (2001:0db8:85a3:0000:0000:8a2e:0370:7334).
	- Advantages over IPv4: increased address space, simplified header structure.

| Subnetting                                                                                                                                          | Supernetting                                                                      |
| --------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Dividing a network into smaller subnets for improved management and efficiency. Subnet Mask defines the network and host portions of an IP address. | Aggregating multiple networks into a larger network to reduce routing table size. |

**NAT** (Network Address Translation) -> Modifies network address information in IP headers during transit. Allows multiple devices to share a single public IP address.
- *Types* -> Static NAT, Dynamic NAT, PAT.

## 2. Network Monitoring Tools

| Tool                               | Description                                                                                                                                          | Features                                                                                                                                                  | Usage                                                                          |
| ---------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Wireshark                          | A widely used, open-source packet analyzer that captures network traffic in real-time, enabling deep visibility into data packets being transmitted. | Captures and inspects packets at a granular level then provides details such as IP addresses, port numbers, and protocols and supports filtering.         | Troubleshooting, Security, Network Analysis.                                   |
| SolarWinds NPM                     | SolarWinds Network Performance Monitor is a comprehensive tool for monitoring network performance across distributed environments.                   | Monitors network traffic, device status, and performance metrics. Supports real-time alerts and graphs. Automatically discovers and maps network devices. | Centralized Monitoring, Alerting, Network Mapping.                             |
| Nagios                             | An open-source network monitoring tool used for monitoring the health of networks, servers, and applications.                                        | Monitors host and service status. Sends alerts via email, SMS, or other methods when network problems occur.                                              | Server and Device Monitoring, Custom Alerting.                                 |
| PRTG Network Monitor               | An all-in-one network monitoring tool that can track bandwidth usage, traffic, and the availability of various network services.                     | Monitors LAN, WAN, VPN, and Cloud services. Provides sensor-based monitoring of devices, applications, and traffic.                                       | Bandwidth Monitoring, Network Uptime Monitoring, Network Traffic Analysis.<br> |
### 2.1 Monitoring and Management Protocols
| Protocol                           | Description                                                                       | Usage                                                                                                    |
| ---------------------------------- | --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Simple Network Management Protocol | SNMP is used for monitoring network devices' performance and faults.              | Performance Monitoring, Fault Detection, Capacity Planning.                                              |
| NetFlow                            | Developed by Cisco to collect IP traffic information for monitoring purposes.     | Analyze network traffic, understand which devices are generating the most traffic, and detect anomalies. |
| Syslog                             | Used to send system log messages to a central server for monitoring and analysis. | Centralized log collection for troubleshooting and security auditing.                                    |
## 3. Network Routing
The process of choosing a path across one or more networks. Directing a data packet from one node to another.

There are limits to how many hop counts a packet can do; if it is exceeded, the packet is considered to be lost.

It works by finding the shortest path from the source node to the destination node across a network. Steps involved in Routing:
1. *Communication initiation* -> One node initiates communication across a network.
2. *Data Packets* -> The source device breaks information into small data packets, each labeled with the destination node's IP address.
3. *Routing Table* -> The source node uses the routing table to select the shortest path and routes the data packet accordingly.
4. *Hopping procedure* -> The data packet undergoes many hops across various nodes until it reaches the destination node.
5. *Reaching the destination node* -> The data packets re-assemble at the destination node, transforming into the complete information.
### 3.1 Types of Routing

| Static Routing                                                                                                                                                                              | Dynamic Routing                                                                                                                                                                                                                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Also called "non-adaptive routing". Routing configuration is done manually by the network administrator.                                                                                    | Works automatically without any human intervention. Packets are sent using various shortest-path algorithms and metrics.                                                                                                                                                                                      |
| *Advantages*<br><ol><li>Minimal CPU and memory resource usage.<br></li><li>Easy implementation in small networks.</li><li>Predictability because the next-hop is always the same.</li></ol> | *Advantages*<br><ol><li> Best for larger networks as it can handle many routes.<br></li><li>Can reroute traffic around failed links which improves reliability and uptime.<br></li><li>Calculates optimal routes based on metrics such as link speed.</li></ol>                                               |
| *Disadvantages*<br><ol><li>Configuration complexity in large networks.</li><li>Needs manual intervention is required to reroute traffic.</li><li>Prone to configuration errors.</li></ol>   | *Disadvantages*<br><ol><li>Requires more CPU, memory, and bandwidth.<br></li><li>Setting up dynamic routing protocols can be complex.<br></li><li>Routes can change due to fluctuations in network conditions, which may lead to unpredictable routing paths if not configured with clear policies.</li></ol> |
### 3.2 Routing Protocols

![[Routing.png | Routing]]

| Distance-Vector                                                             | Link-State                                                 |
| --------------------------------------------------------------------------- | ---------------------------------------------------------- |
| Each router maintains a table of distances to other routers in the network. | Each router has a complete map of the network topology.    |
| Based on distance (hop count)                                               | Based on entire network map                                |
| **Information Sharing** -> only with neighbors                              | **Information Sharing** -> With all routers in the network |
| **Updates** -> Periodic and full routing table                              | **Updates** -> Triggered updates with topology change      |
| Simple Implementation and Low Resource Usage                                | Complex Implementation and High Resource Usage             |
| Less Accurate and Slower to converge.                                       | Efficient Path Selection and Faster to converge            |
- A maximum of 15 hops (16 is unreachable).

## 4. VLAN(Extra Information)

> [!Question] Why use VLANs?
> Network Segmentation, Improved Security, Simplified Management, Broadcast Domain Control, Flexibility

### 4.1 802.1Q Encapsulation
A network standard used for **VLAN tagging** on Ethernet frames. 

#### 4.1.1 VLAN Tagging
Process of adding a tag to Ethernet frames to identify which VLAN they belong to. When a frame is tagged, switches and routers that support VLANs can forward it based on its VLAN ID.

- **Tagged frames**: These carry a VLAN ID, enabling them to traverse network segments designated for specific VLANs.
- **Untagged frames**: Frames without VLAN tags are usually treated as part of the *native VLAN* (default, untagged VLAN).

It allows network administrators to enforce segmentation, access control, and traffic isolation without separate physical networks.

**Components**:
- **TPID** (Tag Protocol Identifier) -> A *2-byte* field with a fixed value which tells if the tagging is set or not.
- **TCI** (Tag Control Information) -> A *2-byte* field with 3 subfields:
	- **PCP** (Priority Code Point) -> A *3-bit* field for specifying the **frame's priority level** (0-7). PCP is used in **Quality of Service (QoS)** to prioritize network traffic, with higher numbers indicating higher priority.
	- **DEI** (Drop Eligible Indicator) -> A *1-bit* field which tells if the frame can be dropped under network congestion.
	- **VID** (VLAN Identifier) -> A *12-bit* field that specifies the **VLAN ID** (0-4095), identifying the VLAN the frame belongs to.
#### 4.1.2 Native VLAN
The "default" VLAN that carries untagged traffic on a trunk link. By default, VLAN "default" is set as the native VLAN.
#### 4.1.3 ROAS (Router-on-a-Stick)
A technique for enabling **inter-VLAN routing** using a single physical router interface.

### 4.2 VLAN Creation in Packet Tracer
1. `interface` command -> used to specify ports. 
2. `switchport mode` command -> tells which mode the port is going to be (can be `access` or `trunk`).
3. `switchport access vlan` command -> allows us to create a new VLAN by specifying the id (`10`, `20`, `30`).
4. `show vlan brief` command -> shows VLAN configuration information.
5. `vlan <id>` into `name <name>` -> to change the name of the VLAN.
```bash
interface range g1/0-3
switchport mode access
switchport access vlan 10

interface range g2/0-2
switchport mode access
switchport access vlan 20

interface range g3/0-3
switchport mode access
switchport access vlan 30

do show vlan brief

vlan 10
name ENGINEERING

vlan 20
name HR

vlan 30
name SALES
```

## Other Random Things
1. We only require a single primary and a single backup connection (having more than that is a waste of resources).
2. If all connections break then it is called a *Network Outage*.
3. **Broadcast Domain** -> The scope within which broadcast frames are forwarded. A single VLAN or LAN (Router) is 1 broadcast domain.
4. **Collision Domain** -> The network segment where data collisions can occur. A 32-port switch has 32 collision domains.



## 1. File Systems and Architecture

### 1.1. File System Architecture

**File System** --> The method operating systems use to organize and store files on storage devices. It handles data storage, retrieval, and organization of files and directories. Choosing the correct file system is very important for system efficiency and reliability since they have different levels of performance, data integrity, and security.

### 1.2. Types of File System Architecture

1. **FAT32** (File Allocation Table 32) --> introduced by Microsoft in the mid-1990s, is simple and highly compatible across operating systems, making it ideal for USB drives and external storage. However, it has significant limitations, such as a maximum file size of 4GB and partition size of 2TB, which makes it unsuitable for modern needs. 
2. **NTFS** (New Technology File System), also developed by Microsoft, is the default file system for Windows. It supports larger file and partition sizes, offers better security with file permissions and encryption, and provides advanced features like journaling and compression. It is less compatible with non-Windows systems without additional software. 
3. **ext4** (Fourth Extended Filesystem) is the standard file system for Linux systems. It balances performance and reliability with features like journaling, support for large volumes, and reduced fragmentation. Although it works well in Linux, its compatibility with Windows and macOS is limited without third-party tools. Each file system serves a specific purpose, with FAT32 focusing on portability, NTFS on advanced Windows integration, and ext4 on Linux efficiency and scalability.

| Feature               | NTFS                          | EXT4                                        |
| :-------------------- | :---------------------------- | :------------------------------------------ |
| Made By               | Microsoft                     | Linux community (open source)               |
| Platform              | Windows                       | Linux                                       |
| Max File Size         | 16 exabytes (practical lower) | 16 terabytes                                |
| Max Volume Size       | 256 terabytes                 | 1 exabyte                                   |
| Journaling            | Yes, transaction logs         | Yes, write-ahead logging                    |
| File Permissions      | Advanced (ACLs)               | Standard POSIX (user/group/world)           |
| File System Type      | MFT-based                     | Inode-based, uses block groups              |
| Compression           | Supported                     | Not natively supported                      |
| Encryption            | Supported (EFS)               | Not natively supported                      |
| Performance           | Good, large files             | Excellent, particularly for Linux workloads |
| Use Cases             | Windows, large file storage   | Linux, general-purpose computing            |
| Hard Link Support     | Yes                           | Yes                                         |
| Symbolic Link Support | Yes                           | Yes                                         |
### 1.3. Disk Partitioning and Mounting

**Disk Partitioning** --> Dividing a physical disk into separate, isolated sections (partitions), each functioning as a logical disk.
- **Why Partition?**
	*   Organization --> Separate data into sections (OS, user data, backups).
	*   Dual Booting --> Install multiple OSes on the same disk.
	*   Data Management --> Improve performance by isolating filesystems, simplify backup/restore.
	*   Security --> Limit access to specific disk sections.
	*   Tools --> Disk Management tool, Diskpart command line.

**Disk Mounting** --> Making a partition's filesystem accessible to the OS and user. The OS can then read/write to the disk. Linux mounts to directories like /mnt or /media. Windows uses drive letters (D:, E:).
- **Why Mount?** --> Allows the OS to interact with new disks/partitions by assigning a logical location (directory) for file access.

## 2. Linux Installation and Configuration

**Linux** --> An open-source OS known for stability, security, and customization, popular among developers and system administrators.
*   **WSL** (Windows Subsystem for Linux) --> Enables running a full Linux environment directly on Windows 10, providing access to Linux tools, applications, and a terminal.

### 2.1. Installation on Windows

1. **Check Windows Version**  
   WSL requires Windows 10 version 1607 or later. Check by pressing `Win+R`, typing `winver`, and pressing Enter.

2. **Enable WSL and Virtual Machine Platform**  
   Open PowerShell as Administrator and run:
   ```powershell
   dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
   dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
   ```
   Restart your computer.

3. **Install a Linux Distribution**  
   Open the Microsoft Store, search for "Linux" or "WSL," select a distribution (e.g., Ubuntu), install, and launch it.

4. **Set Up Linux**  
   On first launch, set up a UNIX username and password.

5. **(Optional) Set WSL 2 as Default**  
   Run in PowerShell as Administrator:  
   ```bash
   wsl --set-default-version 2
   wsl --set-version <DistroName> 2
   ```

6. **Access Files**  
   Open File Explorer: `\\wsl$`

7. **Install Software**  
   Use your distribution's package manager:  
   ```bash
   sudo apt update
   sudo apt install <package-name>
   ```

### 2.2. Linux File System Structure  
Linux uses a hierarchical structure with `/` as the root directory.

**Common Directories:**
- `/home/`: User home directories  
- `/etc/`: Configuration files  
- `/bin/`: Essential binaries  
- `/usr/`: Programs, libraries, docs  
- `/var/`: Logs, spools  
- `/tmp/`: Temporary files  

**Commands:**
- Create a directory: `mkdir <directory>`  
- Create a file: `touch <file>` or `echo 'text' > <file>`  
- Verify files: `ls` or `stat <file>`  
- Add a user: `useradd -m -s /bin/bash <username>`  
- View users: `cat /etc/passwd`  

### 2.3. File and Directory Permissions in Linux  
Permissions control access to files and directories (read: `r`, write: `w`, execute: `x`).

**View Permissions:**  
```bash
ls -l <filename>
```

**Modify Permissions:**  
```bash
chmod u+x <file>   # Add execute for owner  
chmod g-w <file>   # Remove write for group  
chmod o=r <file>   # Read-only for others  
chmod 755 <file>   # Owner rwx, group/others rx  
chmod 644 <file>   # Owner rw, group/others r  
```

---

## 3. System Security and Hardening Best Practices

1. **Least Privilege:** Only give users and services the access they truly need. Avoid giving admin or root privileges unnecessarily, and check access regularly.  
2. **Regular Updates:** Keep your system and apps updated, especially for security fixes. Use automated tools to manage updates.  
3. **Strong Authentication:** Use multi-factor authentication (MFA) and strong passwords. Disable any default or unused accounts.  
4. **Encryption:** Protect sensitive data by encrypting it during transfer and storage. Use secure protocols like HTTPS and SSH.  
5. **Backups:** Automatically back up important data and system settings, store backups securely off-site, and test that you can restore them.  
6. **Firewalls & Network Segmentation:** Set up firewalls, separate networks by purpose, and use tools to detect and prevent threats.  
7. **Logs and Audits:** Turn on detailed logging, check logs regularly, and use a centralized system to manage them.  
8. **Remote Access:** Use VPNs for secure remote connections, limit access to trusted IPs, and enable MFA. Consider using bastion hosts for extra security.  
9. **System Hardening:** Strengthen systems by removing unnecessary apps and services, and follow best-practice guidelines like CIS Benchmarks.  
10. **User Awareness:** Train users on safe practices, like avoiding phishing scams and using strong passwords. Test their knowledge with simulated attacks.  
11. **Access Control:** Use role-based access controls (RBAC), check user access logs, and remove unneeded permissions.  
12. **Traffic Monitoring:** Monitor network traffic to spot unusual patterns and potential threats.  
13. **Separation of Duties:** Split important security tasks among multiple people to reduce the risk of insider threats.