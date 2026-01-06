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
