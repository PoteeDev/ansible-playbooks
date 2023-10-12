# Create system user

## Generate password hash

```
sudo apt install -y whois
mkpasswd --method=sha-512
```

## Insert hashed password to inventory/create-system-user/group-vars/all.yml

```
---
system_user: player
system_user_pass: $6$fKSvBD3Ul/PstPj9$pQAHDJEh5C.Z1H1UQO1/nAUED.pBpj.dB3QPAayu/eW4FxILPjLpoQ0wNG1xmTRF/Cgi153vlYip6kHsPksXW/
```

## Run playbook as root user and ask for password prompt

```
ansible-playbook -i inventory/hosts.ini create-system-user.yml -kK
```