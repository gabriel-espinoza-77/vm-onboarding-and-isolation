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
- **Any other relevant tool or service**

## Onboarding Steps
1. Log into the MDE Portal and Navigate to the Onboarding page in the Settings dashboard

Note: The VM `io-test-vm` was used for this demonstration
<p align="center">
  <img src="https://github.com/user-attachments/assets/be2be258-ef1f-4dbf-b9ee-ae936e77de46" alt="Screenshot description" width="600"/>
</p>

2. An Onboarding package will be available here and within the device you are trying to onboard, you download and install the MDE package

Reminder: There are different onboarding package options, it just depends what operating system you are trying to onboard.

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

1. First to test that the device is activtely working, open command prompt and use `ping` command to conenct to the device

Note: The device is responding to the ping

<p align="center">
  <img src="https://github.com/user-attachments/assets/e6046ecf-07d9-49cc-8479-d70f425febdb" alt="Screenshot description" width="600"/>
</p>

2. Next, using the same device log into the MDE Portal
3. Browse to devices and select the device, in my case its `io-test-vm`
4. in the upper right corner, click the 3 dots and then press isolate device

<p align="center">
  <img src="https://github.com/user-attachments/assets/a0986736-97d1-437d-9958-39c5d89577cd" alt="Screenshot description" width="600"/>
</p>



<p align="center">
  <img src="https://github.com/user-attachments/assets/aa5530ed-fd12-4cf2-8dcc-084fbfa3fa35" alt="Screenshot description" width="600"/>
  <img src="https://github.com/user-attachments/assets/a61324b2-e66c-4221-9dbd-736db31b1721" alt="Screenshot description" width="600"/>
</p>

4. Try and ping again and youll see youll not be able to connect to the device

<p align="center">
  <img src="https://github.com/user-attachments/assets/ab3a80bc-d27d-4bc2-9be7-09f0337908c0" alt="Screenshot description" width="600"/>
</p>

Reminder: Once the device has been isolated, no users can use the device

5. If you go on the device page, you can see that there is text saying the device has been "isolated"

<p align="center">
  <img src="https://github.com/user-attachments/assets/2f9ba00e-82fe-4a4a-ba69-db97e8f106f8" alt="Screenshot description" width="600"/>
</p>

6. If you want to release the device from isolation, go to the device page again, you click the 3 dots again and in the "more actions" options you'll see "Release From Isolation" 

<p align="center">
  <img src="https://github.com/user-attachments/assets/a89319c0-1800-4957-a5c5-9acfb7070ff7" alt="Screenshot description" width="600"/>
  <img src="https://github.com/user-attachments/assets/844494d3-095f-4a7c-91e3-67e2f4c3b858" alt="Screenshot description" width="600"/>
  <img src="https://github.com/user-attachments/assets/da9aeb25-0ed3-466c-ad15-aca27b027711" alt="Screenshot description" width="600"/>
</p>


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
