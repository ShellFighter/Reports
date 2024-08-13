# Sensitive Information Exposure in JSON Response in Titan MFT WebUI Component

## Version

Titan MFT Server version 2.0.25.2426 contains a critical vulnerability where sensitive information, including passwords, is exposed in clear text within the JSON response when configuring SMTP settings via the Titan MFT Web UI.

This vulnerability poses a significant security risk, as an attacker or insider with access to the API could intercept this sensitive information, even in a local environment. The exposed credentials could be easily exploited, potentially leading to unauthorized access.

Moreover, if an administrator's credentials are compromised through phishing or social engineering, this vulnerability could be leveraged by a threat actor to facilitate lateral movement within the victim's network, leading to further compromise and escalation.


## Description


## Detail
