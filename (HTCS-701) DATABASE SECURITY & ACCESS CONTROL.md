# 📘 DATABASE SECURITY & ACCESS CONTROL (HTCS-701)

## **DETAILED THEORY NOTES (EXAM ORIENTED)**
---

## 🔹 **UNIT I**

---

## 1️⃣ Introduction to Access Control **(IMP)**

**Access Control** is a core concept of information security that ensures **only authorized users are allowed to access specific resources** in a system.
It protects systems from **unauthorized access, misuse, and data leakage**.

Access control is applied to:

* Files
* Databases
* Applications
* Networks
* Operating systems

### Why Access Control is Needed:

* Prevents data theft
* Protects confidential information
* Ensures system stability
* Enforces organizational security rules

### Basic Components:

* **Subject** – User or process requesting access
* **Object** – Resource being accessed
* **Operation** – Read, Write, Execute, Delete

### Box Diagram:

```
[ Subject / User ]
        |
        v
[ Access Control Policy ]
        |
        v
[ Object / Resource ]
```

### Example:

In a university system, **students can view marks**, but **only teachers can update marks**.

---

## 2️⃣ Purpose and Fundamentals of Access Control **(IMP)**

The **main purpose** of access control is to **protect system resources** by allowing access only to legitimate users.

### Key Purposes:

1. Maintain **Confidentiality**
2. Ensure **Integrity** of data
3. Provide **Availability**
4. Prevent unauthorized activities
5. Support auditing and accountability

### Fundamental Steps of Access Control:

#### 1. Identification

User claims an identity (username, ID).

#### 2. Authentication

System verifies identity using:

* Password
* OTP
* Biometrics

#### 3. Authorization

System decides what resources the user can access.

#### 4. Accountability

User activities are logged.

### Box Diagram:

```
User → Identification → Authentication → Authorization → Access Granted
```

### Example:

Online banking login → OTP verification → Access to account → Transaction logs stored.

---

## 🔹 **UNIT II**

---

## 3️⃣ Policies of Access Control **(IMP)**

Access control **policies define rules** that determine **who can access what and under which conditions**.

Policies are **high-level guidelines** used by organizations to enforce security.

### Types of Policies:

* Discretionary policy
* Mandatory policy
* Role-based policy

### Importance:

* Provides consistency
* Helps meet compliance
* Reduces security risks

### Example:

A company policy states that **employees can access data only during working hours**.

---

## 4️⃣ Models of Access Control **(IMP)**

Access control **models translate policies into practical systems**. Access control models are frameworks used to manage user permissions and protect resources by defining how individuals or systems are granted access. As of 2026, the primary models implemented across physical and digital environments

They define:

* How permissions are assigned
* Who controls access decisions

### Common Models:

* DAC
* MAC
* RBAC

### Box Diagram:

```
Security Policy
      ↓
Access Control Model
      ↓
Access Control Mechanism
```

### Example:

RBAC model is used in hospitals where permissions depend on staff roles.

---

## 5️⃣ Mechanisms of Access Control

Access control mechanisms are **technical tools** that enforce policies.
While access control models define the high-level strategy (the why and who), mechanisms are the specific technical and physical tools used to enforce those policies (the how). As of 2026, these mechanisms are broadly categorized into logical and physical controls

### Common Mechanisms:

* Password systems
* Biometrics
* Smart cards
* Tokens
* ACLs

### Purpose:

* Enforce authorization
* Prevent unauthorized access

### Example:

Fingerprint scanner used for office entry control.

---

## 6️⃣ Discretionary Access Control (DAC) **(IMP)**

In DAC, **resource owners decide who can access their resources**.
Discretionary Access Control (DAC) is a decentralized security model where the owner of a resource (such as a file, folder, or database) has full authority to determine who can access it and what actions they can perform. Unlike models managed by a central authority, DAC allows individual users to grant, modify, or revoke permissions at their own discretion

### Features:

* Owner-Driven Control
* Flexible
* Common in operating systems

### Common Mechanisms:

* Access Control Lists (ACLs)
* Capability Lists

### Advantages:

* Easy to use
* Flexible sharing

### Disadvantages:

* Risk of data leakage
* Weak security

### Box Diagram:

```
Owner → Grants Permission → Other Users
```

### Example:

A user shares a file with read permission to another user.

---

## 7️⃣ Non-Discretionary Access Control

Access decisions are made by **central authority**, not owners.
Non-Discretionary Access Control (NDAC) refers to security models where access rights are regulated by a central authority or system-level policy rather than by the individual owners of resources. As of 2026, NDAC is the preferred standard for enterprise and high-security environments because it removes human error and unauthorized permission sharing.

