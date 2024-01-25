<h2 dir="rtl" align="center">
بسم الله الرحمن الرحيم
</h2>

# Managing Multiple Github Accounts

In this repo I will explain in detail how to work with multiple Github accounts on a single device running **Windows** operating system using **SSH**.

Suppose this scenario :  
We have two github accounts, one **personal** and the other one for  **work** and want to setup our device to interact with both 2 accounts.

**Note**  
Every single command and configuration file exists in this repo so read it carefully and then apply each step.

## 1. Start OpenSSH Authentication Agent
<div align="center">

 ![image](https://github.com/MohamedHashish42/Managing-Multiple-Github-Accounts/assets/81900786/777df7dd-588a-43c6-8a1c-35d0f7d9ccf5)

</div>

## 2. Create SSH keys for each account
### First, we will need to create **.ssh** folder as the following

<div align="center">

![image](https://github.com/MohamedHashish42/Managing-Multiple-Github-Accounts/assets/81900786/6af06fc3-2aef-4313-9111-e504ece1f983)

</div>

### Then Create SSH keys for each account
<div align="center">

![image](https://github.com/MohamedHashish42/Managing-Multiple-Github-Accounts/assets/81900786/df982f8c-1f55-4f9d-a5d4-db1e636d5019)

</div>

## 3. Create a Config File and Make Host Entries

<div align="center">

![image](https://github.com/MohamedHashish42/Managing-Multiple-Github-Accounts/assets/81900786/400aea7b-caef-4ec2-84cb-7fef9d1966b6)

</div>

## 4. Add SSH keys to SSH Agent 


<div align="center">

![image](https://github.com/MohamedHashish42/Managing-Multiple-Github-Accounts/assets/81900786/1e4bd616-11b9-4ac1-bcaf-2fc3b5d1ae88)

</div>


## 5. Add SSH public key to the Github Accounts
In this step we will copy our public key (that we have generated in our previous step) and add it to corresponding github accounts as the following.

<div align="center">

![image](https://github.com/MohamedHashish42/Managing-Multiple-Github-Accounts/assets/81900786/2287e14e-c617-4848-88dc-2529fddcf540)

![image](https://github.com/MohamedHashish42/Managing-Multiple-Github-Accounts/assets/81900786/7d2dca01-821f-4f2f-b057-1ff508a1b540)

</div>

### Test connection
<div align="center">
  
![image](https://github.com/MohamedHashish42/Managing-Multiple-Github-Accounts/assets/81900786/69fac7cc-3984-4813-8d3f-47d4c81189dd)

</div>

## 6. Add config file for each account
Now we can clone repos from the 2 different accounts using the 2 hosts **(personal and work)** we defined 
in config file in .ssh folder.    

For example if the ssh for a repo on the personal account is    
**git@github.com:[your_user]/TestRepo.git**  

We will clone it like this
```bash
git clone git@personal:[your_user]/TestRepo.git
#or
git clone personal:[your_user]/TestRepo.git
```

But there an issue because for example if we make commit for any repo from any account we will find that commit was made 
by the user and email defined in global git config, to solve this issue we have two options.

### The two Options to solve previous issue
#### Option1: Setting needed config for each repo each time we clone it using the following 2 commands  
git config user.email "[repo_corresponding_email]"  
git config user.name "[repo_corresponding_username]"  

#### Option 2: Creating a folder and git config file for each account (Preferred)
##### - Create a folder for each account as the following
<div align="center">

![image](https://github.com/MohamedHashish42/Managing-Multiple-Github-Accounts/assets/81900786/f11a7876-f678-4b27-938a-91da9b214bcb)

</div>

##### - Create git config file for each account as the following

<div align="center">

![image](https://github.com/MohamedHashish42/Managing-Multiple-Github-Accounts/assets/81900786/f47f141a-6889-4563-b0b8-f6a23c98d5ce)

</div>


##### - Edit your global git config as the following

<div align="center">
  
![image](https://github.com/MohamedHashish42/Managing-Multiple-Github-Accounts/assets/81900786/3d60600f-7d27-4eca-81fa-2ef9178632e5)

</div>

##### - Test that configs are added correctly
<div align="center">
  
![image](https://github.com/MohamedHashish42/Managing-Multiple-Github-Accounts/assets/81900786/cc8cbafd-488d-4331-807e-f3be6394db06)

</div>

## Commands and configuration files

- [All Configrations Files](https://github.com/MohamedHashish42/Managing-Multiple-Github-Accounts/blob/main/AllConfigrationsFiles.md)

- [Commands Used In Each Section](https://github.com/MohamedHashish42/Managing-Multiple-Github-Accounts/blob/main/CommandsUsedInEachSection.md)

## References

- [How to work with multiple GitHub accounts on a single Windows computer using SSH](https://www.youtube.com/watch?v=Fyfp0oEWD6w) 
- [Work With Multiple Github Accounts](https://gist.github.com/rahularity/86da20fe3858e6b311de068201d279e3)
- [Chat GPT](https://chat.openai.com/auth/login)

