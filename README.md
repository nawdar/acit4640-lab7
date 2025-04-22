# Ansible Lab Week 7 - Web Server Automation

## Summary
This lab provisions two EC2 instances and configures them using Ansible to run Nginx with a custom `index.html` served from `/web/html`.

## Commands

```bash
# Create SSH Key Pair
ssh-keygen -t rsa -b 4096 -f ~/.ssh/aws

# Import Key to AWS
./scripts/import_lab_key ~/.ssh/aws.pub

# Provision EC2 Instances
cd terraform
terraform init
terraform apply -auto-approve

# Verify connectivity
cd ../ansible
ansible all -i inventory/hosts.yml -m ping

# Run playbook
ansible-playbook playbook.yml

## HTML Output

Below is the screenshot of the rendered web page:

![Rendered HTML Screenshot](./screenshot.png)
