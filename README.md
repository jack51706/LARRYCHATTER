[![forthebadge made-with-python](http://ForTheBadge.com/images/badges/made-with-python.svg)](https://www.python.org/)

[![GitHub license](https://img.shields.io/github/license/Naereen/StrapDown.js.svg)](https://github.com/Naereen/StrapDown.js/blob/master/LICENSE)
#
![screenshot](Logo.png)
# LARRYCHATTER

## Introduction:
Introducing a  super-stealthy extra sneaky Python-based Implant Framework that uses Twitter & Dropbox as a C2 Server.
This project has been inspired by the Russian threat-group APT-29's own malware HAMMERTOSS tDiscoverer variant.
In fact, LARRYCHATTER is HAMMERTOSS Revenant. A Reincarnation. In pure Python. It's a lot similiar except that it's better.

## A Simplified Block Diagram First:
![screenshot](LARRYCHATTER_Simplified_Block_Diagram.png)

## Another One Of Twitter Handle Generation Algorithm:
![screenshot](LARRYCHATTER_Twitter_Handle_Generation_Algorithm.png)

## What Is LARRYCHATTER Exactly?
LARRYCHATTER is a cross-platform C2 Framework. Much like Merlin, Sliver, Faction C2, yada yada yada. The only difference is that it uses covert channels over public platforms instead of standard communication over HTTP/HTTPS to attacker-controlled domains which can be detected very easily and also taken down in a jiffy. It's purpose is to make the life of Blue-teamers a lot-less easy! It is primarily aimed at professional red-teamers for red-team engagements. Modules can be written in Python and integrated at the click of a finger. The Prototype version of LARRYCHATTER comes with two modules - a 'recon' module and a 'kill' module in-built which is albeit very crude and doesn't do much. My main goal was to show everyone how easily social-media and public platforms can be exploited by malware to communicate with it's operators. Additional modules and advancement of existing ones coming soon, so stay tuned ;)

## Terminology:
LARRYCHATTER Framework consists of:
- CommandPost - The software which is used to issue commands to the Implant run by the operator.
- Implant - The main malware which is run on the target machine.

This repository contains two source files:
- ```LARRYCHATTER_CommandPost.py``` which is the source-code of the LARRYCHATTER Command Post(CP).
- ```LARRYCHATTERImplant.py``` which is the source-code of the LARRYCHATTER Implant.

## Features:
- No suspicious Internet traffic to external unknown domains for C&C - Only traffic observed is Twitter and Dropbox! (Say buh-bye to those pesky firewalls)
- 'kill' module - Terminates the Implant on the target machine
- 'recon' module - Performs initial recon on the target system like basic system details, patches installed, takes screenshots on a random interval for 'x' minutes and searches for all types of juicy file-types for exfiltration later. Windows-support only. Very crude. No AV-Evasion subroutines. But fully functional and uploads collected Intel on a Dropbox account for retrieval by the operator later.
- Basic Steganography integrated
- Hardcoded Symmetric Encryption support in-built with 128-bit AES in CBC Mode
- Coded in Python 3
- Single Implant support only by CommandPost since this is only the Prototype.

## Etymology:
So y'all might be wondering what sort of a peculiar name is LARRYCHATTER? So you have seen the cute bird in the Twitter logo right? Well her name is Larry and since this Implant communicates over Twitter(chatter), I figured it's only appropiate I name it LARRYCHATTER.

## Prerequisites:
For this to work you will need:
- A Twitter Dev Account (**Please use a dedicated account! Do NOT use your personal one!**)
Create an App with Read, Write access. Specifically note down the CONSUMER KEY, CONSUMER SECRET, ACCESS TOKEN and ACCESS TOKEN SECRET values (I am not gon' tell you guys how, go Google it, should be a pretty easy thing to do)
Also note down the Handle/Username of your Twitter Account.
- A Dropbox Account. (**Please use a dedicated account! Do NOT use your personal one!**) 
Generate an API Token. (Again not gon' explain how, pretty easy to figure it out)
- A Machine with a Linux VM and a Windows 7/8/10 VM OR two separate machines

## Guide:
- Install the required Python dependencies
- `pip install -r requirements.txt`
- Run the LARRYCHATTER_CommandPost.py on the Linux VM(operator machine) and follow the instructions herein. Type help for further assistance.
- `python3 LARRYCHATTER_CommandPost.py`
- Run the LARRYCHATTER_Implant.py on the Windows VM(target machine)
`python LARRYCHATTER_Implant.py`
- Run 'recon' module on the Command Post and follow the on-screen instructions
- Wait for some time for the Implant to collect the intel
- Check the Dropbox Files section for the uploaded Intel
- Run 'kill' module on the Command Post to kill the Implant on the target machine
- Decrypt the Intel with the help of the decrypter.py and Profit!

- Note - Don't forget to change the Encryption keys!

## To Do:
- [ ] Integrate Twitter Handle Generation Algorithm
- [ ] Integrate AV Evasion Routines
- [ ] Modify the 'recon' module to add more features
- [ ] Integrate more advanced modules
