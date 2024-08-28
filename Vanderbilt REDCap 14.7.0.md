
# CSRF Vulnerability in Project Title of Vanderbilt REDCap 14.7.0 Allows Unauthorized Logout of Users

## Version

REDCap 14.7.0 

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

- Deployment Model: Demo ( 1- week trial https://redcapdemo.vumc.org/index.php)

- Operating System : Windows 11

- Software (https://redcapdemo.vumc.org/)

## PoC

![image](https://github.com/user-attachments/assets/d0ff44cb-b836-4aa3-8678-db6b33f747b1)


![image](https://github.com/user-attachments/assets/f9ffda10-e21f-4fd7-8238-79484ced4869)
assiging the user to the project

![image](https://github.com/user-attachments/assets/29220e6d-92ac-4d53-aad5-1e6ac034f759)

![image](https://github.com/user-attachments/assets/4a7952de-fd7b-4d33-a863-d96b6915e240)

![image](https://github.com/user-attachments/assets/fd7beba0-6bd1-4f48-8a13-62650d60ec0a)

victim gets logged out
