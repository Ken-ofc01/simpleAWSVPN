# SimpleAWSVPN
This is abut how you can create a simple VPN using AWS free tier service.

# Free VPN on Cloud

This focuses on how you can create a simple & free VPN service for yourself in AWS.

# Installation

## Create AWS Account

Create an AWS Free TIer Account fron this  [url](https://aws.amazon.com/)

## Choose your desired Location for your server

Firstly you would have to choose your desired location for your vpn server.( I am going for Mumbai, India for some personal benefits)
![image](https://github.com/user-attachments/assets/ed89406e-ed23-4e20-b93e-48b7d5c1de42)

## Create your EC2 Instance
Seaarch for EC2 on the search bar on AWS
![image](https://github.com/user-attachments/assets/7e1d564d-851c-42b6-b921-e1dd27ab9d47)

CLick on Instance
![image](https://github.com/user-attachments/assets/6009b4f5-67c6-461e-9203-ed9a2d51b567)

Click on Launch Instance

![image](https://github.com/user-attachments/assets/999f2bb3-e18e-4407-aaa7-15a3f9f35821)

Give a name for your Server
![image](https://github.com/user-attachments/assets/b4823669-05f2-4dbd-9ee9-57af87bad627)

Chosing Linux Image
![image](https://github.com/user-attachments/assets/295aae75-02c7-48d4-b39a-36a41832762c)

Keypair
- As I refer this to be a tutorial for complete beginners we would not create keypairs assusing that you are not very good with ssh tech.
![image](https://github.com/user-attachments/assets/1a24fb38-7c70-43f0-9348-b94618c2fe43)

## Configuring EC2 Network Settings
![image](https://github.com/user-attachments/assets/257962a1-9083-4d66-86a7-e3074210e49f)
- Adding Inbound Security Rule
  ![image](https://github.com/user-attachments/assets/57f5ceb7-5ff5-4923-8140-0e307552e7ae)
This is because, the firewall of the EC2 does block all the ports and does not allow the traffic to flow from it. As we are creating aa VPN Service we need the ports to open so that our devices could connect to this server. Here we opened all UDP ports ( this is not secure and would be better if we opened the specific port that PIVPN uses).

## Launch the instance
You can Launch Your instance after configuring all these settings

## Connecting to the Instance

As we created no keypairs we cannot connect to the server using the SSH connection for your terminal. So we would just use the EC2 instance connect service from Amazon to connect to the instance.
![image](https://github.com/user-attachments/assets/2dcb164c-b969-43d3-9cf7-d683951d29fd)
![image](https://github.com/user-attachments/assets/e7ca0d37-c17c-4516-b469-7c25be498165)

## Installing PIVPN Script
After you connect to the instance, run the following commands
```
sudo su
```
```
sudo apt-get update
sudo apt-get upgrade
```

Go to the  [PIVPN website](https://pivpn.io)
Copy the Installation Script 
The Installation Script should look something like this:
```
curl -L https://install.pivpn.io | bash
```
Paste the Script to the EC2 Serial Console.

- Keep everything default
- Wait till the Server Reboots



# Usage

After the installation of the PIVPN, You can run the following commands.
Here I created two users profile one for my PC and one for for my Phone.
![image](https://github.com/user-attachments/assets/de93d43c-3dab-46c5-99b1-1054bc7bd103)

You can also use qr code to connect using your wireguard app.
![image](https://github.com/user-attachments/assets/aed151d3-59e2-44c1-b5d6-50d471ed701b)












