# All Configrations Files

## 1. ssh config (config)

```ini
# GitHub personal
Host personal
Hostname github.com
User git
IdentityFile "C:/Users/[your_user]/.ssh/[private_key_of_personal_account]"
IdentitiesOnly yes

# GitHub work 
Host work
Hostname github.com
User git
IdentityFile "C:/Users/[your_user]/.ssh/[private_key_of_work_account]"
IdentitiesOnly yes
```

## 2. git configs

### 2.1 Personal git config (.gitconfig-personal) 

```ini
[user]
    name = [username_of_personal_account]
    email = [email_of_personal_account]

[core]
    sshCommand = C:/Users/[your_user]/.ssh/[private_key_of_personal_account]
```

### 2.2 Work git config (.gitconfig-work) 
```ini
[user]
    name = [username_of_work_account]
    email = [email_of_work_account]

[core]
    sshCommand = C:/Users/[your_user]/.ssh/[private_key_of_work_account]

```

### 2.3 Global git config (.gitconfig)

Add the following sections 

```
[includeIf "gitdir:C:/Users/[your_user]/Documents/Github/personal/"] 
    path = .gitconfig-personal

[includeIf "gitdir:C:/Users/[your_user]/Documents/Github/work/"] 
    path = .gitconfig-work

[core]
    sshCommand = C:/Windows/System32/OpenSSH/ssh.exe
```


