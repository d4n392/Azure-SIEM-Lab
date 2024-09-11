# Azure-SIEM-Lab


In this home business lab I built my own SOC and configured Microsoft Sentinel SIEM. This SIEM acts as the central hub for monitoring all my connected devices. The following is the step-by-step process I used to monitor remote logins via RDP port 3389 on my Azure Windows vm.

### SIEM setup
I begin by spinning up a Windows vm in Microsoft Azure. I enabled native RDP over port 3389 to observe some local remote login traffic, afterwards I installed Microsoft Sentinel. Set configurations to monitor remote login attempts specifically over RDP port 3389.

![Screenshot 2024-09-10 222313](https://github.com/user-attachments/assets/3c4ee468-e911-45aa-acfc-f17f50c9374c)

![Screenshot 2024-09-10 224025](https://github.com/user-attachments/assets/ac68ed35-82cc-475a-b166-d67bb98b7c2b)

![Screenshot 2024-09-10 224058](https://github.com/user-attachments/assets/bc30b90a-fc7d-4ad7-bbc6-55c5535dc43e)


![image](https://github.com/user-attachments/assets/9d0d22a0-410c-4709-af62-67f83ff36def)

### I added Log Analytics to my workspace

![Screenshot 2024-09-10 222437](https://github.com/user-attachments/assets/2536ef4c-765a-42a1-948a-d8fbaa9979b0)

### I Installed Azure Monitor Agent (AMA) Data Connector to pull all event logs from the vm endpoint to our Microsoft Sentinel SIEM.
_Over 40,000 recorded in two days_


![image](https://github.com/user-attachments/assets/b1e502e5-f9a3-4d85-9163-bddfc0181dec)

### I created a Data Collection Rule inside Sentinel that checks for successful sign-ins via RDP every 5 minutes, whilst filtering out our own system logins:

_**where** Activity **contains** "success" **and** Account **!contains** "system"_

![image](https://github.com/user-attachments/assets/d03a23d3-b2c4-495b-94bd-9505cfbfbd2d)

![image](https://github.com/user-attachments/assets/119f1976-46f5-45e3-be31-3b98db7a4e79)

### Initiating remote session over RDP.
I logged in remotely using RDP and watched for the incident alert.

![image](https://github.com/user-attachments/assets/19eadd19-4dda-40fe-b313-46e3c531b5a1)

![image](https://github.com/user-attachments/assets/21f4fb6e-e5bf-49a8-a362-e0ff6b5dc378)

![image](https://github.com/user-attachments/assets/57859550-5835-42a3-ac89-89a71f995662)

#### _Incident Alerts shown below are from the past 30 days_

![image](https://github.com/user-attachments/assets/f0d1b20d-b7b5-443a-aa74-db11e82c69be)

![image](https://github.com/user-attachments/assets/c1385de7-2014-491d-bba4-8827dfc223ce)

### Out of over 83K Event logs, our script detected 12 Incidents involving successful local sign ins over RDP.


















