# Lecture Notes: DLP and Classification


## Lecture 1 of 3: Data Loss Prevention (DLP)

- **Why** (5 min)

- Why use DLP?
  - PII/compliance requirements
  - Protecting intellectual property
  - Data visibility/monitoring

- **What** (10 min)

- What is DLP?
  - Data loss prevention is a data security control designed to monitor and control the movement of data by classification type
  - Differentiate
    - Program (policy)
    - Product (tool)

- What are the different types of DLP?
  - Endpoint
  - Network
    - Edge system (E.G. firewall)
  - Cloud
    - E.G O365 DLP

- What types of detection scenarios occur for systems like DLP and antivirus?
  - True positive
  - False positive
  - True negative
  - False negative

- What is driving the adoption of DLP systems?
  - Growth of CISO role
  - Compliance
  - Complexity of technologies/mobile devices
  - Data breaches
  - Stolen data sold on dark web

- What are some DLP best practices?
  - Figure out your objective for using DLP
  - Work with the C-level
  - Define roles and responsibilities
    - Data Owner - E.G. the administrator/CEO/board/president of a company
    - Data custodian - Professionals taking care of the actual data - like IT staff (generally) or HR staff (for HR-related data)
    - System owner - The individual that is in charge of one or more systems, which may contain and operate data owned by various data owners.

- **How** (30 min)
- How to implement and use DLP?

- **Experimentation and Discovery Ideas**

### Lecture 2 of 3: Data Classification

- **Why** (5 min)
- Why classify data?
  - Compliance such as GDPR
  - Manageability of systems and data
  - Improve security posture of organization
  - "Spring cleaning"

- **What** (10 min)
- What is data classification?
  - Process of organizing data by relevant categories so that it may be used and protected more efficiently.
  - [Standards for classification](https://digitalguardian.com/blog/what-data-classification-data-classification-definition)
    - Context-based data classification:
      - Content-based classification inspects and interprets files looking for sensitive information
      - Context-based classification looks at application, location, or creator among other variables as indirect indicators of sensitive information
    - User-based data classification:
      - User-based classification depends on a manual, end-user selection of each document.
      - User-based classification relies on user knowledge and discretion at creation, edit, review, or dissemination to flag sensitive documents.

  - **Data Roles and Responsibilities**
    - Data owner: Ultimately responsible
    - Data steward: responsible for data quality and oversight
    - Data custodian: information systems management
    - Data privacy officer: oversees PII assets

  - **Data Classifications**
    - Public (unclassified)
    - Confidential (secret)
    - Critical (Top-Secret)
    - Proprietary
      - Owned information of commercial value
    - Private/Personal Data
      - PII
    - Sensitive
      - Personal data such as beliefs, ethnic origin, or sexual orientation

  - **Privacy Notices and Data Retention**
    - Legislation and regulations
      - GDPR
      - Rights of data subjects
    - Privacy Notices
    - Impact Assessments
    - Data retention

  - **Data Sharing and Privacy Terms of Agreement**
    - Service Level Agreement (SLA)
    - Interconnection Security Agreement (ISA)
    - Non-disclosure Agreement (NDA)
    - Data Sharing and use agreement

- **How** (30 min)
- How to implement data classification?
  - Evaluate current data handling
  - Create a data classification policy
  - Prioritize and organize data

- **Experimentation and Discovery Ideas**

### Lecture 3 of 3: PCI-DSS Compliance

- **What** (5 min)
- Show: [Sample audit report](https://data.yorkopendata.org/dataset/16afe378-b8dd-4f14-bbc3-22cf4c512de0/resource/a2a762a2-b4d0-4e32-a1ee-1d76050688b0/download/pci-dss-compliance-1718---final-report.pdf)
