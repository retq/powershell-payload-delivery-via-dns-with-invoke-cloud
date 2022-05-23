### Deliver a PS empire payload using DNS and see how the sys reacts

![image](https://2603957456-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-LFEMnER3fywgFHoroYn%2F-LOyJgZtOsGBwoIRdjbW%2F-LOyPPPiK48hITH_0AcE%2Fempire-stager-via-dns.gif?alt=media&token=e90b0f6c-69ff-416a-a104-d0a9955a50c6)

- **host "suddenly" bursted "many" DNS TXT requests to one domain
- **DNS queries follow the naming convention of 1, 2, 3, ..., N
- **majority of DNS answers contain TXT Lenght of 255 (trivial to change/randomize)
- **DNS answers are all TTL = 120 (trivial to change/randomize)
- **TXT data in DNS answer has no white spaces (easy to change)
- **host suddenly/in a short span of time spawned "many" nslookup processes
- **has the endpoint changed once the DNS lookups stopped? i.e new processes spawned?**

![image](https://user-images.githubusercontent.com/73394656/169733003-5fcd6fc7-cb83-4306-a66e-a16dd1139f75.png)

Spike a ``nslookup``

![image](https://user-images.githubusercontent.com/73394656/169733017-eca6b28a-31f9-4066-948f-34d5bf0ae2bc.png)
