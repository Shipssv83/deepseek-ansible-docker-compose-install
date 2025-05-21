Hi, ![](https://user-images.githubusercontent.com/18350557/176309783-0785949b-9127-417c-8b55-ab5a4333674e.gif) my name is Serhii Shypylov
=========================================================================================================================================

-------------------------------

## 🛠️ Technologies & Tools
<div align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg" height="40" alt="Linux logo" />
  <img width="12" />
  <img src="https://cdn.simpleicons.org/gnubash/4EAA25" height="40" alt="Bash logo" />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/ansible/ansible-original.svg" height="40" alt="Ansible logo" />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg" height="40" alt="Docker logo" />
  <img width="12" />
</div>

## 🌐 Connect with Me
<p align="left">
  <a href="https://t.me/OenITConsultant_bot">
    <img src="https://img.icons8.com/ios-glyphs/30/ffffff/telegram-app.png" alt="Telegram" width="30" height="30" />
  </a>
  <a href="https://www.linkedin.com/in/sergey-shipilov-7262a31b4/">
    <img src="https://img.icons8.com/ios-glyphs/30/ffffff/linkedin.png" alt="LinkedIn" width="30" height="30" />
  </a>
  <a href="https://www.instagram.com/shipssvpl/">
    <img src="https://img.icons8.com/ios-glyphs/30/ffffff/instagram-new.png" alt="Instagram" width="30" height="30" />
  </a>
  <a href="https://www.facebook.com/profile.php?id=100083345006373">
    <img src="https://img.icons8.com/ios-glyphs/30/ffffff/facebook.png" alt="Facebook" width="30" height="30" />
  </a>
  <a href="https://discord.com/invite/6z5EyagDyW?ref=1it.pro">
    <img src="https://img.icons8.com/ios-glyphs/30/ffffff/discord.png" alt="Discord" width="30" height="30" />
  </a>
  <a href="mailto:admin@mail.1it.pro">
    <img src="https://img.icons8.com/ios-glyphs/30/ffffff/new-post.png" alt="Email" width="30" height="30" />
  </a>
  <a href="https://1it.pro/">
    <img src="https://img.icons8.com/ios-glyphs/30/ffffff/domain.png" alt="Website" width="30" height="30" />
  </a>
</p>

---
# DeepSeek Installation via Ansible and Docker Compose

This guide provides step-by-step instructions to set up DeepSeek using Ansible and Docker Compose.

## Playbook Structure
1. **Server Setup (`server-install.yml`)**: Installs necessary server dependencies and configures system settings (e.g., timezone).
2. **Docker Installation (`docker-install.yml`)**: Installs Docker and Docker Compose to prepare the system for running containers.
3. **DeepSeek Docker Installation (`ollama-docker-install.yml`)**: Deploys DeepSeek in a Docker container and configures firewall rules.

## Requirements
Before running the playbook, ensure the following requirements are met:
- Ansible 2.9+ installed on the control node.
- SSH access to the target host.
- A Linux server (Ubuntu, CentOS, etc.) with internet access.

## Roles Used
- `roles/server-install`: Sets up server environment and system configurations.
- `roles/docker-install`: Installs Docker and Docker Compose.
- `roles/ollama-docker-install`: Deploys DeepSeek in a Docker container.

## Variables
Customize the playbook using the following variables:

```yaml
vars:
  fqdn: example.com
  server_name: "openia.{{ fqdn }}"
  openia_root_url: "https://openia.{{ fqdn }}"
```

## Ansible Galaxy Roles
### Install required roles
```sh
ansible-galaxy install -r roles/requirements.yml
```
### Upgrade existing roles
```sh
ansible-galaxy install -g -f -r roles/requirements.yml
```

## Running the Playbook
Execute the playbook using your inventory file and variables:
```sh
ansible-playbook -i inventory --user root --extra-vars "host=host_name" playbooks/ollama-docker-install.yml
```

## License
This project is licensed under the MIT License.

