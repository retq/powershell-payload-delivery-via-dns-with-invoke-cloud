# How is Invoke-PowerCloud different from PowerDNS?

### With PowerDNS, you will need :

- a dedicated linux box with a public IP where you can run PowerDNS, so it can act as a DNS server

- you also need multiple domain names to get the nameservers configured properly

### Cloudfare ? eh ?

- Take the powershell payload file and base64 encode it
- Divide the payload into chunks of 255 bytes
- Create a DNS zone file with DNS TXT records representing each chunk of the payload data retrieved from the previous step
- Send the generated DNS zone file to cloudflare using their APIs
- Generate two stagers for use with authoritative NS/non-authoritative NS
- Stager can then be executed on the victim system. The stager will recover the base64 chunks from the DNS TXT records and rebuild the original payload
- Stager executes the payload in memory!
