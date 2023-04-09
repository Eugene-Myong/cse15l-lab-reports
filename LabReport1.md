# How to Log into a Course-Specific Account on ieng6
## A Tutorial for UCSD Students

![Image](./hi shitpost.jpg)

---

So you wanna learn how to log into a remote server, and I have to make this blog post for my grade, so it seems we can reach an agreement here. I need the grade, you have no idea what you're doing, and my rate is $120 USD per hour. Let's get started.

---
## Part 1: Setup
### Installing VSCode

This tutorial assumes you already set up your cs15lsp23zz account, with zz being any two letters that correspond to your account.

First things first, you need to install **VSCode**.  You can download it here at this link: [VSCode](https://code.visualstudio.com/).
It should look something like this: 

![Image](https://github.com/Eugene-Myong/cse15l-lab-reports/blob/main/vsc%20menu%20screenshot.png)

Just follow the setup process (default options for all are ok).

Now you've got VSCode downloaded. Great, we can move on.

### Terminal and Installing Git

Next, after you've got it set up, it should look (something) like this: 

![Image](https://github.com/Eugene-Myong/cse15l-lab-reports/blob/main/vsc%20main%20menu%20screenshot.png)

From here, open a terminal in VScode by clicking `Terminal` at the top bar then clicking on `New Terminal`.
After that, you should see this thing at the bottom (or side, or somewhere on screen): 

![Image](https://github.com/Eugene-Myong/cse15l-lab-reports/blob/main/vsc%20terminal%20menu%20screenshot.png)

Just a quick note: The `PS C:\Users\eugen>` just means the current `User` profile I'm on is `eugen`. The `eugen` part should be whatever you named your profile.

Now that you have VSCode and a Terminal ready, you need to download **Git**, which you can get here: [Git for Windows.](https://gitforwindows.org/)
Git has a lot of setup proccesses, so if this is your first time or you don't have any preferences, the default options will do just fine.
Once you have Git installed, then we can move on.

Next is setting up **Git Bash** on VSCode. What this means is that Git Bash will be integrated into VSCode, allowing you to do Git stuff in VSCode. Don't worry about the small details, I don't know them yet either. 
To do this, follow these steps:
1. Open the command palette using `Ctrl` + `Shift` + `p`
2. Type in "Select Default Profile" and click on it 
3. Select "Git Bash" from the options (if you don't see anything, give it a minute or two to load.).
4. Go to your terminal and select the `+` option which is located here 

![Image](https://github.com/Eugene-Myong/cse15l-lab-reports/blob/main/vsc%20terminal%20menu%202%20ss.png)

7. The new terminal will be a Bash terminal. You can also press that little arrow to toggle between other terminals.

Congratulations, now you have a working Git Bash Terminal and can use it to type some commands and access a remote server. But how? 

---
## Part 2: Accessing the ieng6 server remotely

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

![Image](https://github.com/Eugene-Myong/cse15l-lab-reports/blob/main/ss%20terminal%20shit.png)

Where lots of the text may differ based on your last login, users, load and such.

Congratulations, you're now connected to a computer in the CSE basement. 
This next and last section will cover some commands you can run and what they do.

---
## Part 3: Commands to use

Below are some commands to use while connected to the server, as well as my discovered explanations of what they do:
* `cd~` - This will take your directory back to the home directory, which is the one whth your account username.
* `cd ..` - This will take your directory back one.
* `ls <directory> where <directory> is /home/linux/ieng6/cs15lsp23/cs15lsp23abc, where the abc is one of the other group members’ username` - This one will lead to an access denied result, but I'm quite sure it will take you to their accout directory.
* `pwd` - will print your current directory.
* `ls` - will list all the directories and files in your directory.
* `cat` - will print out the file listed for it.
* `exit` - will leave the server.

Here is a screenshot from one of my sessions where I played around with some code. See if you can trace it:

![Image](https://github.com/Eugene-Myong/cse15l-lab-reports/blob/main/terminal%20commands%20ss.png)


And that's it for now. Thanks for reading!
