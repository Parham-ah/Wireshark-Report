# Wireshark-Report-DNS
Report on the review and analysis of DNS protocol in wireshark.

**Analyzing DNS packets using Wireshark**

**Introduction**
This project analyzes DNS (Domain Name System) packets using Wireshark tool. The purpose of this project is to investigate the behavior of the DNS protocol and extract information from the recorded network traffic. DNS packets contain information about requests (Queries) and responses (Responses) between the client and DNS servers.

![Screenshot 2024-09-10 151124](https://github.com/user-attachments/assets/19299082-4fe9-4405-b5dc-54fd042c1900)


**1.**Work steps****

Packet capture and filtering:
Wireshark was used to capture network traffic.
A dns filter was applied in Wireshark to display only packets related to the DNS protocol.

**2.**Checking DNS packets:****

DNS packets are divided into two main types:
Query: Requests sent from the client to the DNS server.
Response: DNS server responses to requests.

**The findings**

1.Total number of DNS packets captured: [146]
2.Total number of requests (Queries): [79]
3.Total number of responses (Responses): [67]

The difference in the number of requests (79) and responses (67) in DNS packet analysis can refer to several issues. This discrepancy indicates that some of the DNS requests sent from the client side did not receive a response from the server side, or their response was not fully recorded.

**The analysis of DNS packets showed that the highest number of type A requests were to get IP addresses associated with different domains.**

**Here, according to the image below, we want to check the DNS packet for the api.github.com**

If you look at the picture, you can see that the request first went from the source IP to the DNS that I set on my system. The request is a standard query with a length of 74 bits and transaction ID: 0xed0e, which is the same ID for the request and the response. In fact, according to the Transaction ID, it is possible to request and find something similar, I found the answer.
The word A means to use IPv4.
In the queries section, we see the desired domain.
But in the response section, it is returned from IP DNS to the source IP

![dns2](https://github.com/user-attachments/assets/ae70338b-0715-4d7f-a0d3-265561096bc4)