### Features:

* Strict enforcement
* High security
* Less flexible

### Example:

Banking systems where users cannot change permissions.

---

## 8️⃣ Mandatory Access Control (MAC) **(IMP)**

MAC uses **security labels and classifications**.
Mandatory Access Control (MAC) is the most restrictive security model, where a central authority (system administrator) defines access rights based on security levels. In this model, individual users have no discretion to grant or revoke access to resources, even if they own them.

### Key Concepts:

* Subjects have clearance levels
* Objects have security labels
* Access is strictly controlled

### Advantages:

* High security
* Prevents data leakage

### Disadvantages:

* Complex
* Not user friendly

### Box Diagram:

```
User Clearance → Security Check → Resource Label
```

### Example:

Military systems where only authorized officers can access classified files.

---

## 9️⃣ Access Control List (ACL) & Limitations **(IMP)**

ACL specifies **which users can access a resource and what actions they can perform**.
An Access Control List (ACL) is a sequential set of rules used by computer systems and network devices to permit or deny access to resources. In 2026, ACLs remain a foundational mechanism for enforcing security policies across digital and physical environments.

### Structure:

* Attached to objects
* List of users + permissions

### Box Diagram:

```
File
 ├─ User A → Read
 ├─ User B → Write
 ├─ User C → No Access
```

### Limitations:

* Difficult to manage
* Poor scalability
* Large ACLs increase overhead

### Example:

Windows NTFS file permissions.

---

## 🔟 Capability List & Limitations

Capability list defines **what resources a user can access**.
Capability List (C-List) is a decentralized mechanism for enforcing access control where users or processes (subjects) hold "tickets" or "tokens" that grant them specific rights to resources (objects).

### Structure:

* Attached to users
* Contains object-permission pairs

### Box Diagram:

```
User → [File A: Read, File B: Write]
```

### Limitations:

* Capabilities can be copied
* Revocation is difficult

### Example:

Token-based authorization systems.

---

## 🔹 **UNIT III**

---

## 1️⃣ Role-Based Access Control (RBAC) **(IMP)**

RBAC assigns permissions based on **roles instead of individual users**.
Role-Based Access Control (RBAC) remains the industry standard for managing user permissions in large organizations. It simplifies administration by assigning permissions to specific roles (e.g., HR Manager, IT Admin) rather than to individual users.

### Key Elements:

* Users
* Roles
* Permissions
* Sessions

### Advantages:

* Easy management
* Scalable
* Secure

### Box Diagram:

```
User → Role → Permission → Resource
```

### Example:

Teacher role can upload marks; student role can view marks.

---

## 2️⃣ Core RBAC **(IMP)**

Core RBAC (also known as Flat RBAC) is defined as the foundational level of the NIST RBAC standard. It establishes the basic relationship between users, roles, and permissions without the complexities of hierarchies or constraints.
The primary objective of Core RBAC is to move away from managing thousands of individual user profiles to managing a smaller, more manageable set of predefined job functions.

Core RBAC defines:

* User-Role assignment
* Role-Permission assignment

### Example:

HR role assigned permissions to view employee data.

---

## 3️⃣ Hierarchical RBAC

Roles arranged in **parent-child hierarchy**.
Hierarchical RBAC is the standard advancement over Core RBAC that introduces a structured relationship between roles, allowing for the inheritance of permissions. This model reflects the natural reporting structure of an organization, where senior positions automatically possess all the access rights of their subordinates in addition to their own unique privileges.


### Advantage:

* Permission inheritance

### Box Diagram:

```
Admin
  |
Manager
  |
Employee
```

### Example:

Manager inherits employee permissions.

---

## 4️⃣ Statically Constrained RBAC

Constraints applied **during role assignment**.

### Purpose:

* Prevent conflict of interest

### Example:

User cannot be assigned both Auditor and Accountant roles.

---

## 5️⃣ Dynamically Constrained RBAC

Constraints applied **during session execution**.

### Example:

User can activate only one sensitive role per session.

---

## 6️⃣ Limitations of RBAC **(IMP)**

* Role explosion
* Complex administration
* Difficult in dynamic environments

---

## 7️⃣ Comparing RBAC with DAC and MAC **(IMP)**

| Feature     | DAC    | MAC    | RBAC   |
| ----------- | ------ | ------ | ------ |
| Control     | Owner  | System | Role   |
| Security    | Medium | High   | High   |
| Flexibility | High   | Low    | Medium |

---

## 8️⃣ RBAC Integration in Enterprise IT **(IMP)**

### RBAC for WFMS:

Controls workflow tasks based on roles.

### RBAC for UNIX & JAVA:

