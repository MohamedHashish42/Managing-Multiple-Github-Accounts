# Commands used in each section

## Create SSH keys for needed accounts
```bash
ssh-keygen -t rsa -b 4096 -C "personal" -f "C:\Users\[your_user]\.ssh\github_personal_key"
ssh-keygen -t rsa -b 4096 -C "work" -f "C:\Users\[your_user]\.ssh\github_personal_key"
```

## Add SSH keys to SSH Agent 
```bash
ssh-add  C:\\Users\\[your_user]\\.ssh\\github_personal_key
ssh-add  C:\\Users\\[your_user]\\.ssh\\github_work_key
```
### Check that SSH keys are added to SSH Agent
```bash
ssh-add -l
```

## Display the contents of the public key 
```bash
type .\.ssh\github_personal_key.pub
type .\.ssh\github_work_key.pub
```

## Testing connection
```bash
ssh -T personal
ssh -T work
```

## List git configs
```bash
git config --list
```
