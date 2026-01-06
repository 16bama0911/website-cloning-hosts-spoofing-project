# Website Cloning and Hosts File Spoofing Project
### Overview
This project demonstates how website cloning combined with local DNS manipulation can be used to simulate phishing and social engineering attacks in a controlled lab enviroment. The lab focuses on understanding attacker techniques and documenting defensive detection and mitigation opportunities.

All activity was performed in isloated virtual machines for educational and defensive analysis purposes. All websites used in this lab were created and hosted by the author solely for educational purposes.


### Lab Objectives
-  Clone a test website for offline hosting
-  Modify cloned content to simulate malicious document delivery
-  Redirect domain traffic using the Window hosts file
-  Test spoofed domain access from a client system
-  Analyze defensive detection and mitigation strategies

### Enviroment
#### Component|Details
- Hypervisor|VMware Workstation
- ClientVM|Windows(hosts file modification & user access)
- ServerVM|Ubuntu Linux (web hosting)
- Tools|HTTrack, Python HTTP server
- Network|Host-only/NAT (isolated lab)

### Attack Simulation Workflow
#### 1. Test Website Creation & Cloning
- Created a temporary, publicy accessible test website specifically for this lab
- Used HTTrack to clone the site to simulate how attackers mirror legitamate web content
- Preserved directory structure and internal links for realism
- No real organization or production websites were used

<img width="1280" height="800" alt="02_modified_site_content" src="https://github.com/user-attachments/assets/92cbdbae-acbe-477c-b89c-18a26c84513a" />

### 2. Local Web Server Hosting
- Hosted the cloned website on the Ubuntu server using a lightweight Python HTTP server:
    #### python3 -m http.server 8000
  
- Verified the service was actively listening on all interfaces using:
    #### ss -tuln

<img width="1280" height="263" alt="01_server_listening_port_8000" src="https://github.com/user-attachments/assets/0afa82b0-d81b-4c18-945c-9bdb61d9ea9b" />

### 3. Hosts File Modification (Local DNS Spoofing)
- Edited the Windows hosts file to override DNS resolution and redirect a lab domain to the Ubuntu server:
    #### <server_ip> training-portal.local
- Applied changes by flushing the local DNS cache

<img width="1024" height="687" alt="03_hosts_file_spoofing" src="https://github.com/user-attachments/assets/18cabe88-6d5d-4972-ac0b-1b7afd53b54d" />

### 4. DNS Resolution Verification
- Confirmed spoofed domain resolution prior to browser access
- Validated that the domain resolved to the internal server IP using ICMP

<img width="1024" height="684" alt="04_dns_resolution_verified" src="https://github.com/user-attachments/assets/4c74df56-f335-448a-9383-0c68fe979b41" />





