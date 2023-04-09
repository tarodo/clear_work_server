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
4. Don't forget about fonts on your host
   1. Windows:
      - Download JetBrainsMono Nerd Font from here.
      - Extract into a folder
      - Select all fonts and right-click "Install for all users"
      - In Windows Terminal open Settings
      - Under "Profiles" select the profile you use to open AstroNvim with
      - Additional Settings > Appearance > Font Face > JetBrainsMono Nerd Font
   2. Ubuntu:
      ```shell
      /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/JetBrains/JetBrainsMono/master/install_manual.sh)"
      ```

## Run
Use shell:
```shell
ansible-playbook -i inventory.ini main.yml -u root
```