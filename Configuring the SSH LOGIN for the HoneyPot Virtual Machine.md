# SSH SETUP FOR HONEYPOT VM
I created a the KeyPair file (Public and Private) using the this command : <img width="348" height="23" alt="image" src="https://github.com/user-attachments/assets/0bce99d7-f2ab-4d2e-b8b5-258ed2f26ec1" /> <br>
which was saved on my Local Host (PC) and then I used this command to locate and view my Public Key <br>
<img width="361" height="22" alt="image" src="https://github.com/user-attachments/assets/ee71b459-9afc-40a2-ba86-c0fdc499ffb5" /><br>
I then copied the Public key, Mine looked like this <img width="864" height="21" alt="image" src="https://github.com/user-attachments/assets/8521d329-5ace-4432-a7ae-cd126887b23c" /> <br> and Pasted it into my ~/.ssh/authorized_keys File in my HoneyPot Virtual Machine. 

I dont think I had the ~/.ssh Directory available so i had to create the that. using this command from my terminal <br>
<img width="230" height="50" alt="image" src="https://github.com/user-attachments/assets/d12d1085-8fbe-4e1e-9b24-c9b6a0e4c617" /><br>

The -p in the command makes it so that if the directory already exist, An error message would not POP UP. Pretty Nice!! 

I then created a FILE called authorized_keys in the ~/.ssh Directory using this command <br>
<img width="289" height="64" alt="image" src="https://github.com/user-attachments/assets/54756905-ca8e-4d18-875e-1f0015d85911" /> <br>                                                                                                                            
I also gave the Directory and File the right Priviledges using this command: <br>
<img width="331" height="58" alt="image" src="https://github.com/user-attachments/assets/c1cbcdb2-2fce-4a20-839d-f8b27972d08f" /> <br>

So the command above: Only The owner of the file (the user whose home directory contains the .ssh folder) has read and write access to the authorized_keys file. 

Cool, After that i use the command IP A as shown in the diagram below 
<br>
<img width="822" height="230" alt="image" src="https://github.com/user-attachments/assets/8c37a32e-8de6-4b61-94fe-d17867e28eaa" /> <br>

To view the static Ip of the HoneyPot Virtual Machine which i already setup prior to this Documentation. 
I also made sure it was isolated while being able to communicate with the Local-Host 

At this Point typing the command : ssh username@vm_ipaddress the SSH LOGIN should be successful but there is still one more step to check that i struggled with . 

After a few research, i edit a Configuration File called sshd_config as shown in the image below <br>
<img width="327" height="52" alt="image" src="https://github.com/user-attachments/assets/d31b41da-5d32-485c-a7c0-a1770d728ff1" /> <br>

This file is always located in the /etc/ssh/sshd_config 

Everything in this file should be commented out with the # like this <br>
<img width="328" height="255" alt="image" src="https://github.com/user-attachments/assets/45a1a374-d4b5-47c5-b0b2-01eee972cba6" /> <br> 

The two things we should look for are 

1. Pubkey Authentication <br>
<img width="586" height="186" alt="image" src="https://github.com/user-attachments/assets/46e29bd5-6355-4785-8e48-fb9f8a71d64c" /> <br>

2. Password Authentication <br> 
<img width="647" height="197" alt="image" src="https://github.com/user-attachments/assets/ca0868a4-64a6-4bce-a879-d55eb40c775b" /> <br>

So you should find both of them commented with the # in from of them. Take the # off and make sure they are both set to YES! As shown in the Images above. <br>

Control X to exit and then Y to save and then Press ENTER to Fully Exit out of the File Editor. BOOOOM!

Finally i used the command shown below <br>
<img width="311" height="54" alt="image" src="https://github.com/user-attachments/assets/d9ed992c-736c-4bf7-b6e5-3ad4942c8657" /> <br>

To restart the SSH Service ( PORT 22 ) and then BOOOOOOOOOOOOOOOOOOM !!! 

In your LOCAL HOST ( YOUR ACTUAL LAPTOP OR PC ) IN COMMAND PROMPT (CMD) OR POWERSHELL <BR>

The Command: ssh username(which is kali)@vm_ipaddress(which is 172.168.72.20) should be working, Hopefully LMAO 😭😭

Here is my screenshot of me connecting to my HoneyPot VirtualMachine Via SSH. <br>
<img width="1001" height="696" alt="image" src="https://github.com/user-attachments/assets/c4e74d2f-d4db-4ca6-8a16-5539a42cb8bf" /> <br>

And as you can see from previous screenshots that I used the same IP ADDRESS and the HostName is the same which is HoneyPotty. Also Just to not forget, The Password for Login in to the SSH should be the same password for the Virtual Machine you are trying to log into not your SSH PassPhrase...

# THANK YOU 















