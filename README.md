 Task 4: Automated Web Server Deployment with Terraform & Ansible

This project demonstrates automated provisioning and configuration of an AWS EC2 instance as a web server using Terraform and Ansible.

 Structure

- `main.tf` — Terraform configuration to provision EC2 and security group.
- `ansible/` — Contains Ansible playbook, inventory, and custom web page.
  - `site.yml` — Ansible playbook to install NGINX and deploy `index.html`.
  - `inventory` — Hosts file for Ansible (update IP as needed).
  - `index.html` — Custom web page to be served by NGINX.

 Steps

1. Provision Infrastructure with Terraform

```sh
terraform init
terraform apply
```
- This creates a security group and an EC2 instance in AWS.
- The public IP of the instance is output after apply.

 2. Configure Web Server with Ansible

Update `ansible/inventory` with the EC2 public IP.

```sh
cd ansible
ansible-playbook -i inventory site.yml
```
- Installs NGINX and deploys the custom `index.html`.

3. Access the Web App

Visit `http://<EC2_PUBLIC_IP>` in your browser.
 Requirements

- Terraform
- Ansible
- AWS account & credentials
- Existing AWS key pair (`task3.pem`)

 Notes

- `.gitignore` excludes Terraform state and lock files.
- Security group allows SSH (22) and HTTP (80) from

screenshots:
<img width="1151" height="580" alt="image" src="https://github.com/user-attachments/assets/8e352bfa-08d5-4768-9c29-4e67f0ad5a51" />