* UNIX: Groups
* JAVA: Security Manager

### Example:

Only developers can deploy applications.

---

## 🔹 **UNIT IV**

---

## 1️⃣ Smart Card Based Information Security **(IMP)**

Smart cards store **secure credentials and cryptographic keys**.
Smart Card-based security serves as a critical hardware-based mechanism for identity management and multi-factor authentication (MFA). Unlike traditional magnetic stripe cards, smart cards contain an embedded integrated circuit (IC) chip that can process data, provide cryptographic functions, and securely store sensitive information.

### Features:

* Embedded chip
* Tamper resistant
* Portable

### Box Diagram:

```
User → Smart Card → Reader → System
```

### Example:

ATM card.

---

## 2️⃣ Smart Card OS – Fundamentals

a Smart Card Operating System (SCOS) is a specialized, highly secure software framework embedded within a card's microprocessor. Unlike general-purpose operating systems (like Windows or Linux), an SCOS is designed for a single purpose: to manage data access, perform cryptographic operations, and ensure the integrity of the hardware-software boundary.

Manages:

* Memory
* Files
* Security
* Applications

### Example:

Java Card OS.

---

## 3️⃣ Design & Implementation Principles

* Secure architecture
* Minimal attack surface
* Efficient memory usage

---

## 4️⃣ Memory Organization **(IMP)**

Smart Card Memory is organized into three physical types and a logical file hierarchy:
### 1. Physical Memory Types
* ROM: Stores the permanent Operating System (SCOS). It cannot be changed after manufacturing.
* RAM: Temporary "scratchpad" for calculations and session data. It is wiped when the card is removed from the reader.
* EEPROM / Flash: Persistent, rewritable storage for user data, security keys, and account balances.

### 2. Logical File Hierarchy (ISO 7816)
The data is structured like a computer directory:
* Master File (MF): The "Root" directory of the card.
* Dedicated Files (DF): "Folders" that group specific applications (e.g., a folder for Banking, another for ID).
* Elementary Files (EF): The actual "Files" containing data (e.g., your name, a photo, or a digital certificate).

### 3. Security & Access
Access is governed by the SCOS, which uses Access Control Conditions to ensure an EF can only be read or written if specific criteria (like a PIN match or biometric scan) are met.


### Types:

* ROM – OS
* EEPROM – Data
* RAM – Temporary data

### Box Diagram:

```
ROM | EEPROM | RAM
```

---

## 5️⃣ Smart Card Files & File Management

Smart Card file management is standardized by ISO/IEC 7816-4, organizing data into a tree structure managed by the card's operating system.
1. **File Types Master File (MF):** The "Root" directory (Entry point).
* Dedicated Files (DF): "Folders" that separate different apps (e.g., Banking vs. ID).
* Elementary Files (EF): The "Files" holding actual data.

**2. Data Structures (EFs)
Transparent:** A continuous block of binary data (e.g., a photo).
* Linear Fixed: Set of records with equal length (e.g., a name list).
* Cyclic: A "ring" of records where new data overwrites the oldest (standard for transaction history).

**3. Management & Security
Selection:** Users navigate the tree using the SELECT command to pick a folder or file.
* Access Rules: Each file has specific Security Attributes (e.g., "Read only allowed after PIN entry").
* Lifecycle: Files are protected by "State" logic, meaning they can be "Active," "Deactivated," or "Terminated" (Permanent lock).




Stores:

* User identity
* Cryptographic keys
* Application data

### Example:

SIM card storage.

---

## 6️⃣ PPS Security Techniques **(IMP)**
The term "PPS Security Techniques" in the context of smart cards refers to mechanisms used during the Protocol and Parameter Selection (PPS) phase to ensure secure communication between a card and a reader. These are primarily a function of the underlying ISO/IEC 7816-3 standard.
Core Security Measures in PPS
The PPS phase is handled automatically by the reader's firmware and the card's operating system directly after the card is reset and the Answer to Reset (ATR) is transmitted. Its security techniques are intrinsic to the protocol's design
Includes:

* User identification
* Smart card security
* Quality assurance
* Testing

---

## 7️⃣ Smart Card Life Cycle – 5 Phases **(IMP)**

1. Design
2. Manufacturing
3. Personalization
4. Usage
5. Disposal

---

## 8️⃣ Smart Card Terminals

Used to communicate with smart cards.
Smart card terminals, or readers, are the essential interface devices that provide power to the smart card and facilitate secure communication between the card's chip and a host system. In 2026, the primary types are categorized by how they connect to the card (contact or contactless) and their deployment environment. 

### Example:

POS terminal.

---

