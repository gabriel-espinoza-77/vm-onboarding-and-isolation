# VM Onboarding and Isolation

This project demonstrates the process of onboarding virtual machines (VMs) into a security monitoring environment and isolating them in response to detected threats.  

It's designed for cybersecurity professionals seeking to understand and practice these critical incident response and security operations tasks.

## Objective
To document and demonstrate the following processes:
- Onboarding a VM into a security monitoring environment.
- Isolating a VM to contain and mitigate potential threats.

## Tools Used
- **Microsoft Azure / AWS / Other** (as applicable)
- **Microsoft Defender for Endpoint / Sentinel** (if applicable)
- **PowerShell / Bash** (for automation)
- **Any other relevant tool or service**

## Onboarding Steps
1. Log into Microsoft Defender and Navigate to the Onboarding page in the Settings dashboard

Note: The VM `io-test-vm` was used for this demonstration
<p align="center">
  <img src="https://github.com/user-attachments/assets/be2be258-ef1f-4dbf-b9ee-ae936e77de46" alt="Screenshot description" width="600"/>
</p>

2. An Onboarding package will be available here and within the device you are trying to onboard, you download and install the MDE package

<p align="center">
  <img src="https://github.com/user-attachments/assets/c5527fec-1f33-4fc0-8342-975498fd3178" alt="Screenshot description" width="600"/>
</p>

3. Message like this should pop up

<p align="center">
  <img src="https://github.com/user-attachments/assets/b6ce51c3-6810-40d4-b7be-65263418294d" alt="Screenshot description" width="600"/>
</p>

4.  You have now successfully onboarded the device, check back on MDE to confirm the device is onboarded (it takes within 5-10 minutes for the device to show)

Note: the Device Inventory dashboard shows devices with the most recent activity and as you can see the `io-test-vm` device was successfully onboarded with the status being `Onboarded`

<p align="center">
  <img src="https://github.com/user-attachments/assets/e31ef336-d78f-4a9d-8b45-fb5499f5fad6" alt="Screenshot description" width="600"/>
  <img src="https://github.com/user-attachments/assets/35884a2f-e75e-4a2e-a919-bc851deec44f" alt="Screenshot description" width="600"/>
</p>

## VM Isolation Process
1. Clearly outline the trigger for isolation (e.g., suspicious activity, incident alert).
2. Step-by-step isolation commands or configurations.
3. Notes on what changed in the environment post-isolation.

## Key Commands
```bash
# Example PowerShell or Bash commands
Get-MpComputerStatus
Set-MpPreference -DisableRealtimeMonitoring $true
az vm update --name <vm-name> --resource-group <rg> --set properties.networkProfile.networkInterfaces[0].id=null
```

## Findings / Lessons Learned
- Summarize what worked well.
- Highlight any challenges or limitations you encountered.
- Reflect on what you would do differently in a real-world scenario.

## Conclusion
A brief summary of what the project demonstrates and any next steps or future improvements you plan to make.

---

**Author:** [Your Name]  
**Contact:** [Your GitHub / LinkedIn link]  
**License:** [e.g., MIT License]
