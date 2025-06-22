# Tenable-Nessus scanning VM

Hey everyone!

Today, I’ll be walking you through how to scan your environment using Tenable Nessus Essentials (Free Version). Nessus is a powerful vulnerability scanner widely used by cybersecurity professionals to assess systems for known vulnerabilities, misconfigurations, and compliance issues. I will be using Windows 11 VM.


# Step 1: Set up your target VM

 1. When setting up your virtual machine, make sure to configure the network adapter to "Host-Only Adapter." This ensures the VM receives a private IP address that is accessible only from your host machine, allowing Nessus to communicate with and scan the VM effectively within a secure, isolated environment.

 2.  Once your VM is up and running, it's recommended to temporarily disable the Windows Firewall during scanning. This allows Nessus to successfully ping and communicate with the target VM, ensuring accurate and complete vulnerability scan results.

 
 ![Alt Text](https://github.com/JamahdPerry99/Tenable-Nessus/blob/ec75eeb206bb2bcf784706418ed09b5c169f7b6a/Windows%20firewall%20disabled.png)
 
 
 3.  After disabling the firewall, open the Command Prompt on the VM and run "ipconfig" to retrieve the IP address. You'll need this IP to configure your Nessus scan target.




# Step 2: Download and Install Nessus

1. Navigate to https://www.tenable.com/products/nessus/nessus-essentials and follow the step-by-step instructions to download Nessus Essentials. Be sure to register with a valid email to receive your free activation code.

2. Once the installation is complete, open your browser and navigate to https://localhost:8834. During the account setup, you'll be prompted to enter the activation code that was sent to your email. After logging in, allow a few minutes for Nessus to download and update its plugins—this is important for accurate and up-to-date scanning.


# Step 3: Create and run a discovery scan

1. We'll begin by performing a discovery scan, which is designed to identify active hosts and detect open ports on the network. To initiate this, click on “New Scan” located in the top right-hand corner of the Nessus interface.

2. Next, select the “Host Discovery” scan template to begin identifying live hosts and gathering basic network information.


![Alt Text](https://github.com/JamahdPerry99/Tenable-Nessus/blob/a3b285cbc36a222ff0a96252e69db48ff70ec1b2/Host%20discovery%20scan.png)


3. Now, enter the scan configuration details, including the Name, Description, and Target, which should be the IP address of the VM you intend to scan. Additionally, you have the option to schedule the scan to run at specific times and configure notifications to alert designated recipients once the scan is complete.


![Alt Text](https://github.com/JamahdPerry99/Tenable-Nessus/blob/91b4715d8f2c14a7b847c575cc9571cc76d4888e/complete%20the%20Settings%20for%20the%20host%20discovery%20scan.png)


4. Once you've saved the scan settings, you'll be redirected to the main dashboard. From there, simply locate your newly created scan and click “Launch” to start the scan.

5. Once the scan is complete, a checkmark will appear next to it, indicating successful execution. Click on the scan to view the results, which will include the discovered live hosts and a list of their open ports.





# Step 4: Create and run a basic network scan

1. We'll start with a Basic Network Scan, which performs a comprehensive vulnerability assessment across the entire system—ideal for scanning any host. To begin, click on “New Scan” in the top-right corner of the Nessus interface.

2. Next, select the “Basic Network Scan” template to begin configuring the scan and collecting essential information about the target system.


![Alt Text](https://github.com/JamahdPerry99/Tenable-Nessus/blob/a3b285cbc36a222ff0a96252e69db48ff70ec1b2/Host%20discovery%20scan.png)


3. Just like in a Host Discovery Scan, you'll now configure the scan settings by entering key details such as the Name, Description, and the Target IP address, which should be the address of the VM you intend to scan. Nessus also allows you to schedule the scan to run at specific times and set up notifications to alert designated recipients once the scan is complete.

For a more in-depth analysis, you can enable credentialed scanning by adding valid user credentials (e.g., username and password). This allows Nessus to log into the system and perform a more comprehensive assessment, including checks that require authenticated access.


![Alt Text](https://github.com/JamahdPerry99/Tenable-Nessus/blob/12074f5c6cf5e917102a42e6634b19722def83b5/basic%20network%20scans.png)


4. After saving your scan settings, you’ll be redirected to the main dashboard. From there, simply click “Launch” to start your scan. Nessus will begin analyzing the target system based on the configuration you’ve defined.

5. Once the scan is complete, a green checkmark will appear next to the scan name, indicating it finished successfully. Click on the scan to view detailed results. You’ll see a list of identified vulnerabilities on the target system, categorized by severity.
To document your findings, you can generate a report by clicking “Report” in the top-right corner. Prioritize remediation starting with Critical vulnerabilities, followed by High, Medium, and then Low severity issues.


![Alt Text](https://github.com/JamahdPerry99/Tenable-Nessus/blob/8ca2e5c15da55a83070088ebaf774a9517eb9f2f/Vulnerability%20scan%20results.png)




