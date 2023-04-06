# How to Log into a Course-Specific Account on ieng6
## A Tutorial for UCSD Students

![Image](https://github.com/Eugene-Myong/cse15l-lab-reports/blob/main/hi%20shitpost.jpg)

---

So you wanna learn how to log into a remote server, and I have to make this blog post for my grade, so it seems we can reach an agreement here. I need the grade, you have no idea what you're doing, and my rate is $120 USD per hour. Let's get started.

---
## Installing VSCode

This tutorial assumes you already set up your cs15lsp23zz account, with zz being any two letters that correspond to your account.

First things first, you need to install **VSCode**. In my opinion, quite a mid IDE but it is what it is. You can download it here at this link: [VSCode](https://code.visualstudio.com/).
It should look something like this: ![Image](https://github.com/Eugene-Myong/cse15l-lab-reports/blob/main/vsc%20menu%20screenshot.png)
Here are the steps to download it: 
1. Press the big fat blue download button
2. Fuck around and find out

Now you've got VSCode downloaded. Great, we can move on.

---
## Terminal and Git

Next, after you've got it set up, it should look (something) like this: ![Image](https://github.com/Eugene-Myong/cse15l-lab-reports/blob/main/vsc%20main%20menu%20screenshot.png)

From here, open a terminal in VScode by clicking `Terminal` at the top bar then clicking on `New Terminal`.
After that, you should see this thing at the bottom (or side, or somewhere on screen): ![Image](https://github.com/Eugene-Myong/cse15l-lab-reports/blob/main/vsc%20terminal%20menu%20screenshot.png)
Just a quick note: The `PS C:\Users\eugen>` just means the current `User` profile I'm on is `eugen`. The `eugen` part should be whatever you named your profile.

Now that you have VSCode and a Terminal ready, you need to download **Git**, which you can get here: [Git for Windows](https://gitforwindows.org/)
Git has a lot of setup proccesses, so if this is your first time or you don't have any preferences, the default options will do just fine.
Once you have Git installed, then we can move on.

Next is setting up **Git Bash** on VSCode. What this means is that Git Bash will be integrated into VSCode, allowing you to do Git stuff in VSCode.
To do this, follow these steps:
1. Open the command palette using `Ctrl` + `Shift` + `p`
2. Type in "Select Default Profile" and click on it 
3. Select "Git Bash" from the options (if you don't see anything, give it a minute or two.).
4. Go to your terminal and select the `+` option which is located here ![Image](https://github.com/Eugene-Myong/cse15l-lab-reports/blob/main/vsc%20terminal%20menu%202%20ss.png)
5. The new terminal will be a Bash terminal. You can also press that little arrow to toggle between other terminals.

Congratulations, now you have a working Git Bash Terminal and can use it to type some commands and access a remote server. But how? 

---
## Accessing the ieng6 server remotely

So, in order to access the remote server, you will need your account name and password.
Type into the terminal `ssh cs15lsp23zz@ieng6.ucsd.edu`, with **zz** being replaced by the two letters that associate with your account.
As it's your first time logging in, you will see this message: 
```
⤇ ssh cs15lsp23zz@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
```
If you see this message as you log into a server you go to often, this could mean your being compromised. In that case, kill your computer, lock your doors and close the windows, cut the lights, get down, and have your sling ready. Or just read this article on it because [someone may be trying to listen in or control the conversation](https://superuser.com/questions/421074/ssh-the-authenticity-of-host-host-cant-be-established/421084#421084).
Once you're good, type yes, and next you'll see something like this: 
```
⤇ ssh cs15lsp23zz@ieng6.ucsd.edu
The authenticity of host 'ieng6-202.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
Password: 
```
Type in your password and now you're in! You should see something like this:
```
# Now on remote server
Last login: Sun Jan  2 14:03:05 2022 from 107-217-10-235.lightspeed.sndgca.sbcglobal.net
quota: No filesystem specified.
Hello cs15lsp23zz, you are currently logged into ieng6-203.ucsd.edu

You are using 0% CPU on this system

Cluster Status 
Hostname     Time    #Users  Load  Averages  
ieng6-201   23:25:01   0  0.08,  0.17,  0.11
ieng6-202   23:25:01   1  0.09,  0.15,  0.11
ieng6-203   23:25:01   1  0.08,  0.15,  0.11

Sun Jan 02, 2022 11:28pm - Prepping cs15lsp23
```
Where lots of the text may differ based on your last login, users, load and such.
Congradulations, you're now connected to a computer in the CSE basement. 
This next and last section will cover some commands you can run and what they do.

---
## Commands to use

Below are some commands to use while connected to the server, as well as my discovered explanations of what they do:
* `cd~` - This will take your directory back to the home directory, which is the one whth your account username.
* `cd ..` - This will take your directory back one.
* `ls <directory> where <directory> is /home/linux/ieng6/cs15lsp23/cs15lsp23abc, where the abc is one of the other group members’ username` - This one will lead to an access denied result, but I'm quite sure it will take you to their accout directory.
* `pwd` - will print your current directory.
* `ls` - will list all the directories and files in your directory.
* `cat` - will print out the file listed for it.
* `exit` - will leave the server.


And that's it for now. Thanks for reading, and if you liked it, feel free to donate to me! I accept only cash in unmarked envelopes and in divisions of 10s.


