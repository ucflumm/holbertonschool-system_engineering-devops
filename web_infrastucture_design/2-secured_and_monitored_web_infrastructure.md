## Explanation of Components:
##### 1. Adding Firewalls:
    Each server is protected by a firewall to regulate and control incoming and outgoing network traffic, providing an additional layer of security to safeguard the infrastructure against potential threats and unauthorized access.
##### 2. SSL Certificate and HTTPS:
    An SSL certificate is added to serve www.foobar.com over HTTPS. This encrypts data transmitted between the server and users' web browsers, ensuring data integrity, confidentiality, and secure communication.
##### 3. Monitoring Clients (Sumo Logic or other monitoring services):
    Monitoring clients or data collectors are implemented to collect and analyze system and application data. Sumo Logic or similar services are used for performance monitoring, log analysis, and proactive issue detection.

### Specifics about the Infrastructure:
##### 1. Firewalls:
    Firewalls act as a security measure to control incoming and outgoing network traffic, preventing unauthorized access and potentially malicious requests from reaching the servers.
##### 2. HTTPS for Traffic:
    HTTPS encrypts the data transmitted between users and the website, securing sensitive information from being intercepted or tampered with during transmission.
##### 3. Monitoring Purpose:
    Monitoring tools are utilized to track system performance, detect issues, analyze logs, and proactively respond to potential failures or security breaches.
##### 4. Data Collection by Monitoring Tool:
    The monitoring tool collects data by deploying agents or clients on the servers, capturing metrics, logs, and other relevant information for analysis.
##### 5. Monitoring Web Server QPS:
    To monitor the web server QPS (Queries per Second), the monitoring tool needs to track and analyze the number of incoming requests to the web server over a given period.

#### Issues with this Infrastructure:
##### 1. Terminating SSL at the Load Balancer Level:
    Terminating SSL at the load balancer could expose the decrypted data between the load balancer and servers, potentially compromising data security.
##### 2. Single MySQL Server Capable of Accepting Writes:
    Having only one MySQL server capable of accepting writes creates a single point of failure for write operations. If this server fails, it disrupts the ability to write new data into the database.
##### 3. Servers with Same Components:
    Using identical components across all servers might create a problem if those components fail simultaneously. Diversity in server roles or staggered component versions could mitigate such risks.


To enhance this infrastructure, it's important to distribute write capabilities across multiple MySQL servers, consider SSL termination carefully, and introduce diversity in server components for increased resilience against failures.
