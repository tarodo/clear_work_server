# My private server

## Prepare
Create `inventory.ini` file in base directory with hosts:
```
[webservers]
target_host_ip ansible_user=myuser ansible_ssh_private_key_file=mykeyfile.pem
```

## Run
Use shell:
```shell
ansible-playbook -i inventory.ini main.yml -u root
```