# Home-Lab-Work-In-Progress

My goal with this project is to establish an at home SOC environment that I could explore and mess with to learn. So far I have been able to 
successfully set up the Wazuh agent on my Windows 11 desktop and manager on an Ubuntu VM, as well as configure some tools in the sofware.

========================= COMPLETED CAPABILITIES =========================

- File Integrity Monitoring
    - Learned how to set up FIM between the manager and agent. I was able to see when I created, deleted, modified, and moved a file. I was able to see when time it happened as well, which is super important. 
     So far my biggest issue is storage. If I configure FIM to monitor every event on the computer, it eats through any storage I have incredible fast. Fortunately, I can fix this by only monitoring certain directories, but I left it on one day by accident and all o fmy storage was gone.
         
- Security Events
    - This allowed me to see all kinds of events through my Ubuntu VM, such as failed and successful login attempts. I was able to see all the information about the login, including agent and data name, IP, GeoLocation, etc. Upon further research, if I have a public facing machine (the VM is not), 
      there will be a lot of brute force login attemps, mainly from Russia.

- Malware Detection
    - I learned that I can set up malware detection by building upon FIM. What I did was integrate VirusTotal with FIM. First, I had to get an API key from VirusTotal, so when FIM sees that a file has changed, it passes the hash to the VirusTotal API to check for malware.
      
- Active Response
    - I learned that if malware is detected, the file can be automatically deleted or isolated using active response using a script. There is a lot more I can do for this, such as actively scan endpoints for rootkits, but so far this is what I have.
