# Azure-SIEM-Lab

Azure SIEM Lab


To build my own Security Operations Center (SOC), I first deployed a Security Information and Event Management (SIEM) tool in my home business lab. This SIEM acts as the central hub for monitoring all my connected devices, such as laptops, servers, and IoT devices. Here's the step-by-step process:
### SIEM setup
I begin by selecting Microsoft Azure and spinning up a Windows vm. I enabled native RDP over port 3389 to observe some local remote login traffic. I then installed Microsoft Sentinel . I configure it to monitor remote login attempts specifically over RDP port 3389.

I added Log Analytics to my workspace

I Installed Azure Monitor Agent (AMA) Data Connector to pull logs from the vm endpoint to our Microsoft Sentinel SIEM.
Created a Data Collection Rule inside Sentinel that checks for successful sign-ins via RDP, whilst filtering out our own system logins:

_**where** Activity **contains** "success" **and** Account **!contains** "system"._

![Screenshot 2024-09-10 223147](https://github.com/user-attachments/assets/3c3f7a55-0bc0-41ca-b631-fe3ccf1a0033)

![Screenshot 2024-09-10 222313](https://github.com/user-attachments/assets/3c4ee468-e911-45aa-acfc-f17f50c9374c)

![Screenshot 2024-09-10 222437](https://github.com/user-attachments/assets/2536ef4c-765a-42a1-948a-d8fbaa9979b0)

![image](https://github.com/user-attachments/assets/9d0d22a0-410c-4709-af62-67f83ff36def)

![image](https://github.com/user-attachments/assets/21f4fb6e-e5bf-49a8-a362-e0ff6b5dc378)

![Screenshot 2024-09-10 222633](https://github.com/user-attachments/assets/42e676a5-6524-4a35-bd51-ee5075e4251b)

![Screenshot 2024-09-10 222747](https://github.com/user-attachments/assets/1d26a8c4-3473-4b44-a38a-94a47c9758bc)

![Screenshot 2024-09-10 222921](https://github.com/user-attachments/assets/685d5760-caf2-49d4-adc6-74666e27413d)

![Screenshot 2024-09-10 223238](https://github.com/user-attachments/assets/322e4663-4d47-4612-a7ab-c28a62d1d679)

![Screenshot 2024-09-10 223707](https://github.com/user-attachments/assets/74752d4f-1c9c-45bb-8634-18d3739b1495)

![image](https://github.com/user-attachments/assets/8e091e87-ed3f-4946-910e-5e25974e3fa7)

![Screenshot 2024-09-10 223902](https://github.com/user-attachments/assets/12302ef6-71b3-4926-96bd-500e655f0af5)

![Screenshot 2024-09-10 224025](https://github.com/user-attachments/assets/ac68ed35-82cc-475a-b166-d67bb98b7c2b)

![Screenshot 2024-09-10 224058](https://github.com/user-attachments/assets/bc30b90a-fc7d-4ad7-bbc6-55c5535dc43e)


![Screenshot 2024-09-10 230126](https://github.com/user-attachments/assets/2866d640-8403-45a7-b5e6-c6ea66fede05)




















