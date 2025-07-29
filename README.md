
# Fullstack App Deployment using Ansible Role

## 📝 Overview

This project demonstrates the deployment of a fullstack Node.js web application using **Ansible** and a reusable role from **Ansible Galaxy**.

It utilizes a public role I created and published:

🔗 Galaxy Role: [abeerseada.fullstack_deploy](https://galaxy.ansible.com/abeerseada/fullstack_deploy)  
🔗 GitHub Repo: [ansible-role-fullstack-deploy](https://github.com/abeerseada/ansible-role-fullstack-deploy)

---

## 📦 Role Installation

First, install the role from Ansible Galaxy:

```bash
ansible-galaxy install abeerseada.fullstack_deploy
````

This will download the role to `~/.ansible/roles/`.

---

## 🚀 Usage

### Inventory

Create an `inventory` file with your target host:

```ini
[target]
your-server-ip ansible_user=deploy ansible_ssh_private_key_file=~/.ssh/id_rsa
```

### Playbook

```yaml
- name: Deploy fullstack app using Galaxy role
  hosts: target
  become: true
  roles:
    - abeerseada.fullstack_deploy
```

Run the playbook:

```bash
ansible-playbook -i inventory playbook.yaml
```

---

## 📂 Application Files

The fullstack Node.js app is already included in the Galaxy role under `files/app/`.
It will be copied to `/var/www/todo-app/` on the remote server automatically.

---

## 🧑‍💻 Author

**Abeer A. Mohamed**
GitHub: [abeerseada](https://github.com/abeerseada)

