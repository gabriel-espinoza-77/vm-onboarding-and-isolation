# VM Onboarding and Isolation

This project demonstrates the process of onboarding virtual machines (VMs) into a security monitoring environment and isolating them in response to detected threats.  
It’s designed for cybersecurity professionals seeking to understand and practice these essential incident response and security operations tasks.

## Objective
To document and demonstrate the following processes:
- Onboarding a VM into a security monitoring environment.
- Isolating a VM to contain and mitigate potential threats.

## Tools Used
- **Microsoft Azure / AWS / Other** (as applicable)
- **Microsoft Defender for Endpoint / Sentinel** (if applicable)
- **Any other relevant tool or service**

## Onboarding Steps

**The following steps outline the process for onboarding a virtual machine (VM) into a security monitoring environment using Microsoft Defender for Endpoint. This ensures the device is properly integrated and visible within the security platform.**

1. Access the **Microsoft Defender for Endpoint (MDE)** portal and navigate to the **Onboarding** page within the **Settings** dashboard.

   <p align="center">
     <img src="https://github.com/user-attachments/assets/d7df4784-4fa9-4840-8430-36f7aa6dd970" alt="Onboarding page in MDE" width="500"/>
   </p>

   **Note:** The virtual machine (VM) `io-test-vm` is used as an example in this demonstration.  
   <p align="center">
     <img src="https://github.com/user-attachments/assets/be2be258-ef1f-4dbf-b9ee-ae936e77de46" alt="Onboarding page in MDE" width="450"/>
   </p>

2. On the onboarding page, several onboarding packages are available for download, each corresponding to the appropriate operating system.  

   **Note:** Due to limited administrative privileges, these packages are not displayed in this example.

3. Select the onboarding package suitable for the target device. Once the onboarding script is executed, the program will prompt for confirmation. Type and enter `Y` to proceed with the onboarding process.
  
   <p align="center">
     <img src="https://github.com/user-attachments/assets/c5527fec-1f33-4fc0-8342-975498fd3178" alt="Onboarding package download" width="750"/>
   </p>

4. After successfully executing the onboarding script, a confirmation message similar to the one below should appear:  
   <p align="center">
     <img src="https://github.com/user-attachments/assets/b6ce51c3-6810-40d4-b7be-65263418294d" alt="Successful onboarding confirmation" width="700"/>
   </p>

5. Once the onboarding process is complete, verify the device’s status within the MDE portal. It typically takes between 5–10 minutes for the device to appear.

   **Note:** The **Device Inventory** dashboard displays devices with the most recent activity. In this demonstration, the `io-test-vm` device appears with the status **Onboarded**.  
   <p align="center">
     <img src="https://github.com/user-attachments/assets/e31ef336-d78f-4a9d-8b45-fb5499f5fad6" alt="Device onboarded in MDE" width="1100"/>
     <img src="https://github.com/user-attachments/assets/35884a2f-e75e-4a2e-a919-bc851deec44f" alt="Device inventory status" width="300"/>
   </p>

## VM Isolation Process

**The steps below demonstrate how to isolate a device within Microsoft Defender for Endpoint. This action is essential for containing threats and preventing lateral movement during a security incident.**

1. To verify that the device is active and responsive, use the `ping` command in the command prompt along with the device’s public IP address.

   **Note:** At this stage, the device should respond to ping requests.  
   <p align="center">
     <img src="https://github.com/user-attachments/assets/e6046ecf-07d9-49cc-8479-d70f425febdb" alt="Ping test - device responsive" width="400"/>
   </p>

2. In the MDE portal, navigate to the **Devices** section and select the target device to isolate (in this demonstration, `io-test-vm`) .

3. In the upper-right corner of the device page, click the three-dot menu (`...`) and select **Isolate Device**. Provide a brief comment explaining the reason for isolating the device, then click Confirm to proceed.  
   <p align="center">
      <img src="https://github.com/user-attachments/assets/a0986736-97d1-437d-9958-39c5d89577cd" alt="Isolate device option" width="450"/>
     <img src="https://github.com/user-attachments/assets/aa5530ed-fd12-4cf2-8dcc-084fbfa3fa35" alt="Isolate device action" width="500"/>
     <img src="https://github.com/user-attachments/assets/a61324b2-e66c-4221-9dbd-736db31b1721" alt="Device isolation initiated" width="450"/>
   </p>

   **Note:** The Action Center pop-up will display the current status of the device isolation

4. After isolation is initiated, attempt to ping the device again. The device should no longer respond to ping requests, confirming that isolation has been successfully enforced.  
   <p align="center">
     <img src="https://github.com/user-attachments/assets/ab3a80bc-d27d-4bc2-9be7-09f0337908c0" alt="Ping test - device isolated" width="400"/>
   </p>

   **Reminder:** Once a device is isolated, no users can access it.

5. The device page in MDE will display a clear indication that the device is now **Isolated**.  
   <p align="center">
     <img src="https://github.com/user-attachments/assets/2f9ba00e-82fe-4a4a-ba69-db97e8f106f8" alt="Device isolated status" width="400"/>
   </p>

6. To release the device from isolation, return to the device page, click the three-dot menu (`...`), and select **Release from Isolation** under the **More Actions** section.  
   <p align="center">
     <img src="https://github.com/user-attachments/assets/a89319c0-1800-4957-a5c5-9acfb7070ff7" alt="Release from isolation option" width="425"/>
     <img src="https://github.com/user-attachments/assets/844494d3-095f-4a7c-91e3-67e2f4c3b858" alt="Release from isolation action" width="450"/>
     <img src="https://github.com/user-attachments/assets/da9aeb25-0ed3-466c-ad15-aca27b027711" alt="Release from isolation confirmation" width="450"/>
   </p>

   **Note:** The Action Center pop-up will display the status of the release process.


## Conclusion
This project successfully demonstrates the onboarding and isolation of virtual machines within Microsoft Defender for Endpoint. By following these documented steps, cybersecurity professionals can ensure that devices are properly integrated into their security monitoring environment and can be swiftly isolated to contain potential threats. These processes form a fundamental part of effective incident response and security operations workflows.

---

**Author:** Gabriel Espinoza   
