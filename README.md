# Wireshark-to-capture-network-traffic

## Objective

 Using Wireshark and FTP to demonstrate that FTP (insecure protocol) transmits data in cleartext. Don't use insecure protcols like FTP or Telnet that passes data in cleartext, attackers utilizing sniffing software can sniff the network and steal your credentials (username and password). 


### Skills Learned

- How to install an FTP server and create a user/password using Filezilla
- How to start and capture network packets. 
- Launch the FTP service on Kali (client) to connect to the Windows box (server)

### Tools Used

- Filezilla
- Kali
- Windows 10 


## Steps
1. We are going to be using Filezilla, which is a free FTP service to create our FTP server.
2. Google Filezilla and down load the Filezilla server, will be a default install.
3. Once the program launches, click on the Server tab->configure and go to Create User.
4. Notice you will be using 21 port for the FTP.
5. Create a user, I created Elsa as a user.
6. Select 'Require a password to logon' my password was Elsa123.
7. Click Apply, then Ok. Your username and password are now created.
8. We are going to go to Kali to steal the password.
9. Open the Wireshark program that should already be pre-installed on Kali.
10. We will be listening to eth0 and need the IP address of the Windows box.
11. Navigate back the your Windows box and launch a command prompt. Should be able to find the IP address using the command 'ipconfig'
12. Take note of that IP address.
13. Navigate back to Kali and click on the blue Shark Fin in Wireshark to start a packet capture.
14. Open up a terminal and type FTP
15. FTP>open, to: IP address of the Windows box
16. You are now connected to the FTP server on the Windows box.
17. It will ask for your username and password.
18. Once username and password are correctly applied, the login is successful.
19. Go to Wireshark and click the Stop icon to stop capturing packets.
20. Click on the Protocol option sort by protocol and search for the FTP protocols.
21. You will see the username and password were transmitted in plaintext! If we use insecure protocols like FTP, attacks can sniff the actual data and use it.

    FTP credentials in plaintext on Wireshark:
    ![image](https://github.com/user-attachments/assets/2f6d2ec2-1cad-4549-b155-8d095ce649d0)

