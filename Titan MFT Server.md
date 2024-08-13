# Sensitive Information Exposure in JSON Response in Titan MFT WebUI Component

## Version

Titan MFT Server version 2.0.25.2426 

## Description

Titan MFT Server version 2.0.25.2426 contains a critical vulnerability where sensitive information, including passwords, is exposed in clear text within the JSON response when configuring SMTP settings via the Titan MFT Web UI.

This vulnerability poses a significant security risk, as an attacker or insider with access to the API could intercept this sensitive information, even in a local environment. The exposed credentials could be easily exploited, potentially leading to unauthorized access.

Moreover, if an administrator's credentials are compromised through phishing or social engineering, this vulnerability could be leveraged by a threat actor to facilitate lateral movement within the victim's network, leading to further compromise and escalation.

## Steps to Reproduce

- Log in to the application as an admin.

- Intercept the traffic using a tool such as Burp Suite or the web dev for Firefox

- Update the SMTP configuration.


- Observe the POST request containing plain text credentials

## Environment of testing:

- Deployment Model: On-Premises

- Operating System : Windows 11

- Software (https://srtcdnstorage.blob.core.windows.net/software/nextgen/titansftp/titansftp-win-x64.exe)

## PoC

In a POST request, the BasicEmailServerCreds parameter is reflected in the server's response, directly exposing the credentials of the SMTP server.

![POST request](https://github.com/user-attachments/assets/1e54961b-0fb0-48a6-83b7-c890ca79ff5d)

The configuration can be performed in the Web UI as follows:


![Titan MFT web UI](https://github.com/user-attachments/assets/601fb49f-ff41-4177-af6f-3a4e7f8a3529)


<img width="1250" alt="titanSMTP" src="https://github.com/user-attachments/assets/f6569208-052a-4fca-866c-803a68bc622e">
