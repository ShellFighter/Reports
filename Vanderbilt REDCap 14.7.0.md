
# Sensitive Information Exposure in JSON Response in Titan MFT WebUI Component

## Version

Titan MFT Server version 2.0.25.2426 

## Description

Vanderbilt REDCap 14.7.0 contains a vulnerability in the project creation function that allows attackers to log out authenticated users via a Cross-Site Request Forgery (CSRF) attack. By tricking a user into clicking a crafted malicious link, an attacker can force the user to be logged out, disrupting their session. This vulnerability is due to the lack of CSRF protection on the logout request, allowing unauthorized actions to be performed on behalf of the user.


## Steps to Reproduce

- Log in to the application as a normal user.
- Navigate to the project creation page:
- Go to https://redcapdemo.vumc.org/index.php?action=myprojects.
- Create a new project by clicking on + New Project.
- Inject the malicious hyperlink:
For the project title, enter the following HTML code that creates a clickable hyperlink. When clicked, this link will log the user out of the application and redirect them to a specific page:
<a href="https://redcapdemo.vumc.org/index.php?action=myprojects&logout=1">HELP Please</a>
- Assign the victim to the project:
- Visit the User Rights and Permissions feature and add the victim to this specific project.
- Victim receives access notification:
- The victim will receive an email informing them that they have been granted access to the REDCap project.
- If the victim clicks on the "HELP Please" link in the project title, they will be logged out of the application.


## Environment of testing:

- Deployment Model: On-Premises

- Operating System : Windows 11

- Software (https://redcapdemo.vumc.org/)

## PoC


