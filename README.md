# security-job-interview
organizing security engineer job interview questions and answers

## Questions
1. **How does internet work? How to connect from your laptop?**  
   The Internet is a huge network where a lot of servers and devices are connecting. I will give you an example case that connects to google web site which is on google server, from my browser on my laptop computer. In this case, there are two key components to make the connection. One is a DNS server, and the other is SSL. First, I know and input the FQDN of google web site, which is www.google.com. But the client and server can connect over the internet only by IP address. So the client needs to resolve the FQDN to google website's IP address. DNS server plays this role. Client sends a request to DNS server to give back the IP address, then, the client reaches google web site to initiate SSL handshake. SSL encrypts the packets to keep confidentiality and integrity. After the handshake is completed, a session is held between the client and google website.
2. **Tell me about DNS server behavior when you connect to the internet.**  
   As I mentioned, the DNS, which is a domain name system, matches the hostnames to their corresponding IP addresses. In the DNS system, the dns server is consist of a hierarchical and distributed structure based on the domain name. When a user types the URL of a website into a browser, for example www.google.com, the DNS query is requested to the DNS root server, which knows the top level domain DNS server address. In this case, the top level domain is “.com”. So the request is passed to the .com server. This server knows the IP address of the dns server which administers google.com domain so the request is passed to there again. This server knows the www.google.com IP address so this gives back the IP address of www.google.com to the client browser. Then client brouwser tries to connect www.google.com site and session is initiated.
3. **Tell me about SSL handshake.**  
   In SSL handshake, a server authenticates a client, exchanges and agrees on some information like encryption algorithm, data compression format, encryption key and so on. In detail, There are generally 2 round trip messages exchanges. First, the client sends an initial ClientHello message. In this message, the client starts to negotiate with the server about SSL/TLS version, encryption sweet, and compression format. Then the server sends back to the client ServerHello message, Certificate message, and ServerHelloDone message. In this message, the server answers the requests from the client like which SSL/TLS version to use with additional information like a public key in certificate and server random number for message encryption. Then the client sends a ClientKeyExchange message which contains the client random number and pre_master_secret encrypted by the server public key. Then, the client and the server create credential information like session keys by the random number and pre_master_secret. Finally, the server sends a Finished message to initiate an SSL/TLS session.
4. **What is the difference between SSL and TLS?**  
   TLS is the successor protocol to SSL. Namely, TLS is an improved version of SSL with additional features like DH key exchange algorithm. But sometimes TLS is called SSL or SSL/TLS for simplification.
5. **What are symmetric vs. asymmetric encryption?**  
   Symmetric encryption uses the same key to encrypt and decrypt. In the case that server A and server B communicate with encryption, each server has the same key to encrypt and decrypt the messages. Representatives are DES and AES algorithms. Asymmetric encryption uses different keys to encrypt and decrypt, which are called public key and private key. A message is encrypted by public key, and decrypted by private key. Once a message is encrypted, no one can decrypt and see plain text without the one who has a private key. Representatives are RSA algorithms. The major advantage of symmetric encryption is the faster speed of encryption and decryption. The advantage of asymmetric encryption is the ease of key exchange. Public keys can be distributed to an unspecified number of people without any security risk. 
6. **When would you use symmetric vs. asymmetric encryption?**  
   Symmetric encryption is used in the situation where speed is important. For example, SSL connection uses symmetric encryption algorithms in the sessions. On the other hand asymmetric encryption is used in the situation of connection with unspecified people. For example, SSL connection uses this algorithm to exchange a session key at SSL handshake.
   https://www.sciencedirect.com/topics/computer-science/asymmetric-cryptography
7. **What is RSA encryption? How does it work?**  
   RSA stands for Rivert-Shamir-Adleman which comes from the developers of this algorithm. This is a the very popular algorithms of asymmetric encryption. This algorithm uses the product of much larger prime numbers as a private creadencial which is nearly impossible to be factorized into original prime numbers. 
8. **Tell me about AES encryption? How does it work?**  
   AES stands for Advanced Encryption Standard. This algorithm is one of the symmetric encryption algorithms. Currently this is considered safe and fast as symmetric encryption so are used in many cases.
9. **How the ping command work?**  
    Ping is a command-line utility that acts as a test to see if a networked device is reachable. This utility uses echo request and reply of ICMP protocol. First local host issues ping command and sends a echo request packet to the remote host address which will be tested. Then the remote host send back echo reply packets to the local host. If there is no response from remote host, ping shows error messages which is key to solve the network problem. The major error messages are [here](./ping_errors.md).
10. **What is Cyber Kill Chain?**  
    Cyber Kill Chain is a part of the Intelligence Driven Defence model for the identification and prevention of cyber intrusions activity. This model provides seven steps which adversaries must completely progress through. Reconnaissance, weaponization, delivery, exploitation, installation, command&control(C2), Actions on objects. Finally, the adversaries collect user credentials or confidential assets from organizations. Defenders must block them at every steps by implementing security methods for each. More detail is [here](./cyber_kill_chain.md)
