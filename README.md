# VM Onboarding and Isolation

This project demonstrates how virtual machines (VMs) can be integrated into a security monitoring environment such as Microsoft Defender for Endpoint and isolated in response to detected threats. It is designed to showcase incident response capabilities using modern endpoint protection tools.

## Objective

This demonstration focuses on two core operational capabilities:
- Integrating a virtual machine into a centralized security monitoring solution.
- Isolating a VM to contain and mitigate threats during an incident.

## Tools Used

- **Microsoft Azure / AWS / Other** (as applicable)
- **Microsoft Defender for Endpoint / Microsoft Sentinel**
- **Any additional relevant platforms or utilities**

## Onboarding Overview

To establish visibility into the target system, the virtual machine `io-test-vm` will be onboarded into Microsoft Defender for Endpoint (MDE). This process involves navigating to the **onboarding section** within MDE and selecting the appropriate deployment method based on the VM's operating system.

   <p align="center">
     <img src="https://github.com/user-attachments/assets/d7df4784-4fa9-4840-8430-36f7aa6dd970" alt="Onboarding page in MDE" width="500"/>
   </p>

**Note:** The virtual machine `io-test-vm` is used as the testing endpoint in this demonstration.  

   <p align="center">
     <img src="https://github.com/user-attachments/assets/be2be258-ef1f-4dbf-b9ee-ae936e77de46" alt="Onboarding page in MDE" width="450"/>
   </p>

Onboarding scripts may not be immediately visible due to permission settings. Select the package that matches the endpoint's OS, then execute the script on the VM. A confirmation prompt will appear, and onboarding completes upon successful execution.

   <p align="center">
     <img src="https://github.com/user-attachments/assets/c5527fec-1f33-4fc0-8342-975498fd3178" alt="Onboarding package download" width="750"/>
   </p>

Upon successful execution, a confirmation message indicates that the device has been integrated with the security platform

   <p align="center">
     <img src="https://github.com/user-attachments/assets/b6ce51c3-6810-40d4-b7be-65263418294d" alt="Successful onboarding confirmation" width="700"/>
   </p>
   
The device should appear in the MDE **Device Inventory** dashboard within a few minutes. Its status will be updated to **Onboarded** once visibility is established.

   <p align="center">
     <img src="https://github.com/user-attachments/assets/e31ef336-d78f-4a9d-8b45-fb5499f5fad6" alt="Device onboarded in MDE" width="1100"/>
     <img src="https://github.com/user-attachments/assets/35884a2f-e75e-4a2e-a919-bc851deec44f" alt="Device inventory status" width="300"/>
   </p>

## Isolation Demonstration

When suspicious activity is observed or an incident is detected, isolating the affected device can prevent further spread and reduce potential impact. Prior to isolation, the system's responsiveness is verified via a `ping` test using its public IP address.

   <p align="center">
     <img src="https://github.com/user-attachments/assets/e6046ecf-07d9-49cc-8479-d70f425febdb" alt="Ping test - device responsive" width="400"/>
   </p>

Isolation is initiated by accessing the device details within MDE. From the context menu, the **Isolate Device** option is selected, and a reason for the action is provided. This triggers immediate device isolation.

   <p align="center">
      <img src="https://github.com/user-attachments/assets/a0986736-97d1-437d-9958-39c5d89577cd" alt="Isolate device option" width="450"/>
     <img src="https://github.com/user-attachments/assets/aa5530ed-fd12-4cf2-8dcc-084fbfa3fa35" alt="Isolate device action" width="500"/>
     <img src="https://github.com/user-attachments/assets/a61324b2-e66c-4221-9dbd-736db31b1721" alt="Device isolation initiated" width="450"/>
   </p>

The isolation status is reflected in the **Action Center**, and follow-up network tests confirm that the device is no longer responsive.

   <p align="center">
     <img src="https://github.com/user-attachments/assets/ab3a80bc-d27d-4bc2-9be7-09f0337908c0" alt="Ping test - device isolated" width="400"/>
   </p>

Once isolated, the device is inaccessible until manually released. MDE will display the updated status accordingly.

   <p align="center">
     <img src="https://github.com/user-attachments/assets/2f9ba00e-82fe-4a4a-ba69-db97e8f106f8" alt="Device isolated status" width="400"/>
   </p>

If the threat is mitigated or determined to be benign, the device can be released from isolation through the **More Actions** menu within the device's page.

   <p align="center">
     <img src="https://github.com/user-attachments/assets/a89319c0-1800-4957-a5c5-9acfb7070ff7" alt="Release from isolation option" width="425"/>
     <img src="https://github.com/user-attachments/assets/844494d3-095f-4a7c-91e3-67e2f4c3b858" alt="Release from isolation action" width="450"/>
     <img src="https://github.com/user-attachments/assets/da9aeb25-0ed3-466c-ad15-aca27b027711" alt="Release from isolation confirmation" width="450"/>
   </p>

## Conclusion

This walkthrough demonstrates how virtual machines can be successfully onboarded into Microsoft Defender for Endpoint and isolated when needed as part of a responsive security operations workflow. These practices enhance visibility, enable containment, and support a proactive approach to incident response within enterprise environments.

---

**Author:** Gabriel Espinoza   
