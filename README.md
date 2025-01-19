# Zphisher-RMIT-Cybersecurity-Project
One of the Red teaming activities from my [RMIT Cybersecurity Project](https://github.com/Kazu010101/RMIT-Cybersecurity-Project/blob/main/README.md)

## Objective

- Install Zphisher on Kali Linux
- Generate a phishing link using Zphisher 
- Deliver the phishing link to the victim in a personalized email
- Verify the successful attack

## The Scenario

During reconaisance phase, the attacker discovered email address on one of the XYZ Company's staff, including the victim's hobby of watching Netflix. With this information at hand, the attacker attampted to steal the staff's credential using email phishing. 

## Lab Setup

- Kali Linux VM with NAT Network Setting
- Personal email to send the phishing link

## Installing & Running Zphisher

**Installation:** enter the following commands on Kali Terminal:
- sudo git clone https://github.com/htr-tech/zphisher.git

**Running Zphisher:**
- cd zphisher
- sudo bash zphisher.sh > enter password 

![zphisher](https://github.com/user-attachments/assets/dc813246-edba-4cbe-a94a-9533a736e2a2)

*Figure 1: Zphisher main interface. This is where we can choose the template for the phishing login page*

**Generate Phising Link**
- After choosing the template, select the host type and custom port preferance
  
![zphiserurl](https://github.com/user-attachments/assets/37062f7e-1d2a-42db-9926-2acb5bd68e14)

*Figure 2: After setting the host type and custom port preference (1), a phishing link is generated (2). Note that some options of the app template may not work anymore.*

**Phising Attack**

At this point, the method to deliver the phishing link to the victim could be various; the most common ones are through personalized email and text messages. 

![zphisher faker](https://github.com/user-attachments/assets/496a07c4-a7b0-4618-9f86-1c71e315a90a)

*Figure 3: A Netflix phishing webpage that prompts user to login using username and password. Note that the URL generated by Zphiser does not look genuine and looks suspicious.*

**Verify the successful attack**

The username and password of the victim who clicked and entered the login credentials is recorded in the path /zphisher/auth/username.dat 

![zphisher veri](https://github.com/user-attachments/assets/b40ad7d8-75c6-481e-9e9f-83ab9ddfacbc)

*Figure 4: Victims who clicked the link will have their IP address recorded, then if they fill in the usernames and password, the credentials are also recorded.*

## Result

We demonstrated how the victim clicked the link and gave in the credentials to the attacker. With the credentials, the attacker could hack into the victim's account. However in the actual world, the success of the attack depends on whether or not the victim is aware of the phising email.

## Mitigation Plan

- Routine cybersecurity awareness training to the employees on how to identify and respond against phishing emails.
- On endpoint devices, install email filtering and security software to detect and block emails from malicious domains.
- Implement Multi Factor Authentication on staff accounts