11. **Explain the OSI Model. What protocols are used.**  
    OSI stands for Open Systems Interconnection. This model describes severn layers that computer systems use to communicate over a network.The modern internet is not based on this model, but on the simpler TCP/IP model. However, the OSI 7-layer model is still widely used, as it helps visualize and communicate how networks operate, and helps isolate and troubleshoot networking problems. IOS model consists of 7 layers, Physical Layer, Data Link Layer, Network Layer, Transport Layer, Session Layer, Presentation Layer, and Application Layer. More details are [here](./osi_model.md).
12. **What is Server Hardening?**  
    Server hardening is a set of disciplines and techniques which improve the security of an 'off the shelf' server. NIST defines it as "a process intended to eliminate a means of attack by patching bulnerabilities and turning off non-essential services". Server Hardening is requirement of security frameworks such as PCI-DSS and is typically included when organisation adopt ISO 27001. The purpose is to reduce the attack surface of the server, which is all the different points where an attacker can attempt to access or damage the server. For that purpose, the goal of hardening is to remove all unnecessary components and access to the server in order to maximize its security.
13. **How would you implement Server Hardening?**  
    There are generally 9 elements of hardening, which are secure server location, control access permissions, set up your firewall, manage configuration, secure user accounts, apply patches to vulnerabilities, remove unnecessary software, plan a backup strategy, continuously monitor
14. **What is Server Hardening benchmark?**  
    A major Server Hardening benchmark is the Center of Internet Security(CIS). This is a set of globally recognized and consensus-driven best practices to help security practitioners implement and manage their cybersecurity defenses.
15. What is a zero-day vulnerability?
    
16. What is TTP?
17. What's the difference between hashing, encryption, and encoding?
18. Describe your home network or lab?
19. Which is more secure, open source or closed source?
20. What security framework is the best?
21. What is the primary goal of IT security or cybersecurity?
22. What is a threat, risk, and a vulnerability?
23. Where do you get security news from?
24. Why are preventive controls better than detective controls?
25. Should you compressed or encryped first?
26. What are the most important files in Linux?
27. What is the difference between shadow file and password file in linux?
28. What is previlege escalation in linux?\
29. What is the HTTP status code we might get back from a server?
30. What is the vulnerability assessment and penetration test?
31. What is the Mitre Att&ck framework?
32. How can we determine if an email is legitimate?
33. What is SQL injection and how to prevent it?
34. What is Cross-site Scripting (XSS) and how will you mitigate it?
35. What is data leakage and how will you detect and prevent it?
36. What is Salting?
37. What is Password salting?
38. What is honeypot?
39. What is Residual Resk?



22. What is the difference between IDS and IPS?
23. How would you approach reducing security vulnerability resolution times across software products?
24. Implement a cypher to perform basic encoding.
25. How would you protect against a specific type of security attack (e.g. man-in-the-middle)?
26. What sort of anomalies would you look for to identify a compromised system?
27. What tools and approaches would you use for penetration testing?
28. Given a specific scenario, how would you consider threat modeling?
29. Describe what happens when you type www.google.com into your browser.
30. How would you detect a DDOS attack?
31. How would you prevent buffer overflows and memory leaks?
32. How do you think about the different types of firewalls and when you would implement each one?
33. How do you ensure that a server is secure?
34. How do you differentiate between symmetric and asymmetric encryption?
35. What Is the CIA Triad?
36. What is the difference between HIDS and NIDS?
37. What Is SSL encryption?
38. Explain a brute force attack along with the steps to prevent it.
39. What do you mean by port scanning?
40. What is identity theft? Can you prevent it?
41. Black Hat Hackers vs. White Hat Hackers vs. Gray Hat Hackers: Are all illegal?
42. How frequently do you perform patch management?
43. Can you reset a password-protected BIOS configuration?
44. What is the difference between Black Box Testing and White Box Testing?
45. What do you mean by phishing? How many types of phishing are there?
46. What is forward secrecy?
47. What are spyware attacks?
48. What is ARP poisoning? Can you explain with an example?
49. What do you mean by SQL injection?
50. Explain active reconnaissance.
51. How do you differentiate between viruses and worms?
52. What is SYN/ACK, and how does it work?
53. Do you know what XXE is?
54. Differentiate XSS from CSRF.
55. What is a server-side request forgery attack?
56. What is the same-origin policy and CORS?
57. What is role-based access control (RBAC), and why do compliance frameworks cover it?
58. What is the NIST framework, and why is it influential?

## Technical Terms
[here](./terms.md)

## Threats
Major threats are [here](./threats.md)

## Vulnerabilities
Major vulnerabilities are [here](./vulnerabilities.md)

## Common ports
Common network ports are [here](./ports.md)

## Security tools
Common security tools are [here](./tools.md)

## Senario tasks
Senario based interview questions are [here](./senarios.md)


## References
1. https://www.edureka.co/blog/interview-questions/cybersecurity-interview-questions/
2. https://www.interviewkickstart.com/interview-questions/security-engineering-interview-questions
3. https://blog.tryexponent.com/how-to-prepare-for-a-security-engineer-interview/
4. https://www.indeed.com/career-advice/interviewing/cyber-security-interview-questions
5. https://www.youtube.com/watch?v=jb7T26soBo0
6. https://www.indeed.com/career-advice/interviewing/cyber-security-interview-questions
7. https://www.youtube.com/watch?v=7M4I0GaCWQA