## 🔹 **UNIT V**

---

## 1️⃣ Cloud Data Security **(IMP)**

Protects data stored in **cloud environments**.
cloud data security has shifted from reactive defense to a proactive, AI-driven model focused on predicting and preventing breaches in real-time. Organizations increasingly rely on centralized platforms like CNAPPs (Cloud-Native Application Protection Platforms) to unify visibility across complex multi-cloud and hybrid environments.

### 1. The Three States of Security
* Data at Rest: Protected by AES-256 encryption and Post-Quantum Cryptography (PQC) to resist future quantum computer attacks.
* Data in Transit: Secured via TLS 1.3 and Secure Access Service Edge (SASE), which encrypts data moving between users and cloud apps.
* Data in Use: Protected by Confidential Computing, which processes data inside hardware-isolated "enclaves" so even the cloud provider cannot see it.
### 2. Core Frameworks
* Zero Trust: "Never trust, always verify." Every request is checked for identity, device health, and location before access is granted.
* Shared Responsibility: The provider (e.g., AWS, Azure) secures the hardware; the user secures the data, configurations, and Identity and Access Management (IAM).
* DSPM (Data Security Posture Management): Automated tools that scan the cloud to find and secure "Shadow Data" (forgotten or unencrypted files).


### Recent Trends:

* Encryption
* Zero Trust
* Attribute-based access

### Example:

Encrypted cloud storage.

---

## 2️⃣ Database Security & Access Control **(IMP)**

database security has evolved to address the complexities of distributed cloud environments and the rise of AI-driven data processing. It focuses on protecting the Confidentiality, Integrity, and Availability (CIA) of data stored within Database Management Systems (DBMS).


Controls:

* Authentication
* Authorization
* Auditing

### Example:

Role-based DB access.

---

## 3️⃣ Cloud Data Audit – Introduction **(IMP)**

Cloud Data Auditing has become a strategic necessity as over 80% of organizations manage data across multiple public clouds. It is a systematic review of a company’s cloud infrastructure, security controls, and compliance posture to ensure that data is secure, accurate, and aligned with regulatory standards. 

### Core Objectives of Cloud Data Auditing
* Verification of Security Controls:
Assessing the effectiveness of technical safeguards like encryption (at rest and in transit) and multi-factor authentication (MFA).
* Regulatory Compliance:
Ensuring adherence to evolving global and regional laws such as GDPR, HIPAA, and India's DPDP Act.
* Risk Mitigation:
Identifying misconfigurations—which account for approximately 32% of security incidents—and unauthorized access points early.
* Operational Optimization:
Evaluating resource utilization and performance metrics to reduce waste and optimize cloud spending (FinOps).

### The "4 A's" Framework
A comprehensive 2026 cloud audit typically focuses on four crucial elements: 
* Authentication: Verifying the identity of users and systems attempting to access resources.
* Authorization: Determining if appropriate permissions (e.g., Role-Based Access Control) are correctly implemented.
* Accountability: Ensuring user actions are tracked and recorded for incident investigation.
* Auditability: Establishing clear audit trails through comprehensive logging and data retention policies. 
Audit checks:

* Data usage
* Compliance
* Security policies

---

## 4️⃣ Cloud Audit Best Practices

* Regular audits
* Log monitoring
* Least privilege

---

## 5️⃣ Key Management **(IMP)**

Key Management is the fundamental discipline of overseeing the entire lifecycle of cryptographic keys—from creation to destruction—to ensure the ongoing security of encrypted data. With 2026 marked by shrinking certificate lifespans and the transition to post-quantum security, automation has shifted from a convenience to a critical operational requirement.

Manages:

* Key creation
* Storage
* Rotation
* Revocation

### Box Diagram:

```
Key Generation → Storage → Usage → Rotation
```

---

## 6️⃣ Cloud Key Management Audit

Cloud Key Management Audit is a specialized assessment of the cryptographic systems that protect sensitive data across public, private, and hybrid clouds. Unlike traditional audits, a 2026 audit emphasizes Post-Quantum Cryptography (PQC) readiness, the management of thousands of non-human identities, and automated compliance drift detection.

### Core Focus Areas
* Separation of Duties: Verification that those who manage keys (admins) are not the same people who use keys (developers), preventing internal fraud.
* Key Lifecycle: Automated checks to ensure keys are generated in FIPS 140-3 hardware, rotated frequently, and "shredded" when deleted.
* Access Control: Checking that "Just-in-Time" (temporary) access and Multi-Factor Authentication (MFA) are enforced for all key-related tasks.

Ensures:

* Secure key storage
* Compliance
* Access control

### Example:

AWS KMS audit.
