# SplunkUBAThreatFeedsviaGist

## Summary 

Splunk UBA denies and allows by default.

1. Denied domains: 
- Splunk UBA includes a list of high-confidence entries from the Collective Intelligence Framework (CIF). New entries are periodically added to the list in new versions of Splunk UBA.
2. Denied IP addresses:
-	Splunk UBA does not include a default set of denied IP addresses.
3. Allowed domains
- Splunk UBA selects allowed domains from the top 250,000 global website domain names according to Alexa.
4. Allowed IP addresses
- Splunk UBA selects allowed IP addresses from the top 50,000 global website IP addresses and ranges according to Alexa.
5. Allowed users
- Splunk UBA does not include a default set of allowed users. Add HR data to Splunk UBA before uploading a list of allowed users.

Add a domain or IP address to a deny list to generate anomalies whenever a user or device interacts with that domain or IP address.

- Interaction with a denied domain generates a Blacklisted Domain anomaly.
- Interaction with a denied IP generates a Blacklisted IP Address anomaly.

Reference: https://docs.splunk.com/Documentation/UBA/5.0.5.1/GetDataIn/ConfigureAllowDenyLists

### Instructions on how to add new entries to a deny list with gist
** These instructions are used for demo purposes only and uses a public gist. Tested and validated in Splunk UBA 5.0.5.1 version. 

1. Create a Gist: Github -> Navigate to gist home page -> Create a public gist 
2. Create two files: 
- ip_blacklist.txt
- domain_blacklist.txt
3. Set up the Splunk UBA Connector: 
Manage -> Data Sources -> New Data Source -> UBA Threat Feed
4. Configure the following: 
- Name
- URL
- Schedule 
5. For the name, configure the raw gist URL. In this example, I used: https://gist.githubusercontent.com/annettefo/af6776ddc5f2a36216eddcdb0302c04b/raw/5e20c738bfa1016c74dde5bccb7bcaf469d0c872
6. Click Next
7. Click OK 
8. Once it is done processing, the results will be available under Manage -> Black/White lists
7. <img width="1509" alt="Screen Shot 2022-03-03 at 12 10 52 PM" src="https://user-images.githubusercontent.com/20345440/156644916-62336fe8-7b66-4757-9dfd-2089530183c2.png">

For troubleshooting, refer to GetExternalFeeds.log
