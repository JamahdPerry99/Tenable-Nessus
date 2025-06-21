# Tenable-Nessus scanning VM

Hey everyone!

Today, I’ll be walking you through how to scan your environment using Tenable Nessus Essentials (Free Version). Nessus is a powerful vulnerability scanner widely used by cybersecurity professionals to assess systems for known vulnerabilities, misconfigurations, and compliance issues. I will be using windows 11 VM.


# Step 1: Set up your target VM

 1. When setting up your virtual machine, make sure to configure the network adapter to "Host-Only Adapter." This ensures the VM receives a private IP address that is accessible only from your host machine, allowing Nessus to communicate with and scan the VM effectively within a secure, isolated environment.

 2.  Once your VM is up and running, it's recommended to temporarily disable the Windows Firewall during scanning. This allows Nessus to successfully ping and communicate with the target VM, ensuring accurate and complete vulnerability scan results.

 
 ![Alt Text](https://github.com/JamahdPerry99/Tenable-Nessus/blob/ec75eeb206bb2bcf784706418ed09b5c169f7b6a/Windows%20firewall%20disabled.png)
 
 
 3.  After disabling the firewall, open the Command Prompt on the VM and run "ipconfig" to retrieve the IP address. You'll need this IP to configure your Nessus scan target.




# Step 2: Download and Install Nessus

1. Navigate to https://www.tenable.com/products/nessus/nessus-essentials and follow the step-by-step instructions to download Nessus Essentials. Be sure to register with a valid email to receive your free activation code.

2. Once the installation is complete, open your browser and navigate to https://localhost:8834. During the account setup, you'll be prompted to enter the activation code that was sent to your email. After logging in, allow a few minutes for Nessus to download and update its plugins—this is important for accurate and up-to-date scanning.


# Step 3: Create and run a scan
