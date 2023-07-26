# Lecture Notes: Reconstructing a Cloud Attack Using Log Data

## MITRE ATT&CK

- **What** (10 min)
  - **Tactics, techniques, and procedures (TTPs)** are “patterns of activities or methods associated with a specific threat actor or group of threat actors” -Definitive Guide to Cyber Threat Intelligence
    - The global repository of known TTPs is maintained by MITRE and is known at the MITRE ATT&CK® matrix
    - What is MITRE ATT&CK® (ref. Video - [Putting MITRE ATT&CK®™ into Action](https://www.youtube.com/watch?v=bkfwMADar0M))
      - **MITRE ATT&CK** is a "globally-accessible knowledge base of adversary tactics and techniques based on real-world observations."
      - "Used for developing threat models and methodologies"
      - Adversarial Tactics, Techniques, and Common Knowledge (ATT&CK™) for enterprise is a framework which describes the adversarial actions or tactics from Initial Access (Exploit) to Command & Control (Maintain).
      - A knowledge base of adversary behavior
        1. Based on real-world observations
        1. Free and open, globally accessible
        1. A common language
        1. Community-driven
        1. Adversaries use TTPs: Tactics, Techniques, and Procedures

      - ATT&CK is a knowledge base of cyber adversary behavior and taxonomy for adversarial actions across their lifecycle. ATT&CK has several parts:
        1. PRE-ATT&CK: Reconnaissance and infrastructure setup
        1. ATT&CK: Enterprise IT networks and cloud
        1. ATT&CK for Mobile: Behavior against mobile devices

## MITRE D3FEND

- **What** (10 min)
  - [MITRE D3FEND](https://d3fend.mitre.org/) is a complementary framework to the MITRE ATT&CK™ matrix
  - The D3FEND matrix helps cybersecurity professionals better defend and protect networks and information technology assets
  - Provides defensive techniques that can be applied to counter the activities of threat actors detailed within the MITRE ATT&CK™ matrix

## Reconstructing a Cloud Attack

- **Why** (5 min)
  - Why do we need to analyze API interactions in the cloud?
    - APIs have a reputation for having security vulnerabilities, yet are increasingly being utilized to keep pace with automation

- **What** (10 min)
  - What is a REST API?
    - **Representational State Transfer (REST) API** is a type of modern architectural style of API facilitating machine to machine communication
      - Formats: JSON, XML, or HTML
      - Pass in a noun and a verb
      - Uses HTTP methods:
        - GET to fetch data
        - PUT to alter the state of data (such as an object, file or block)
        - POST to create data
        - DELETE methods to eliminate it
  - Today's data set takes the form of a JSON file that has been imported into the SIEM. (Ref. [w3schools](https://www.w3schools.com/whatis/whatis_json.asp))
    - **JSON, or JavaScript Object Notation,** is a lightweight format for storing and transporting data, often used when data is sent from a server to a web page but increasingly adopted for situations where data arrays are needed.
    - Example JSON:
      ```json
      {
      "employees":[
        {"firstName":"John", "lastName":"Doe"},
        {"firstName":"Anna", "lastName":"Smith"},
        {"firstName":"Peter", "lastName":"Jones"}
      ]
      }
      ```
    - Note that in JSON format, data is stored in key-value pairs.
    - JSON is composed of lists of dictionaries, making it easily readable by not only APIs but the Python programming language as well. Opportunities for automation abound.
    - Objects are stored in curly braces.
    - Arrays are written in square brackets.
    - Example use case: AWS stores its configurations in JSON format. The IAM policy below serves as a block list for several IP addresses.

    ```json
    {
        "Version": "2012-10-17",
        "Statement": {
            "Effect": "Deny",
            "Action": "*",
            "Resource": "*",
            "Condition": {
                "NotIpAddress": {
                    "aws:SourceIp": [
                        "192.0.2.0/24",
                        "203.0.113.0/24"
                    ]
                },
                "Bool": {"aws:ViaAWSService": "false"}
            }
        }
    }
    ```

  - What is an AWS S3 Bucket?
    - **S3 Buckets** are a part of Amazon Simple Storage Service (S3).
    - Used for storing data files in the cloud.
    - Generally [secured](https://aws.amazon.com/premiumsupport/knowledge-center/secure-s3-resources/) using:
      - Secure configuration including bucket policies and IAM
      - MFA
      - ACL permissions for allowed actions on S3 objects
  - What is an API?
    - [**Amazon S3 REST API**](https://docs.aws.amazon.com/AmazonS3/latest/API/Welcome.html) is a part of the Amazon Simple Storage Service. Therefore, S3 supports the REST API.
    - The AWS CLI (AWS Command Line Interface) can be used to interact with the S3 REST API.
  - What is a reverse proxy?
    - A **reverse proxy** takes traffic from the internet from clients and routes to server.
    - Opposite of a forward proxy (normal proxy)
    ![reverseproxy.jpg](../assets/reverseproxy.jpeg)
    Source: [Medium](https://medium.com/commutatus/how-to-configure-a-reverse-proxy-in-aws-b164de91176e)

- **How** (30 min)
  - How can we make sense of cloud logs and API interactions?
    - We can use a SIEM to help parse and crawl logs.
