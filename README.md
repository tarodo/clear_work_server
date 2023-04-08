# My private server

## Prepare
1. Create `inventory.ini` file in base directory with hosts:
    ```
    [webservers]
    target_host_ip ansible_user=root ansible_ssh_private_key_file=mykeyfile.pem
    ```
2. Create `vars.yml`:
   ```
    users:
      - username: "myuser"
        groups: "admin"
        email: "myuser@email.com"
   ```
3. Add public key for new users into `files/` with name like `myuser_key.pub`

## Run
Use shell:
```shell
ansible-playbook -i inventory.ini main.yml -u root
```