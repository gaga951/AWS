You create a hosted zone when you want to use Route 53 to route internet traffic for your domain or to route traffic within your VPCs. 
Then you create records in the hosted zone for the domain name (example.com) and subdomains (such as www.example.com or blog.example.com).

For example, suppose you have a web server that serves content for your example.com website. You create a public hosted zone named example.com. 
Then you create records named example.com and www.example.com. In each record, you specify the IP address of the web server, for example, 192.0.2.44.

When someone opens a web browser and enters example.com or www.example.com, the browser gets the IP address for your web server from the corresponding Route 53 record. The browser then gets your website content from your web server at 192.0.2.44.



### A record type

You use an A record to route traffic to a resource, such as a web server, using an IPv4 address in dotted decimal notation.


### AAAA record type

You use an AAAA record to route traffic to a resource, such as a web server, using an IPv6 address in colon-separated hexadecimal format.


### NS record type

An NS record identifies the name servers for the hosted zone. Note the following:
The most common use for an NS record is to control how internet traffic is routed for a domain. 
To use the records in a hosted zone to route traffic for a domain, you update the domain registration settings to use 
the four name servers in the default NS record. 
(This is the NS record that has the same name as the hosted zone.)
You can create a separate hosted zone for a subdomain (acme.example.com) and use that hosted zone to route internet 
traffic for the subdomain and its subdomains (subdomain.acme.example.com). 
You set up this configuration, known as "delegating responsibility for a subdomain to a hosted zone" by creating 
another NS record in the hosted zone for the root domain (example.com). 
For more information, see Routing traffic for subdomains.
You also use NS records to configure white-label name servers. For more information, see Configuring white-label name servers.


## CAA record type

A CAA record specifies which certificate authorities (CAs) are allowed to issue certificates for a domain or subdomain. 
Creating a CAA record helps to prevent the wrong CAs from issuing certificates for your domains. 
A CAA record isn't a substitute for the security requirements that are specified by your certificate authority, 
such as the requirement to validate that you're the owner of a domain.

You can use CAA records to specify the following:

Which certificate authorities (CAs) can issue SSL/TLS certificates, if any

The email address or URL to contact when a CA issues a certificate for the domain or subdomain


### CNAME record type

A CNAME record maps DNS queries for the name of the current record, such as acme.example.com, to another domain (example.com or example.net) 
or subdomain (acme.example.com or zenith.example.org).

### SOA record type

A start of authority (SOA) record provides information about a domain and the corresponding Amazon Route 53 hosted zone. 
For information about the fields in an SOA record, see NS and SOA records that Amazon Route 53 creates for a public hosted zone.


### DS record type

A delegation signer (DS) record refers a zone key for a delegated subdomain zone. 
You might create a DS record when you establish a chain of trust when you configure DNSSEC signing. 
For more information about configuring DNSSEC in Route 53, see Configuring DNSSEC signing in Amazon Route 53.

The first three values are decimal numbers representing the key tag, algorithm, and digest type. 
The fourth value is the digest of the zone key. For more information about the DS record format, see RFC 4034.


### MX record type

An MX record specifies the names of your mail servers and, if you have two or more mail servers, the priority order. 
Each value for an MX record contains two values, priority and domain name.

### NAPTR record type

A Name Authority Pointer (NAPTR) is a type of record that is used by Dynamic Delegation Discovery System (DDDS) applications to convert one value to another or to replace one value with another. 
For example, one common use is to convert phone numbers into SIP URIs.


### PTR record type

A PTR record maps an IP address to the corresponding domain name.



### SPF record type

SPF records were formerly used to verify the identity of the sender of email messages. 
However, we no longer recommend that you create records for which the record type is SPF. 
RFC 7208, Sender Policy Framework (SPF) for Authorizing Use of Domains in Email, Version 1, 
has been updated to say, "...[I]ts existence and mechanism defined in [RFC4408] have led to some interoperability issues. 
Accordingly, its use is no longer appropriate for SPF version 1;
implementations are not to use it." In RFC 7208, see section 14.1, The SPF DNS Record Type

### SRV record type

An SRV record Value element consists of four space-separated values. The first three values are decimal numbers representing priority, 
weight, and port. The fourth value is a domain name. SRV records are used for accessing services, 
such as a service for email or communications. For information about SRV record format, 
refer to the documentation for the service that you want to connect to.

### TXT record type

A TXT record contains one or more strings that are enclosed in double quotation marks ("). 
When you use the simple routing policy, include all values for a domain (example.com) or subdomain (www.example.com) in the same TXT record.


