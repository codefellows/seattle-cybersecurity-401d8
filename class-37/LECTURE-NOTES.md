# Lecture Notes: Automating AppSec with ZAP

## Review: Lab Class 30

## Review: Ops Challenge Class 30

## Demo: Ops Challenge Class 31

### Lecture: AppSec

- **Why** (5 min)

  - Why use OWASP ZAP to perform web app security assessments?
    - Automated CI/CD testing via ZAP API
    - More "experimental" than the traditional go-to Burp
    - Free and open source flagship active OWASP project
    - No rate throttling brute force attacks; simpler to use, don't have to pass to Hydra
    - Automatic scanning
  - Drawbacks VS Burp
    - Less "mature" and tends to be more experimental/buggy
    - Somewhat less [popular](https://www.reddit.com/r/oscp/comments/jpp4m2/owasp_zap_vs_burp_suite/) but many people use **both** ZAP and Burp

- **What** (10 min)

  - What is [OWASP ZAP?](https://www.zaproxy.org/)
    - Web application security test tool that acts as a MITM proxy. (DRAW) Features include:
      - Intercepting Proxy
      - Active and Passive Scanners
      - Traditional and Ajax Spiders
      - Brute Force Scanner
      - Port Scanner
      - [Web Sockets](https://en.wikipedia.org/wiki/WebSocket)
    - [Documentation](https://www.zaproxy.org/docs/api/#introduction)

  - What are [WebSockets](https://en.wikipedia.org/wiki/WebSocket)?
    - Full-duplex communication channel over TCP connection.
    - Enables interaction between web browser and web server over TCP 443 or 80
    - Separate protocol from HTTP but both on layer 7, reliant on TCP at layer 4.
    - All popular browsers support WebSockets

  - What is [AJAX](https://www.w3schools.com/whatis/whatis_ajax.asp)?
    - AJAX = Asynchronous JavaScript And XML.
    - AJAX is not a programming language.
    - AJAX just uses a combination of:
      - A browser built-in XMLHttpRequest object (to request data from a web server)
      - JavaScript and HTML DOM (to display or use the data)
    - Key features
      - Read data from a web server - after a web page has loaded
      - Update a web page without reloading the page
      - Send data to a web server - in the background

  - What is a proxy server?
    - Traditionally, a proxy server acts as a gateway between your PC and the internet.
      - A separate computer with its own IP.
      - Historically, on-prem enterprises used proxies to secure traffic into and out of the company LAN.
    - Today we will be setting up ZAP as a "proxy" to Mozilla Firefox.
    - All web traffic will be routed to and from ZAP, which will make the final decisions regarding when traffic will pass through.

- **How** (30 min)

  - How to use ZAP
    - First, you should perform a web app exploration procedure with ZAP against the target so that you have more to test against ("enumeration" stage). Here are some methods you can use:
      - Traditional Spider (Crawler): Use this approach to crawl the HTML resources (hyperlinks etc) in the web application.
      - Ajax Spider: Use this feature if the application heavily relies with Ajax calls.
      - Proxy Regression / Unit Tests This is the recommended approach for security regression testing. Use this approach to explore the application, if you already have a test suite or unit tests in place.
      - OpenAPI/SOAP Definition: Use this approach if you have a well defined OpenAPI definition. The OpenAPI plugin can be downloaded via the marketplace.
    - After the web app is explored, you're ready to scan for security vulnerabilities
      - Passive scan
        - All request proxied through ZAP or initialized by Spider are passively scanned (automatically scanned)
        - Passive scanning does not change or modify requests
      - Active scan
        - Active scans are attacks against the target URL.
      - View status
      - View results
      - Stop active scanning
        - Getting results
          - Security vulnerabilities are displayed as alerts sorted by priority (risk)
      - Getting authenticated
        - Many web apps don't show all content to the general anonymous user. ZAP supports web app authentication to help facilitate in-depth scanning.
          - Form-based authentication
          - Script-based authentication
          - JSON-based authentication
          - HTTP/NTLM based authentication
        - General steps
          - Step 1. Define a context
          - Step 2. Set the authentication mechanism
          - Step 3. Define your auth parameters
          - Step 4. Set relevant logged in/out indicators
          - Step 5. Add a valid user and password
          - Step 6. Enable forced user mode (Optional)

  - Ref. [DEMO.md](DEMO.md)

- **Experimentation and Discovery Ideas**
